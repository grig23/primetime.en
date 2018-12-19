---
description: Customize your reference implementation to integrate Adobe Primetime authentication for your production environment.
seo-description: Customize your reference implementation to integrate Adobe Primetime authentication for your production environment.
seo-title: Integrate Primetime authentication
title: Integrate Primetime authentication
uuid: 34cdf1da-261e-462c-a194-4fcb439e5dfb
index: y
internal: n
snippet: y
---

# Integrate Primetime authentication{#integrate-primetime-authentication}

Customize your reference implementation to integrate Adobe Primetime authentication for your production environment.

The Reference Implementation integration of the Primetime authentication service works out-of-the-box as a demonstration. However, to use the integration in a production-ready player, you must implement the following customizations: 

1. Enable or disable entitlement flows.

   The `EntitlementManager` must first initialize and obtain an instance of the Primetime authentication SDK to be enabled. If the `EntitlementManager` does not initialize this library, the manager will be disabled.
   1. Enable the `EntitlementManger`, from your main application class:

      ```java   
      // initialize the AccessEnabler library, required for Primetime PayTV Pass entitlement workflows 
      EntitlementManager.initializeAccessEnabler(this); // comment out this line to disable entitlement workflows
      ```

   1. Use the `ManagerFactory` class to obtain an instance of the `EntitlementManager`.
   
      You must always use the `ManagerFactory` to get an instance of the `EntitlementManager`, as the `ManagerFactory` maintains a single instance of the EntitlementManager for your application. Never instantiate the `EntitlementManager` or `EntitlementManagerOn` classes by using their constructors.    
   
      ```java   
      EntitlementManager entitlementManager =  
        ManagerFactory.getEntitlementManager();
      ```

   The `ManagerFactory` returns an instance of `EntitlementManagerOn`, with the entitlement flows enabled, if you previously called `EntitlementManager.initializeAccessEnabler`. If you do not first call `EntitlementManager.initializeAccessEnabler`, then the `ManagerFactory` will return an instance of `EntitlementManager`, with the entitlement flows disabled. 1. Configure the Requestor ID.

   The Reference Implementation comes pre-configured with the test Requestor ID set to: "REF". You can use this Requestor ID to test your application. When you are ready to use the Requestor ID provided to you by your Primetime authentication representative, update the application's [!DNL res/values/strings.xml] file with your Requestor ID. 

   ```xml
   <!-- Programmer Requestor ID, change to ID provided by your Adobe  
        Primetime pay-TV pass representative --> 
   <string name="adobepass_requestor_id">REF</string> 
    
   <!-- Adobe Primetime pay-TV pass service provider endpoint for production 
        environment --> 
   <string name="adobepass_sp_url_production">sp.auth.adobe.com</string> 
    
   <!-- Adobe Primetime pay-TV pass service provider endpoint for staging  
        environment --> 
   <string name="adobepass_sp_url_staging">sp.auth-staging.adobe.com</string>
   ```

   Additionally, you may need to change the URLs that your application uses to connect to the Primetime authentication services. These include the Primetime authentication staging and production server URLs, and a URL to a Token Verification Service. Check with your Adobe Primetime representative for details. 1. Sign the Requestor ID.

   In order to establish the identity of the Programmer within the Primetime authentication system, the Programmer's Requestor ID is send to the Primetime authentication system. As an added layer of security, the Requestor ID must be signed by the Programmer prior to sending it to Adobe. Adobe recommends that the Programmer setup a service to sign the Requestor ID on a trusted network.

   The Primetime Reference Implementation demonstrates how to sign the Requestor ID, however this is for demonstration purposes only. Adobe strongly recommends that the signing certificate and the signature generator code, under `com.adobe.primetime.reference.crypto`, should not be included within a production application. Instead, you should move it to a trusted networked service. 

1. Configure the Server Environment.

       The Primetime authentication service can run in two separate environments:

    * Staging - The staging environment is used for testing your application. 
    * Production - The production environment is used for live deployments of your application.

       You set the URIs for both the staging and production environments using the application, however you must set which of these is used by the application within the code. In the `com.adobe.primetime.reference.manager.EntitlementManger` class, set the `environmentUri` variable to either `STAGING_URI` or `PRODUCTION_URI` depending on which Primetime authentication service environment you are using.     
    
       >[!NOTE]
       >
       >The provided Requestor ID ("REF") should only be used with the staging environment.

       `com.adobe.primetime.reference.manager.EntitlementManager`:

       ```java    
       // Adobe Primetime authentication service provider endpoint for production environment 
       PRODUCTION_URI = 
         application.getResources().getString(R.string.adobepass_sp_url_production); 
        
       // Adobe Primetime authentication service provider endpoint for staging environment 
       STAGING_URI = 
         application.getResources().getString(R.string.adobepass_sp_url_staging); 
        
       // Set to STAGING_URI when testing against the staging/test environment 
       // Set to PRODUCTION_URI when deploying the application for production use 
       String environmentUri = STAGING_URI; 
        
       // Adobe Primetime authentication service URI used by this application 
       PAYTV_PASS_URI = environmentUri + "/adobe-services"; 
        
       // Token Verification Service URL 
       TVS_URL = "https://" + environmentUri + "/tvs/v1/validate";
       ```

