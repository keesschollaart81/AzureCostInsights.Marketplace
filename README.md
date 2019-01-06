# Azure Cost Insights

Get in control over your Azure Costs! This Widget gives you insights in your teams' infrastructure spendings. Add the widget to your dashboard and detect anomolies much quicker. The first widget is for free, forever!

## Key Features

- Visualize cost data by Resouce Group, Resouce Type, Subscription or Tag
- Fully customizable: bar & line chart-types, stacked & non-stacked, any timespan
- Filter by subscription and then/or by the name of Resource Group, Resource Type or by the value of the selected Tag (using glob patterns)
- No external service, data stay's within your Azure DevOps tenant
- Leverages your Azure Service Connections for downloading your data
- 1 widget for free, additional widget-instances starting at 1$ per widget per month (in-app purchase)

## Getting started

You need to create an Azure Pipeline for the widget to work. This pipeline is going to download and host your cost-data, used by the widget. [Read the 4 good reasons for 'why the need of a pipeline' here](https://github.com/keesschollaart81/AzureCostInsights.Marketplace/wiki/Why-the-need-of-a-Pipeline).

![](/AzureCostInsights.Marketplace/images/flow.png)
 
1. **Create the build pipeline**<br/>
This build pipeline is required to download and host your cost data.

    - Create a new empty build (not release) pipeline and select a (preferable empty) repository
    - Name the pipeline something like 'Cost Insights'
    - Add the 'Download Cost Data' task for each subscription, then end with the 'Publish Cost Data' task 
    - Depending on your Subscription Type (Pay as you Go, EA, CSP, etc.) you need to select the 'consumption' or the 'usage' API in the 'Download Cost Data' task. [More info here](https://github.com/keesschollaart81/AzureCostInsights.Marketplace/wiki/Usage-vs-Consumption-Api).
    - Your pipeline will look like this:
    ![](/AzureCostInsights.Marketplace/screenshots/buildpipeline.png)

2. **Queue the build** and wait for it to finish before continuing with step 3 <br/>
While waiting, You are encouraged you to read the following tips:
    - In the trigger's tab, disable the 'continuous' trigger and set a scheduled trigger, for example every night at 04:00 AM and make sure 'Only schedule builds if the source or pipeline has changed' is **un**checked
    - The build pipeline has, by default, a maximum duration of 60 minutes (see the 'options' tab), this might be to short depending on the size of your cost data. It takes ~10 minutes to download the costs for 100.000$
    - Observe the artifacts of the build, this is the data that will be used by the widget
    - Create only 1 cost pipeline, teams (within a project) can share it. Add multiple 'download cost data' task for each subscription

3. **Add the Widget to your Dashboard**<br/>
    - Go to your teams' dashboard and add the 'Azure Cost Insights' widget.
    ![](/AzureCostInsights.Marketplace/screenshots/addwidget.gif)
  
## Examples

[![](/AzureCostInsights.Marketplace/screenshots/screen2_thumb.png)](/AzureCostInsights.Marketplace/screenshots/screen2.png)

## One widget for free!

Although this widget is marked as free in this marketplace, be aware that only the first instance of this widget (within your tenant) is free. The price starts at 1.00 € per widget per month for smaller organizations. If you need more than 15 widgets (enterprise plan), please send an email to [info@azurecostinsights.com](mailto:info@azurecostinsights.com).

You can buy additional 'slots' by navigating to: 'Project Settings' (bottom left corner in Azure DevOps) > 'Extensions' > 'Azure Cost Insights'.

## Questions, bugs, feature requests, etc.

Please raise an issue in this GitHub Repository:
https://github.com/keesschollaart81/AzureCostInsights.Marketplace/issues

Send an email at [info@azurecostinsights.com](mailto:info@azurecostinsights.com).

I'm usually online in the [https://teamservices.club/](https://teamservices.club/) Slack Channel.

Tip: If you have problems with the Download/Publish task, set the 'system.debug' to true to get full debugging output / raw-artifacts.

## Supported configurations

- All Azure Subscription types (tested so far: EA, Pay as you Go, MSDN, Microsoft Internal), not tested yet but expected to work: CSP, Free trial, [retired offers](https://azure.microsoft.com/en-us/support/legal/offer-details/) 
- Azure DevOps (TFS/Azure DevOps Server: not yet, contact me if you want to help me test that)
- Tested with latest versions of Chrome, Edge, Firefox and Safari, Internet Explorer 11 seems to work but is not tested thoroughly. 
- All type of hosted Agents

## Privacy, Telemetry & Credit Card data

This extension will never send any of your cost data to any remote endpoint. So things like Azure Data (Subscription/Resource-Group/Tags), Cost data or identities/tokens never leave your Azure DevOps tenant! 

**Only the during preview period:** your Azure DevOps username (email) is included in the telemetry data. If unexpected errors show up in the logs, you might be contacted on why/how that happened. Preview ends ±feb 2019.

Some requests are made to https://license.prd.azurecostinsights.com to validate your license.

Some telemetry data is collected to make this a better product, checkout the details on [the Wiki](https://github.com/keesschollaart81/AzureCostInsights.Marketplace/wiki/Privacy,-Telemetry-&-Credit-Card-data).