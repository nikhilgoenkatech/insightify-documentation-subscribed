---
sidebar_position: 3
---

# Quick Links

### License and bill of materials

Extension would lead to DDU consumption. A fully configured endpoint would consume **350 DDUs** a month for about **15 management zones and 10 host-group**. For more details on DDU consumption, refer to [help link](https://www.dynatrace.com/support/help/shortlink/metric-cost-calculation).

### How long does it take for data to reflect?

Extension has different set of metrics which are consumed at different time interval considering/assuming the criticality of a specific group of metrics.

#### License consumption

The license consumption is updated every hour including the consumption per management zone, host group.

> Note: The consumption metrics are pulled using API, so if the extension is not running the data would be lost during that time. So, this consumption data should be considered as a guideline and more accurate consumption refer to https://myaccount.dynatrace.com (SaaS) or CMC.  

#### Environment Flags
The environment/key feature flags will be pulled once the **Capture adoption flags** is set to **Yes**. These flags are unlikely to be changed frequently for a matured environment, so, these are pulled and updated every 7 days. The first set of environment flag would be available only after 7-days. Lastly, the dashboard considers last 7 days while showing the trend for these metrics.

#### Problem Data and Application Data

The key feature flags will be pulled once the **Capture problem data** is set to **Yes**. The problem related metrics are pulled and updated every day once every 24-hours. The first set of problem data and application data would be available after 24-hours. Lastly, the dashboard considers the dashboard considers last 24-hours while showing the trend for these metrics.

#### Consumption Data per management zone

The consumption metrics (consumption.hostUnits, consumption.demUnits, consumption.ddus) is pulled and pushed every hour.

> NOTE: If there are hosts appearing in multiple management zone, the consumption will be calculated multiple times. So, we recommend to use consumption data per management zones only for reference and not billing.  

#### Consumption Data per host group

The consumption metrics per host group(consumption.hostUnits) is pulled and pushed every hour.  
