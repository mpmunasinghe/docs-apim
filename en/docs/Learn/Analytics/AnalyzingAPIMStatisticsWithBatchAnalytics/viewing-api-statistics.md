# Viewing API Statistics

API statistics are provided for both the API Publisher and the Developer Portal. 

From API-M Analytics 3.0.0 release onwards, Publisher and Developer Portal statistics are moved out from the Publisher and Developer portal apps.
And those can be viewed using the **dashboard** runtime of the API-M Analytics server.

For instructions on how to set up Analytics, see [Configuring APIM Analytics](../configuring-apim-analytics.md) . 
Once Analytics is set up, follow the instructions below to view statistics relevant to API Publisher and Developer Portal.

First, [invoke a few APIs](../../../ConsumeAPI/InvokeApis/InvokeApisUsingTools/invoke-an-api-using-the-integrated-api-console/) to generate traffic and see the statistics.

!!! note
      The following widgets on the API Manager statistical dashboards, display real runtime statistics even when Analytics is not set up (as described in [Configuring APIM Analytics](_Configuring_APIM_Analytics_) ).
      
      **Publisher Dashboard**
      
      + Overview Page
        + Total Api Count
        + Total App Count
        + Total Subscriptions
        + Total Signups
        + Top Api Creators
        + Top App Creators
        + Top Subscriptions per API Provider
      + API and Application Statistics Page
        + Apis Created Over Time
        + Apps Created Over Time
      + Developer Statistics Page
        + Subscriptions Over Time
        + Developer Signups Over Time
      + Faults Page
        + Top Faulty Apis
        + Top Throttled Apis
      
      **Developer Portal Dashboard**
      
      + Registered Application Users


!!! warning
      Please note that our data summarization logic summarizes the data on a **per day** basis.


The sections below explain how to access the statistical dashboards:

