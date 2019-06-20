## Overview

Connect Datadog to Citrix ITM Openmix to:
* Manage traffic using the Datadog monitors to measure the health of routing endpoints
* Trigger immediate traffic changes based on Datadog alerts

![DecisionReport](https://raw.githubusercontent.com/sudhirpatamsetti/CitrixITM/master/images/DecisionReport.png)

## Setup

### Description

The Datadog Fusion integration consists of two parts: 
* A Fusion feed to poll the Datadog monitor of interest, and 
* A Webhook to accept Datadog alerts

### Data Feed Format
```
  {
    "date": "1514928998000",
    "event_id": "4205479851843276922",
    "last_updated": "1514928998000",
    "monitor_id": "3617482",
    "status": "OK",
    "title": "[Recovered on {host:...,url:...}] Fusion Integration Alert"
  }
```
When the monitor is triggering an alert
```
  {
    "date": "1514928760000",
    "event_id": "4205475852893180000",
    "last_updated": "1514928760000",
    "monitor_id": "3617482",
    "status": "Alert",
    "title": "[Triggered on {host:...,url:...}] Fusion Integration Alert"}
  }
  ```
**Note**: The word “Recovered” in the title indicates the that the status is OK, and the word “Triggered” indicates that the monitor is giving out an alert

### Reconciliation Steps
				
Prerequisites: Datadog monitor of interest is already set up
					
* Go to the Datadog portal			
* Go to Monitors on the left navigation panel				
* Find the alert that you set up and click on it					
* Check if the status is OK and if matches the status you see in Fusion

![Fusionintegrationalert](https://raw.githubusercontent.com/sudhirpatamsetti/CitrixITM/master/images/Fusionintegrationalert.png)

### Server Configuration
	
**Configure Webhook**
		
Navigate to Integrations and click on the Webhooks tile. [This page ](https://app.datadoghq.com/account/settings#integrations/webhooks) walks you through the Datadog Webhook integration.
At the bottom of the Webhooks dialog, Add a new Webhook.  Each row is a new Webhook that can be used to alert a different Fusion feed.  There are two required fields:

* Name: Can be any arbitrary name	
* URL: This is the URL from the Portal Fusion Data Feed when you configured Datadog. Leave Custom Payload and Headers blank i.e. make sure the check boxes are not clicked

A single Webhook looks like this:

![Webhook](https://raw.githubusercontent.com/sudhirpatamsetti/CitrixITM/master/images/Webhook.png)

### Setup in Fusion
				
You can access Fusion Data Feeds from the left navigation pane, under Openmix. For initial steps please refer to the Fusion user guide.
When you get to the service-specific configuration dialog box, enter the following:	

* Name: The name given to the data feed. This will default to "Service - Platform Name" if not specified
* Run Every: The frequency with which the data feed is updated from the service	
* Platform: The Platform that is associated with the data feed
* API Key: Available in the Datadog portal
* Application Key: Available in the Datadog portal
  * API and Application keys are in Datadog. Both keys are required to setup a Datadog Fusion feed.  To view the keys log into  Datadog and navigate to: [Integrations -> APIs](https://app.datadoghq.com/account/settings#api)
* Monitor ID:  Monitor ID is the specific monitor you want to poll. 
  * To find the monitor_id in Datadog, navigate to: [Monitors -> manage monitors](https://app.datadoghq.com/monitors/manage)
  * Search for the monitor you'd like to poll. monitor_id is in the browser address bar:   https://app.datadoghq.com/monitors#2511486?group=all&live=4h

![Datafeed](https://raw.githubusercontent.com/sudhirpatamsetti/CitrixITM/master/images/Datafeed.png)

Click Next to complete setting up the Fusion feed. Once the Fusion feed set up is complete, copy the URL provided. This URL will be used to configure the Webhook

![Datafeed1](https://raw.githubusercontent.com/sudhirpatamsetti/CitrixITM/master/images/Datafeed1.png)

Once the Fusion Datadog installation is complete, it will be listed on the Fusion data feeds home page with a green status and monitoring metrics in the log history

To edit a Fusion data feed, click on the data feed in the list and then click the Edit button. Once you have changed the configuration, click Save. This will bring you back to the data feed list with your changes saved and applied to the data feed.

## Data Collected

### Metrics

The Citrix ITM integration does not provide any metrics at this time.

### Events

The Citrix ITM integration does not include any events at this time.

### Service Checks

The Citrix ITM integration does not include any service checks at this time.

## Troubleshooting

Need help? Contact [Datadog Support](http://docs.datadoghq.com/help/).

## Further Reading

Learn more about infrastructure monitoring and all our integrations on [our blog](https://www.datadoghq.com/blog/).
