# Block Subscription to an API

An API publisher **blocks subscription** to an API is a way of disabling access to it and managing its usage and monetization. A subscription blocking can be temporary or permanent. There is an unblocking facility to allow API invocations back.

You can block APIs by subscriptions. That is, a given user is blocked access to a given API that the user has subscribed to using a given application. If a user is subscribed to two an APIs using the same application and you block access to only one of the APIs, the user can still continue to invoke the other APIs that s/he subscribed to using the same application. Also, the user can continue to access the same API subscribed to using different applications.

!!! info
    API level subscription blocking is useful to control only the subscriptions created for a specific API by a user. If you want to block all API requests from a specific application/user/specific IP address or to a specific API, you can use [request blacklisting](../../../../Learn/RateLimiting/managing-throttling/).


Blocking can be done at two levels:

-   **Block production and sandbox access** : API access is blocked with both production and sandbox keys.
-   **Block production access only** : Allows sandbox access only. This is useful when you want to fix and test an issue in an API. Rather than blocking all access, you can block production access only, allowing the developer to fix and test it.

  <html>
  <div class="admonition warning">
  <p class="admonition-title">Warning</p>
  <p>When <a href="../../../../GettingStarted/overview/#api-gateway">API Gateway</a> caching is enabled (it is enabled by default), even after blocking a subscription, consumers might still be able to access APIs until the cache expires, which happens approximately every 15 minutes. Likewise, the API Gateway cache applies even when an API is unblocked.</p>
  </div> 
  
  <div class="admonition note">
  <p class="admonition-title">Note</p>
  <p>See the following topics for the descriptions on the concepts that you need to know when you block subscriptions to an API:
  <ul>
    <li><a href="../../../../GettingStarted/key-concepts/#application">Applications</a></li>
    <li><a href="../../../../GettingStarted/key-concepts/#rate-limits">Rate Limiting</a></li>
    <li> <a href="../../../../GettingStarted/key-concepts/#access-token">Access tokens</a></li></ul>
    </p>
  </div> 
  </html>

1.  Create two APIs.
     1.  Sign in to the WSO2 API Publisher.

     2.  Create two APIs and publish them to the WSO2 API Developer Portal.

         <html>
         <div class="admonition tip"> 
         <p class="admonition-title">Tip</p>
         <p>For more information, see [Create and Publish an API](../../../../Learn/DesignAPI/CreateAPI/create-a-rest-api/).</p>
         </div>
         </html>
         
         <html>
         <body>
         <img src="../../../../assets/img/Learn/two-apis-for-block-subscription.png" onclick="window.open('../../../../assets/img/Learn/two-apis-for-block-subscription.png', '_self');" alt="two-apis-for-block-subscription" width="100%" height="100%">
         </body>
         </html>

2.  Subscribe to both the APIs.
     1.  Sign in to the WSO2 API Developer Portal and click **APIs**.

         Note that the two APIs are visible in the APIs page.

     2.  Subscribe to both APIs using the same application.

         You can use the default application or create your own.
         <html>
         <body>
         <img src="../../../../assets/img/Learn/same-application-for-two-apis.png" onclick="window.open('../../../../assets/img/Learn/same-application-for-two-apis.png', '_self');" alt="same-application-for-two-apis" width="100%" height="100%">
         </body>
         </html>
         
         You can see the Apis you have subscribed as follows and the **Status** as **unblocked**.
         <html>
         <body>
         <img src="../../../../assets/img/Learn/same-application-subscribed-for-two-apis.png" onclick="window.open('../../../../assets/img/Learn/same-application-subscribed-for-two-apis.png', '_self');" alt="same-application-subscribed-for-two-apis" width="100%" height="100%">
         </body>
         </html>
        
     3.  Generate keys and obtain an access token for application.
       