1. Customize the MVPD Selection Grid.

   The content provider selection page displays a table of the top nine MVPDs the user may select from. The application pulls the top nine MVPDs from an ordered list within the application that match the available MVPDs integrated with the Programmer in the Primetime authentication system. The ordered list of the primary MVPDs is keyed on the MVPD ID within the Primetime authentication system, not the MVPD display name. It is important to verify that the MVPD IDs in the primary MVPDs list match the MVPD IDs integrated with the Programmer's account, as in some cases the IDs may be different across integrations. Below is the ordered list of primary MVPDs that is found in the class `com.adobe.primetime.reference.ui.entitlement.MvpdPickerFragment`. 

   ```java
   /* Array of MVPDs to display in a Grid of icons 
   When displaying a grid, only the MVPDs which intersect this array and the 
   ArrayList of all MVPDs are displayed. 
   The array contents are ordered by display preference as only a maximum of 
   MAX_DISPLAY_ICONS are displayed. 
   */ 
   private static final String[] PRIMARY_MVPDS = { 
   "Comcast_SSO",                         // Comcast XFINITY 
   "DTV",                                 // DirectTV 
   "Dish",                                // Dish 
   "TWC",                                 // Time Warner Cable 
   "Cox",                                 // Cox 
   "Charter_Direct",                      // Charter 
   "Verizon",                             // Verizon FiOS 
   "Cablevision",                         // Cablevision Optimum 
   "ATT",                                 // AT&T U-verse 
   "Brighthouse",                         // Brighthouse 
   "Suddenlink",                          // Suddenlink 
   "Mediacom",                            // Mediacom 
   "CableOne",                            // CableOne 
   "WOW",                                 // WOW! 
   "RCN",                                 // RCN 
   "auth_atlanticbb_net",                 // Atlantic Broadband 
   "auth_armstrongmywire_com",            // Armstrong 
   "knology_auth-gateway_net",            // KNOLOGY 
   "serviceelectric_auth-gateway_net",    // Service Electric Cablevision 
   "msauth_midco_net",                    // Midcontinent Communications 
   "auth_metrocast_net",                  // MetroCast 
   "www_websso_mybrctv_com",              // Blue Ridge Communications 
   };
   ```

   The following table provides an example of how the ordered list of primary MVPDs is used. The first column lists the MVPDs integrated with the Programmer. The second column is the (shortened) ordered list of MVPDs. The third column is the result list used to display the top six MVPDs to the user.

   This example uses the top six MVPDs instead of the actual nine just to keep the example simple. Notice how the result list contains the intersection of the first two lists and has the same ordering as the second list. Also, notice that AT&T U-verse is not in the final list, as only the first matching six MVPDs are taken. 

<table id="table_jfv_pyt_xp"> 
 <thead> 
  <tr> 
   <th class="entry"> Available MVPDs </th> 
   <th class="entry"> Primary MVPDs </th> 
   <th class="entry"> Displayed 6 MVPDs </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 
    <ul id="ul_tnh_dzt_xp"> 
     <li id="li_0A033647BA9C459BAD89BDB3091A521B">Comcast XFINITY </li> 
     <li id="li_F94B30AEA186463B854CF6C114CA609D">TWC </li> 
     <li id="li_16E37EB88759466A89D33E5B847E4EAA">Mediacom </li> 
     <li id="li_6B4C17C8075844D082D08BBE632518AA">RCN </li> 
     <li id="li_2205BC64CF4F4E1A88B4FEC5E138ED0E">Dish </li> 
     <li id="li_B65063AE7B39482AA318852D357537FD">AT&amp;T U-verse </li> 
     <li id="li_C62DC756B3D94F1CACFC829A58E8121B">CableOne </li> 
     <li id="li_E9D8B4075A2744E4845557A3CE5EC9B2">Brighthouse </li> 
     <li id="li_9D8BF482CCD94418AAC84572F330AAAA">Atlantic Broadband </li> 
     <li id="li_1391B5BD4E2E4BB291DA526ECCFDF3D6">WOW! </li> 
     <li id="li_49DE45233FAF4FD19CA1F29036CD74B5">MetroCast </li> 
     <li id="li_C8D73FCBF43747FB8A305582FE4C68F3">DirectTV </li> 
     <li id="li_69D2037E37DB4903B2BFEE603E8E082A">Cox </li> 
     <li id="li_E7CF44ACD1234A33823670CAA697E82A">Cablevision Optimum </li> 
    </ul> </td> 
   <td> 
    <ol id="ol_xp4_2zt_xp"> 
     <li id="li_A8D86CB58FC54AF98E9C2FA4C1DBE163">Comcast XFINITY </li> 
     <li id="li_E384D4DBBB6F4F7D8D7FF8BF8F06641B">DirectTV </li> 
     <li id="li_DA86C0799F3041A1B051BCA8908818B7">Dish </li> 
     <li id="li_1B27BA6CBFBE492CA5BE9884553147DD">TWC </li> 
     <li id="li_985D88D668544A1DBB1F5B68948209FB">Cox </li> 
     <li id="li_7593E145528D4BBC99FFF4E634DC646D">Charter </li> 
     <li id="li_B328296B111E47198D44C0893B5BDB74">Verizon FiOS </li> 
     <li id="li_7B9AEAA7A6F24208B8D303BED9DA66D2">Cablevision Optimum </li> 
     <li id="li_7FAD0D64ECDA411E9A41B147B7560ACA">AT&amp;T U-verse </li> 
    </ol> </td> 
   <td> 
    <ol id="ol_ggx_2zt_xp"> 
     <li id="li_D6F9CB43866D404B8CB85544B2685765">Comcast XFINITY </li> 
     <li id="li_44BFDBDC27F2413C91F578D0B40A4163">DirectTV </li> 
     <li id="li_A006BFCCFAA247288EE9E04D708039C7">Dish </li> 
     <li id="li_AB53AAC8760A41518A7C36B5671F3DDE">TWC </li> 
     <li id="li_91798252DA1F4C1492F5C2D6E025CCA8">Cox </li> 
     <li id="li_70414FBACA7B465E8ADE43123326470F">Cablevision Optimum </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>
