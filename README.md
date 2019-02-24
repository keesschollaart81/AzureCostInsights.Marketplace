# Azure Cost Insights

It's easy to get your Azure Costs out of control. _Wouldn't it be great to get insights of your infrastructure spending in your daily routine?_

Costs are a concern of everyone, developers, product owners and operations.
They come together in Azure DevOps, so why not show these insights there?

Azure Cost Insights is a widget that you can put on your Azure DevOps Dashboard.

[![Azure Cost Insights YouTube video](/AzureCostInsights.Marketplace/images/play_thumb.png)](https://www.youtube.com/watch?v=tyIzQWP5dMw)


## Key Features

- **Save money!** Detect yesterday's cost-spike today, instead of at the end of the month
- **Fully customizable**. Bar & line chart-types, pivot by Resouce Group, Resouce Type, Subscription, Tag, Product, Environment, Regio, etc...

![](/AzureCostInsights.Marketplace/screenshots/pivots.png)

- **Secure**, your data never leaves Azure DevOps, no external service, data can be scoped/filtered leveraging the build-in service-connections of Azure Pipelines
- **Advanced**, works with... combined subscriptions, all Subscription types (except CSP), dark-theme, tag on Resource Groups, big enterprise customers

![](/AzureCostInsights.Marketplace/screenshots/config.png)

## Getting started

You might figure it out but **save some time** and read the **[Getting Started](https://github.com/keesschollaart81/AzureCostInsights.Marketplace/wiki/Getting-started)** because it has some **useful tips**!  For example: you need to create an Azure Pipeline for the widget to work which is going to download and host your cost-data, used by the widget. 

If you wonder why this widget needs an Azure Pipeline, [read the 4 good reasons for 'why the need of a pipeline' here](https://github.com/keesschollaart81/AzureCostInsights.Marketplace/wiki/Why-the-need-of-a-Pipeline).

## Pricing

Everyone can use this widget, the first widget is free! If you're exicted about the product you can try out the basic, pro and enterprise plan one month for free.

![](/AzureCostInsights.Marketplace/images/plans.png)

Some explanations:  
* Widgets: the total number of widgets in the Azure DevOps organisation
* Subscriptions: the data of how many Azure Subscriptions can be combined in a single widget
* Filtering: filter the available dataset for widgets / users. This is usefull when Azure Subscriptions are cross team/org and not everyone is suppose to see everything
* On-Prem/Server: get access the a special (non-public) version of this extension that can be installed on TFS / Azure DevOps Server
* Offline: get access the a special (non-public) version of this extension that does not track telemetry and does not require the license server
 
You can upgrade your 'free' plan by navigating to: 'Project Settings' (bottom left corner in Azure DevOps) > 'Extensions' > 'Azure Cost Insights'.

## Release notes / Roadmap

Checkout the full release history at [GitHub Releases](https://github.com/keesschollaart81/AzureCostInsights.Marketplace/releases)

**1.0 - 16-01-2019**: Initial release

**1.5 - 26-02-2019**

- Support for MSI identities
- Support for Dark Theme
- Updated tooltip behaviour for big datasets
- Shift+click on Legend inverses filter behaviour
- 1 month trial mode for basic/pro/enterprise plans
- Filter/download dataset during download (pro/enterprise plans)
- Support for Azure DevOps Server / TFS (pro/enterprise plans)
- Offline mode (enterprise plan)

**1.8 - ± April 2019**

Checkout the upcoming features (or add your own request) for this [upcoming milestone on GitHub](https://github.com/keesschollaart81/AzureCostInsights.Marketplace/milestone/2)

## Questions, bugs, feature requests, etc.

Please raise an issue in this GitHub Repository:
https://github.com/keesschollaart81/AzureCostInsights.Marketplace/issues

Send an email at [info@azurecostinsights.com](mailto:info@azurecostinsights.com).

I'm usually online in the [https://teamservices.club/](https://teamservices.club/) Slack Channel.

Tip: If you have problems with the Download/Publish task, set the 'system.debug' to true to get full debugging output / raw-artifacts.

## What is (not) supported

Not supported:
- CSP Subscriptions

Supported:

- Tested with latest versions of Chrome, Edge, Firefox and Safari, Internet Explorer 11 seems to work but is not tested thoroughly. 
- All type of hosted Agents (Windows/Linux/Private)
- Service Connection based on 'Service Principal' and based on 'Managed Service Identity (MSI)'
- All Azure Subscription types (tested so far: EA, Pay as you Go, MSDN, Microsoft Internal), not tested yet but expected to work: [all the other offer types](https://azure.microsoft.com/en-us/support/legal/offer-details/) except CSP  
- Azure DevOps Server / TFS (only for pro/enterprise plans)

## Privacy, Telemetry & Credit Card data

This extension will never send any of your cost data to any remote endpoint.

Sensitive Azure Data (like names of Subscription/Resource-Group/Tags), your Cost data or identities/tokens never leave your Azure DevOps tenant! 

Customers with the enterprise plan can opt-out for telemetry & license api ('offline' mode) please contact me.

**Only the during preview period:** your Azure DevOps username (email) is included in the telemetry data. If unexpected errors show up in the logs, you might be contacted on why/how that happened. Preview ends ±feb 2019.

Some requests are made to https://license.prd.azurecostinsights.com to validate your license.

Some telemetry data is collected to make this a better product, checkout the details on [the Wiki](https://github.com/keesschollaart81/AzureCostInsights.Marketplace/wiki/Privacy,-Telemetry-&-Credit-Card-data).

The payment is processed via stripe.com and with AzureCostInsights.com (not with/via Microsoft).