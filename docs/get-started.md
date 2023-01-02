---
sidebar_position: 1
---

# Get Started

### What is Insightify Extension?

Insightify Extension is an activeGate extension that is developed to pull and report key metrics. It leverages Dynatrace APIs to pull the metrics from the configured tenant. It will enable your customer to get a single pane of all the different health metrics in the tenant itself highlighting some of the usage and adoption features in Dynatrace.

### How does it work?

End-user uploads the extension on an activeGate and configure the endpoint. Once configured, they will start receiving the data and the data would be available a dashboard for that endpoint.  
![extension-workflow](Health-extension.png)

### Features?

The extension reports the following set of metrics:  
· **License Consumption Insight:** highlighting the current usage of DEM, DDUs, Host Units, Host Units.  
· **Environment Feature flags:** The extension would report on the different feature flags that are currently being used in the environment (like Request attributes, Alerting
profiles. etc.)  
· **Problem Details:** this section would report on the MTTR, and the total number of problems received in the environment in the past month.  
· **Problem by Severity and Impacted Entities**: Dynatrace received problems classified by different severity along with the different entities (like Environment, Services, etc.)  
· **License consumption by management zone:** This section will highlight the license utilization by management zone (once enabled).  
· **License consumption by host group:** This section will highlight the license utilization by host groups (once enabled).  

## Extension installation and configuration  
1. Find the extension from [here](https://github.com/Dynatrace/Dynatrace-health-extension/custom.remote.python.dt_health_report.zip)  
2. Download to get the extension ZIP file. **Don't rename the file.**  
3. Unzip the ZIP file to the `plugin_deployment` (found at `/opt/dynatrace/remotepluginmodule/plugin_deployment/`) directory of your ActiveGate host.  
4. In the Dynatrace menu, go to **Settings > Monitored technologies > Custom extensions and select Upload Extension.**  
5. Upload the ZIP file.
6. Enter the following endpoint information for pulling data:  

   **Endpoint name**: Any label to identify this connection. It is used for identification purposes.
   **Tenant URL**:    Tenant endpoint that you'd like to pull data from. Configure it as `https://abc.live.dynatrace.com/api/v1/`  
                      Replace abc with the tenant UUID for SaaS while for managed, configure the endpoint as `https://managed-server/e/environment-endpoint/api/v1`  
   **Tenant Token**: Token that will be used to pull the data from the configured tenant. Make sure your token has the following permissions:  
                     - Read problems (API v1)  
                     - Read problems (API v2)  
                     - User session query language (API v1)  
                     - CaptureRequestData (API v1)  
                     - Read metrics (API v2)  
**Publish URL**:     Tenant where you would like to push the pulled metrics. Configure it as `http://xyz.live.dynatrace.com/api/v2/`  
                     Replace abc with the tenant UUID for SaaS while for managed, configure the endpoint as `https://managed-server/e/environment-endpoint/api/v1`  
**Publish Token**:   Token that will be used to push the metrics. Make sure your token has the following permissions:  
                     - Write config (Configuration API v1): To create a dashboard with the captured metrics.  
                     - Read config (Configuration API v1) : Permission to access to verify if the dashboard is already created.  
                    - Ingest Metrics (Configuration API v1): Permissions to push the host units, DEM units into Dynatrace.  
**Capture consumption data per management zone**:        Set the flag to **Yes** in order to pull host units/DEM consumption metrics and slice it as per management zones.  
**Capture host units consumption data per host groups**: Set the flag to **Yes** in order to pull host units consumption metrics and slice it as per host groups.  
**Capture and report problem data**:                     Set the configuration to **Yes** to pull problem data like MTTR, problem details, etc.  
**Capture and report adoption data**:                    Set the configuration to **Yes** to pull adoption data.  




`

