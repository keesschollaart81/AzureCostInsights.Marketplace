# Azure Cost Insights

It's easy to get your Azure Costs out of control. _Wouldn't it be great to get insights of your infrastructure spending in your daily routine?_

Costs are a concern of everyone, developers, product owners and operations.
They come together in Azure DevOps, so why not show these insights there?

Azure Cost Insights is a widget that you can put on your Azure DevOps Dashboard.

This widget is built with the belief that cost insights need to be scoped to your spendings. 

[![Azure Cost Insights YouTube video](/AzureCostInsights.Marketplace/images/play_thumb.png)](https://www.youtube.com/watch?v=tyIzQWP5dMw)

## Key Features

- Learn about the costs per product, per environment, per regio, etc....
- Pivot by Resouce Group, Resouce Type, Subscription or Tag
- Detect sudden spikes in a day, instead of at the end of the month
- Fully customizable: bar & line chart-types, stacked & non-stacked, any timespan
- Filter by subscription and then/or by the name of Resource Group, Resource Type or by the value of the selected Tag (using glob patterns)
- All your cost data stay's within your Azure DevOps tenant, no external service dependency 
- Leverages your existing Azure Service Connections integration for downloading your data
- All Azure Subscription (offer) types are supported (like EA, PayG, MSDN, etc.) except CSP
- 1 widget for free, additional widget-instances starting at 1$ per widget per month (in-app purchase)

## Getting started

You need to create an Azure Pipeline for the widget to work. This pipeline is going to download and host your cost-data, used by the widget. [Read the 4 good reasons for 'why the need of a pipeline' here](https://github.com/keesschollaart81/AzureCostInsights.Marketplace/wiki/Why-the-need-of-a-Pipeline).

![](/AzureCostInsights.Marketplace/images/flow.png)
 
1. **Create the build pipeline**<br/>
If you prefer to have your pipeline as (YAML) code, [this is supported and documented over here](https://github.com/keesschollaart81/AzureCostInsights.Marketplace/wiki/YAML-Pipeline).

    - Create a new empty build (not release) pipeline and select a (preferable empty) repository
    - Name the pipeline something like 'Cost Insights'
    - Add the 'Download Cost Data' task for each subscription, then end with the 'Publish Cost Data' task 
    - Depending on your Subscription Type (Pay as you Go, EA, CSP, etc.) you need to select the 'consumption' or the 'usage' API in the 'Download Cost Data' task. [More info here](https://github.com/keesschollaart81/AzureCostInsights.Marketplace/wiki/Usage-vs-Consumption-Api).
    - Your pipeline will look like this:
    ![](/AzureCostInsights.Marketplace/screenshots/buildpipeline.png)

2. **Queue the build** and wait for it to finish before continuing with step 3 <br/>
While waiting, you are encouraged you to read the following tips:
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

## What is supported

Not supported:
- CSP Subscriptions

Supported:

- All Azure Subscription types (tested so far: EA, Pay as you Go, MSDN, Microsoft Internal), not tested yet but expected to work [all the other offer types except CSP](https://azure.microsoft.com/en-us/support/legal/offer-details/) 
- Azure DevOps (TFS/Azure DevOps Server: not yet, contact me if you want to help me test that)
- Tested with latest versions of Chrome, Edge, Firefox and Safari, Internet Explorer 11 seems to work but is not tested thoroughly. 
- All type of hosted Agents

## Privacy, Telemetry & Credit Card data

This extension will never send any of your cost data to any remote endpoint.

Sensitive Azure Data (like names of Subscription/Resource-Group/Tags), your Cost data or identities/tokens never leave your Azure DevOps tenant! 

**Only the during preview period:** your Azure DevOps username (email) is included in the telemetry data. If unexpected errors show up in the logs, you might be contacted on why/how that happened. Preview ends ±feb 2019.

Some requests are made to https://license.prd.azurecostinsights.com to validate your license.

Some telemetry data is collected to make this a better product, checkout the details on [the Wiki](https://github.com/keesschollaart81/AzureCostInsights.Marketplace/wiki/Privacy,-Telemetry-&-Credit-Card-data).