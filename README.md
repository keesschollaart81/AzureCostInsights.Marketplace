# Azure Cost Insights

Get in control over your Azure Costs! This Widget gives you insights in your teams' infrastructure spendings. Add the widget to your dashboard and detect anomolies much quicker. 

## Key Features

- Visualize cost data by Resouce Group, Resouce Type, Subscription or Tag
- Fully customizable: bar & line chart-types, stacked & non-stacked, any timespan
- Filter by subscription and then/or by the name of Resource Group, Resource Type or by the value of the selected Tag (using glob patterns)
- No external service, data stay's within your Azure DevOps tenant
- Leverages your Azure Service Connections for downloading your data
- 1 widget for free, additional widget-instances starting at 1$ per widget per month (in-app purchase)

## Getting started

![](/AzureCostInsights.Marketplace/images/flow.png)
 
1. **Create the build pipeline**<br/>
This build pipeline is required to download and host your cost data.

    - Create a new empty build (not release) pipeline and select a (preferable empty) repository
    - Name the pipeline something like 'Cost Insights'
    - Add the 'Download Cost Data' task for each subscription, then end with the 'Publish Cost Data' task 
    - Depending on your Subscription Type (Pay as you Go, EA, CSP, etc.) you need to select the 'consumption' or the 'usage' API in the 'Download Cost Data' task. [More info here](https://github.com/keesschollaart81/AzureCostInsights.Marketplace/wiki/Getting-Started#subscription-types).
    - Your pipeline will look like this:
    ![](/AzureCostInsights.Marketplace/screenshots/buildpipeline.png)

2. **Queue the build** and wait for it to finish before continuing with step 3
    - While waiting, I really encourage you to check the tips below

3. **Add the Widget to your Dashboard**<br/>
    - Go to your teams' dashboard and add the 'Azure Cost Insights' widget.
    ![](/AzureCostInsights.Marketplace/screenshots/addwidget.gif)
  
## Tips

- In the trigger's tab, disable the 'continuous' trigger and set a scheduled trigger, for example every night at 04:00 AM
- When the costs of the added subscriptions are 'high': extend the maximum duration of your build in the 'options' tab (±10 minutes per 100.000 $)
- Observe the artifacts of the build, this is the data that will be used by the widget
- Create only 1 cost pipeline, teams (within a project) can share it. Add multiple 'download cost data' task for each subscription

## Examples

[![](/AzureCostInsights.Marketplace/screenshots/screen2_thumb.png)](/AzureCostInsights.Marketplace/screenshots/screen2.png)

## One widget for free!

Although this widget is marked as free in this marketplace, be aware that only the first instance of this widget (within your tenant) is free. The price starts at 1.00 € per widget per month. 

You can buy additional 'slots' by going to: 'Project Settings' (bottom left corner in Azure DevOps) > 'Extensions' > 'Azure Cost Insights'.

## Questions, bugs, feature requests, etc.

Please raise an issue in this GitHub Repository:
https://github.com/keesschollaart81/AzureCostInsights.Marketplace/issues

If you want to drop me an email, use [this form](https://www.emailmeform.com/builder/form/6cNG0B3bIfEp232ftoKR2zO7).

I'm usually online in the [https://teamservices.club/](https://teamservices.club/) Slack Channel.

## Things I have to do before Prod

- Detailed getting started
V Move the Marketplace stuff out of the code repo
- Parallelize the download
- Link 'Why'
- Public Dashboard
- Video
- Examples
- Explain the pricing
- Setup prod env.
- Test TFS
- Test different browsers
V Test different build hosts
V Refactor License backend
- Remove this list