3.  Invoke both APIs using the access token you received in the previous step.

     -   [**Format**](#Format)
     -   [**Example**](#Example)
     -   [**Response**](#Response)
     
      <html>
      <div class="admonition tip"> 
      <p class="admonition-title">Tip</p>
      <p>For more information , see  [Consume an API](../../../../Learn/ConsumeAPI/InvokeApis/InvokeApisUsingTools/invoke-an-api-using-the-integrated-api-console/)..</p>
      </div>
      </html>

      <html>
      <body> 
      <img src="../../../../assets/img/Learn/same-application-for-two-apis-response.png" onclick="window.open('../../../../assets/img/Learn/same-application-for-two-apis-response.png', '_self');" alt="same-application-for-two-apis-response" width="100%" height="100%">
      </body>
      </html>

     The following is the [cURL](http://curl.haxx.se/download.html) command format for phoneverify2 API.
     
     **Command**
 
     ``` java
     curl -X POST "https://localhost:8243/phoneverify2/1.0/checkPhoneNumber" -H "accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer 1b4cde76-3951-32bb-9ace-f530bc478490" -d "{ \"CheckPhoneNumber\": { \"PhoneNumber\": \"18006785432\", \"LicenseKey\": \"0\" }}"
     ```

     You can invoke the **PhoneVerification** API with the same token.
     You have subscribed to two APIs and invoked them successfully. Let's block one subscription and see the outcome.

4.  Block an API.

     1.  Login in to the API Publisher.

     2.  Click **API** and click on the API that you need to block.

         In this case, click on the `PhoneVerify2` API.

     3.  Click **Subscriptions** to navigate to the managed subscription section.

     4. Click **Block All**.
        <html>
        <body>
        <img src="../../../../assets/img/Learn/same-application-subscribed-for-two-apis-and-blocked.png" onclick="window.open('../../../../assets/img/Learn/same-application-subscribed-for-two-apis-and-blocked.png', '_self');" alt="same-application-subscribed-for-two-apis-and-blocked" width="100%" height="100%">
       </body>
       </html>
        
       <html>
       <div class="admonition tip"> 
       <p class="admonition-title">Tip</p>
       <p>You can block production only instead of block all. Also you can unblock the subscription which are you have blocked.</p>
       </div>
       </html>

5.  Invoke the APIs to test the blocked API.

    1. Login in to the API Store.

    2. Invoke the two APIs ( `PhoneVerify2` and `PhoneVerification` ) again.

         <html>
         <div class="admonition tip">
         <p class="admonition-title">tip</p>
         <p>You might have to <b>regenerate the access token</b> for the respective application that you subscribed the APIs to (for example in this case it will be `DefaultApplication)` if the access token expiration time (1 hour by default) has passed since the last time you generated it. </p>
         </div>
         </html>

         Note that you can invoke `PhoneVerification` again, but when you invoke `PhoneVerify2` , it gives a message that the requested API is temporarily blocked. Neither the API publisher nor any subscriber can invoke the API until the block is removed.

         <html>
         <div class="admonition warning">
         <p class="admonition-title">Warning</p>
         <p>When [Gateway caching](../../../../GettingStarted/overview/#api-gateway) is enabled, which is the case by default, the subscription blocking will take place only after the token cache expires (the default token cache expiry time is 15min). However, if the token is regenerated after the API is blocked, then the API will be blocked immediately.</p>
         </div>
         </html>


        **Response when invoking PhoneVerify2**

        ``` java
        <ams:fault xmlns:ams="http://wso2.org/apimanager/security">
            <ams:code>900907</ams:code>
            <ams:message>The requested API is temporarily blocked</ams:message>
            <ams:description>Access failure for API: /TestAPI1/1.0.0, version: 1.0.0 status: (900907) - The requested API is temporarily blocked</ams:description>
        </ams:fault>
        ```
        <html>
        <body>
        <img src="../../../../assets/img/Learn/same-application-subscribed-for-two-apis-and-blocked-response.png" onclick="window.open('../../../../assets/img/Learn/same-application-subscribed-for-two-apis-and-blocked-response.png', '_self');" alt="same-application-subscribed-for-two-apis-and-blocked-response" width="100%" height="100%">
        </body>
        </html>
        
     If you click **Applications** in the API Developer portal, and select the application that you used to subscribe to the API, the details of the blocked subscription appears.

     <html>
     <body>
     <img src="../../../../assets/img/Learn/same-application-subscribed-for-two-apis-and-combined-subscription.png" onclick="window.open('../../../../assets/img/Learn/same-application-subscribed-for-two-apis-and-combined-subscription.png', '_self');" alt="same-application-subscribed-for-two-apis-and-combined-subscription" width="100%" height="100%">
     </body>
     </html>

6.  Unblock the API.

     1.  Go back to the API Publisher.

     2.  Click on the respective API

         In this case, click `PhoneVerify2`.

     3.  Click **Subscriptions** and click **Unblock** corresponding to the respective subscription.

         Make sure to click on the subscription that corresponds to the correct Application.

         If you invoke `PhoneVerify2` again, you will notice that you can invoke the API as usual.

         <html>
         <div class="admonition warning">
         <p class="admonition-title">Warning</p>
         <p>When [Gateway caching](../../../../GettingStarted/overview/#api-gateway) is enabled, which is the case by default, the subscription unblocking will take place only after the token cache expires (the default token cache expiry time is 15min). However, if the token is regenerated after the API is unblocked, then the API will be unblocked immediately.</p>
         </div>
         </html>

         You have subscribed to two APIs, blocked subscription to one and tested that you cannot invoke the blocked API.
