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
 
1. Create the build pipeline
2. Queue the build and wait for it to succeed
3. Add the Widget to your Dashboard

Altough it's not rocket science, please take a look in the **['Getting Started'](https://github.com/keesschollaart81/AzureCostInsights.Marketplace/wiki/Getting-started)** because it has some useful tips! 
  
## Examples

[![](/AzureCostInsights.Marketplace/screenshots/screen2_thumb.png)](/AzureCostInsights.Marketplace/screenshots/screen2.png)

## Pricing

![](/AzureCostInsights.Marketplace/images/plans.png)

* Widgets: the total number of widgets active in the Azure DevOps organisation
* Subscriptions: the data of how many Azure Subscriptions can be combined in a single widget
* Filtering: filter the available dataset for widgets / users. This is usefull when Azure Subscriptions are cross team/org and not everyone is suppose to see everything
* On-Prem/Server: get access the a special (non-public) version of this extension that can be installed on TFS / Azure DevOps Server
* Offline: get access the a special (non-public) version of this extension that does not track telemetry and does not require the license server
 
You can upgrade your 'free' plan by navigating to: 'Project Settings' (bottom left corner in Azure DevOps) > 'Extensions' > 'Azure Cost Insights'.

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

Of you want a fully self contained/isolated install with 0 external dependencies/requests, that is possible, please contact me (only paid customers).

**Only the during preview period:** your Azure DevOps username (email) is included in the telemetry data. If unexpected errors show up in the logs, you might be contacted on why/how that happened. Preview ends ±feb 2019.

Some requests are made to https://license.prd.azurecostinsights.com to validate your license.

Some telemetry data is collected to make this a better product, checkout the details on [the Wiki](https://github.com/keesschollaart81/AzureCostInsights.Marketplace/wiki/Privacy,-Telemetry-&-Credit-Card-data).