+ Log in to the Analytics Dashboard by accessing `<Protocol>://<Host>:<Port>/analytics-dashboard` (ex: [https://localhost:9643/analytics-dashboard](https://localhost:9643/analytics-dashboard)). 
+ After login in, you will see the **APIM Publisher** and the **APIM Developer Portal** dashboards listed.
  
       ![](../../../assets/img/Learn/analytics-dashboard-listing.png)

+ Click on the card of any desired dashboard to view that particular dashboard.
+ Admin Portal Statistics can be viewed from the admin app.
    
Please refer below sub sections for more details about each dashboard.
    
-   [**API Publisher statistics**](#api-publisher-statistics)
-   [**Developer Portal statistics**](#developer-portal-statistics)
-   [**Admin Portal Statistics**](#admin-portal-statistics)

## API Publisher statistics

!!! info
      Unlike the previous releases of API-M Analytics dashboards, Publisher statistics dashboard can be viewed by any user having Analytics role, Creator role or Publisher role.
      And these permissions can be changed as per your preferences by going to **Settings** options of the dashboard. More information can be found at [Managing Analytics Dashboard Permissions](../../../../Learn/Analytics/managing-dashboard-permissions/) page.
      
 API Publisher dashboard has 8 main pages namely **Overview**, **API and Application Statistics**, **Developer Statistics**, **Usage Summary**, **Devices**, **API Proxy Performance**, **Faults**, and **Geo Map**.
 
### Overview 
#### Total API Count
This widget displays the total number of apis created and the number of apis created within the last week by the publishers of logged in user's tenant.

  ![](../../../assets/img/Learn/publisher-overview-total-api-count.png)

#### Total App Count
This widget displays the total number of applications created and the number of applications created within the last week by the subscribers of the logged in user's tenant.

 ![](../../../assets/img/Learn/publisher-overview-total-app-count.png)

#### Total Subscriptions
This widget displays the total api subscriptions by the subscribers of the logged in user's tenant and its last weeks statistics of the same factor.

 ![](../../../assets/img/Learn/publisher-overview-total-subscriptions.png)
 
#### Total Signups
This widget displays count of the unique subscribers logged in to the developer portal app and its last week statistics of the same factor.

 ![](../../../assets/img/Learn/publisher-overview-total-signups.png)

#### Overal API Stats

This widget has two sections.

+ Api Availability - Displays a percentage of api availability 
+ Top Rated Apis - Displays the total number of stars received (ratings) by each api 
 
 for that particular tenant.

!!! Note
      In order to view statistics of **Api Availability** widget, it is required to enable alerts as described in [Configuring Alerts](../../ManagingAlertsWithRealTimeAnalytics/configuring-alerts).
      
  The availability of APIs statistics is directly related to the [Availability of APIs (health monitoring)](../../ManagingAlertsWithRealTimeAnalytics/alert-types/#availability-of-apis-api-health-monitoring) alert type. 
  
  ![](../../../assets/img/Learn/publisher-overview-overall-api-stats.png)
  
Along with the total number of stars received for each api, Top Rated Apis section of the widget displays the api creator of each api as well. 
By clicking on the filter arrow
<html>
<body>
<img src="../../../../assets/img/Learn/analytics-filterby-arrow.png" width="20"/>
</body>
</html>
,you can search by **Api name** and **Ratings**.

  ![](../../../assets/img/Learn/publisher-overview-overall-api-stats-ratings.png)

#### Top API Creators

As the name depicts this widget displays the top api creators and the percerntage of apis that each of them have created.
You can choose the limit of api creators that you want to see by giving the number under the limit field.
   
   ![](../../../assets/img/Learn/publisher-overview-top-api-creators-1.png)
   
You also get a list view of api creators along with the number of apis created by each api creator. 
This list can be searched either via Api name or Api count.

   ![](../../../assets/img/Learn/publisher-overview-top-api-creators-2.png)

#### Top App Creators

As same as Top Api Creators widget, Top App Creators widget displays a percentage of apps created by each app creator and also a list of app creators along with the number of apps they created with the filtering capabilities.

   ![](../../../assets/img/Learn/publisher-overview-top-app-creators-1.png)
  
   ![](../../../assets/img/Learn/publisher-overview-top-app-creators-2.png)
  
#### Top Subcriptions per API Provider

This widget displays the percentage of subscription count against each api provider. It also has a list view with the subscription count with the filtering capability based on the provider name and count.

   ![](../../../assets/img/Learn/publisher-overview-top-subscription-per-provider-1.png)
      
   ![](../../../assets/img/Learn/publisher-overview-top-subscription-per-provider-2.png)
   
### API and Application Statistics

Under this page you can choose to view APIs/Apps based on different filter criteria.
You can also select the time period and granularities such as minute, hour,day for which you wish to view the statistics. 

<html>
<body>
<img src="../../../../assets/img/Learn/publisher-date-time-picker.png" width="500"/>
</body>
</html>

#### APIs Created Over Time

This widget displays the number of apis published over a given time period.
You can filter based on the api created by you or apis created by all.
It also has a list view along with the filtering capability based on Api Name.

<html>
<body>
<img src="../../../../assets/img/Learn/publisher-api-and-app-api-created-over-time.png" 
     onclick="window.open('../../../../assets/img/Learn/publisher-api-and-app-api-created-over-time.png', '_self');" 
     alt="failover" width="70%" height="70%"/>
</body>
</html>

#### Apps Created Over Time

This widget displays number of applications created over a given period of time. Statistics can be filtered based on api creator, app creator and subscribed api.
This also has a list view with app name and created time which can be filtered based on the app name.

<html>
<body>
<img src="../../../../assets/img/Learn/publisher-api-and-app-app-created-over-time.png" 
     onclick="window.open('../../../../assets/img/Learn/publisher-api-and-app-app-created-over-time.png', '_self');" 
     alt="failover" width="70%" height="70%"/>
</body>
</html>

### Developer Statistics

#### Subscriptions Over Time

This widget displays the number of subscriptions created for an API over a given period.

<html>
<body>
<img src="../../../../assets/img/Learn/publisher-dev-stats-subscription-over-time.png" 
     onclick="window.open('../../../../assets/img/Learn/publisher-dev-stats-subscription-over-time.png', '_self');" 
     alt="failover" width="70%" height="70%"/>
</body>
</html>

#### Developer Signups Over Time

This widget displays the number of developers who signed up to the developer portal over time. 

<html>
<body>
<img src="../../../../assets/img/Learn/publisher-dev-stats-developer-signups-over-time.png" 
     onclick="window.open('../../../../assets/img/Learn/publisher-dev-stats-developer-signups-over-time.png', '_self');" 
     alt="failover" width="70%" height="70%"/>
</body>
</html>

### Usage Summary

#### Overall API Usage

This widget displays the number of subscriptions of each API with a graphical view of number of api invocations. 
It also has a list view of total number of api invocations across all versions.

<html>
<body>
<img src="../../../../assets/img/Learn/publisher-usage-summary-overall-api-usage.png" 
     onclick="window.open('../../../../assets/img/Learn/publisher-usage-summary-overall-api-usage.png', '_self');" 
     alt="failover" width="70%" height="70%"/>
</body>
</html>

#### API Version Usage Summary

This widget displays the api invocation counts for each of the APIs grouped by each API version.

<html>
<body>
<img src="../../../../assets/img/Learn/publisher-usage-summary-api-version-usage-summary.png" 
     onclick="window.open('../../../../assets/img/Learn/publisher-usage-summary-api-version-usage-summary.png', '_self');" 
     alt="failover" width="70%" height="70%"/>
</body>
</html>

#### Top API Users

This widget lists the users who has done the most number of api invocations. 
It also has several filters to search based on the creator of the api ( either All or Me ), Api Name and Api Version.

<html>
<body>
<img src="../../../../assets/img/Learn/publisher-usage-summary-top-api-users.png" 
     onclick="window.open('../../../../assets/img/Learn/publisher-usage-summary-top-api-users.png', '_self');" 
     alt="failover" width="70%" height="70%"/>
</body>
</html>

#### API Resource Usage Summary

This widget displays the number of api invocations made by resources for an API in a list view.

<html>
<body>
<img src="../../../../assets/img/Learn/publisher-usage-summary-api-resource-usage-summary.png" 
     onclick="window.open('../../../../assets/img/Learn/publisher-usage-summary-api-resource-usage-summary.png', '_self');" 
     alt="failover" width="70%" height="70%"/>
</body>
</html>

#### API Backend Usage Summary

This widget displays the number of total api invocations aggregated based on Api Name, Api Version, Api Creator, Api Context  and Api Backend endpoint.

<html>
<body>
<img src="../../../../assets/img/Learn/publisher-usage-summary-api-backend-usage-summary.png" 
     onclick="window.open('../../../../assets/img/Learn/publisher-usage-summary-api-backend-usage-summary.png', '_self');" 
     alt="failover" width="70%" height="70%"/>
</body>
</html>

#### API Last Access Summary

This widget is a list view of the last access times of an API, according to the version and the accessed subscriber.

<html>
<body>
<img src="../../../../assets/img/Learn/publisher-usage-summary-api-last-access-summary.png" 
     onclick="window.open('../../../../assets/img/Learn/publisher-usage-summary-api-last-access-summary.png', '_self');" 
     alt="failover" width="70%" height="70%"/>
</body>
</html>

### Devices

#### Top User Agents

This widget displays the percentage of api invocations using each browser. And the results can be filtered based on Api Creator ( either All or Me), Api Name and Api version.

<html>
<body>
<img src="../../../../assets/img/Learn/publisher-devices-top-user-agents.png" 
     onclick="window.open('../../../../assets/img/Learn/publisher-devices-top-user-agents.png', '_self');" 
     alt="failover" width="70%" height="70%"/>
</body>
</html>

#### Top Platforms

This widget displays the percentage of api invocations done using different operating systems.
Results of this widget also can be filtered based on Api Creator ( either All or Me), Api Name and Api version.

<html>
<body>
<img src="../../../../assets/img/Learn/publisher-devices-top-platforms.png" 
     onclick="window.open('../../../../assets/img/Learn/publisher-devices-top-platforms.png', '_self');" 
     alt="failover" width="70%" height="70%"/>
</body>
</html>

### API Proxy Performance

#### API Latency Time

This widget displays the execution time of the APIs represented as a combination of throttling, In mediation, Out mediation, backend response time, and authentication time.
It also displays a comparison view of the latencies.

<html>
<body>
<img src="../../../../assets/img/Learn/publisher-api-proxy-performance-api-latency-time-1.png" 
     onclick="window.open('../../../../assets/img/Learn/publisher-api-proxy-performance-api-latency-time-1.png', '_self');" 
     alt="failover" width="70%" height="70%"/>
<img src="../../../../assets/img/Learn/publisher-api-proxy-performance-api-latency-time-2.png" 
      onclick="window.open('../../../../assets/img/Learn/publisher-api-proxy-performance-api-latency-time-2.png', '_self');" 
      alt="failover" width="70%" height="70%"/>
</body>
</html>

### Faults

#### Top Faulty APIs

A successful invocation is when an API receives the expected response. 
In Analytics, if a runtime exception that is related to the backend communication occurs, it is considered as a faulty invocation. 
However, authentication related issues are not considered as faulty invocations. 
A percentage of faulty invocations for each api is displayed in this widget and it also has a list view which displays the total number of faulty invocations for each api.

<html>
<body>
<img src="../../../../assets/img/Learn/publisher-fault-top-faulty-apis.png" 
     onclick="window.open('../../../../assets/img/Learn/publisher-fault-top-faulty-apis.png', '_self');" 
     alt="failover" width="70%" height="70%"/>
</body>
</html>

#### Top Throttled Out APIs

This widget displays a percentage of throttled out request counts for each api as well as a list view with throttled out request count.

<html>
<body>
<img src="../../../../assets/img/Learn/publisher-fault-top-throttled-out-apis.png" 
     onclick="window.open('../../../../assets/img/Learn/publisher-fault-top-throttled-out-apis.png', '_self');" 
     alt="failover" width="70%" height="70%"/>
</body>
</html>

### Geo Map

#### Geo Location Based Invocations

Geolocation based statistics are used to carryout detailed monitoring of geographic locations. 
You need to pass an x-forwarded-for header with the relevant IP in the API request in order to generate Geolocation based statistics. 
For more information, see [Using Geolocation Based Statistics](../../../../Learn/Analytics/AnalyzingAPIMStatisticsWithBatchAnalytics/UsingGeoLocationBasedStatistics/configuring-geolocation-based-statistics/). 

The data script that updates statistics related to geo locations is executed once a day. 
Therefore, at a given time, some statistics generated within the last 24 hours may not be displayed in this widget.

<html>
<body>
<img src="../../../../assets/img/Learn/publisher-geo-map-geo-based-invocation.png" 
     onclick="window.open('../../../../assets/img/Learn/publisher-geo-map-geo-based-invocation.png', '_self');" 
     alt="failover" width="70%" height="70%"/>
</body>
</html>
 
## Developer Portal Statistics

!!! info
      Similar to the Publisher statistics dashboard, Developer Portal statistics dashboard can be viewed by any user having Analytics role or subscriber role. 
      And these permissions can be changed as per your preferences by going to **Settings** options of the dashboard. More information can be found at [Managing Analytics Dashboard Permissions](../../../../Learn/Analytics/managing-dashboard-permissions/) page.


Log into the analytics-dashboard application and access developer portal statistics ( ex: [https://localhost:9643/analytics-dashboard/dashboards/apimdevportal](https://localhost:9643/analytics-dashboard/dashboards/apimdevportal) ) dashboard from there.

#### Faulty Invocation per Application

In a faulty API invocation, the message is mediated though the fault sequence. 
By default, the API Manager considers an API invocation to be faulty when the backend service is unavailable or if a runtime exception occurs that is related to the backend communication.
The total number of invocations made by each application that are faulty are represented in these statistics.

<html>
<body>
<img src="../../../../assets/img/Learn/devportal-faulty-invocations-per-application.png" 
     onclick="window.open('../../../../assets/img/Learn/devportal-faulty-invocations-per-application.png', '_self');" 
     alt="failover" width="70%" height="70%"/>
</body>
</html>

#### Top Application Users

This widget displays the users who made the largest number of API calls per application. 
You also can limit the number of users that needs to be listed by changing the limit filter in the UI.

<html>
<body>
<img src="../../../../assets/img/Learn/devportal-top-application-users.png" 
     onclick="window.open('../../../../assets/img/Learn/devportal-top-application-users.png', '_self');" 
     alt="failover" width="70%" height="70%"/>
</body>
</html>
     
#### Registered Application Users

The statistics for this widget takes the number of users shared across each application in to consideration. 

To enable application sharing among users within the same organization, see [Sharing Applications](../../../../Learn/ConsumeAPI/ManageApplication/SharingApplications/sharing-applications/).
Only users who have generated access tokens using the [password grant type](../../../../Learn/ConsumeAPI/ManageApplication/GenerateKeys/GrantTypes/password-grant/) are considered in these statistics.

<html>
<body>
<img src="../../../../assets/img/Learn/devportal-registered-application-users.png" 
     onclick="window.open('../../../../assets/img/Learn/devportal-registered-application-users.png', '_self');" 
     alt="failover" width="70%" height="70%"/>
</body>
</html>

#### Resource Usage of Application

This widget displays the usage of resources of the APIs by each application.

<html>
<body>
<img src="../../../../assets/img/Learn/devportal-resource-usage-of-application.png" 
     onclick="window.open('../../../../assets/img/Learn/devportal-resource-usage-of-application.png', '_self');" 
     alt="failover" width="70%" height="70%"/>
</body>
</html>

#### Api Usage of Application

This widget displays the number of invocations made for each API by each application.

<html>
<body>
<img src="../../../../assets/img/Learn/devportal-api-usage-of-application.png" 
     onclick="window.open('../../../../assets/img/Learn/devportal-api-usage-of-application.png', '_self');" 
     alt="failover" width="70%" height="70%"/>
</body>
</html>

## Admin Portal Statistics

Log in to the Admin Portal ( `https://localhost:9443/admin` ). 
API Availability is the only statistical view that exists in the Admin Portal. Admin users can view API Availability statistics by navigating to **ANALYTICS &gt; API AVAILABILITY** .

#### Availability of APIs

The status of the APIs (all API versions) represented in a tabular view.

<html>
<body>
<img src="../../../../assets/img/Learn/admin-portal-apiAvailability.png" 
     onclick="window.open('../../../../assets/img/Learn/admin-portal-apiAvailability.png', '_self');" 
     alt="failover" width="100%" height="100%"/>
</body>
</html>

<html>
<table>
<thead></thead>
<tbody>
<tr class="odd">
<td>Status</td>
<td><div class="content-wrapper">
<p>This indicates the status of the API. There are two possible values; <strong>Available</strong> and <strong>Limited</strong> .</p>
<p><strong>Available</strong> - This status indicates that the API has traffic with normal successful invocations. By default, if an API receives successful invocations for at least one out of five invocations within 30000 milliseconds, the status of the API becomes <strong>Available</strong> .</p>

<html><div class="admonition info">
<p class="admonition-title">Note</p>
<p>Note that only the APIs that have traffic are represented in this tabular representation.</p>
</div>
</html>

<html><p><strong>Limited</strong> - If an API receives an alert due to one of the reasons indicated in [Availability of APIs (health monitoring)](../../../../Learn/Analytics/ManagingAlertsWithRealTimeAnalytics/alert-types/#availability-of-apis-api-health-monitoring), the API status changes to <strong>Limited</strong> .</p></html>

<html><div class="admonition info">
<p class="admonition-title">Note</p>
<p>For more information on how to view the generated alerts, see [Viewing Alerts](../../../../Learn/Analytics/ManagingAlertsWithRealTimeAnalytics/viewing-alerts/)</p>
</div>
</html>

</div></td>
</tr>
</tbody>
</table>
</html>

The availability of APIs statistics is directly related to the [Availability of APIs (health monitoring)](../../../../Learn/Analytics/ManagingAlertsWithRealTimeAnalytics/alert-types/#availability-of-apis-api-health-monitoring) alert type.
