# LaunchDarkly Integration

## Overview

Get metrics from LaunchDarkly service in real time to:
* Visualize and monitor LaunchDarkly states.
* Be notified about LaunchDarkly failovers and events.

## Setup

The LaunchDarkly check is **NOT** included in the [Datadog Agent](https://app.datadoghq.com/account/settings#agent) package.

### Configuration
To watch flag update events in DataDog, create a Zapier account so...

**In [Zapier](https://zapier.com/):**
1) Create a zap through Zapier
2) Create a Webhook
3) Catch a Hook 
4) Copy your URL!

**In [LaunchDarkly](https://launchdarkly.com/):**
1) Create a webhook through Integrations 
2) Name your webhook
3) Paste the url from Zapier into the url form
4) This resournce will allow all access to all feature flags in all projects in all environemnts:
                     ``` proj/*:env/*:flag/*```
5) Save this setting.

**In [Zapier](https://zapier.com/):**
1) For the action, create a webhook.
2) Create a POST request.
3) Add your data dog API key to the POST url (you can check the url in the datadog [docs](https://docs.datadoghq.com/api/?lang=bash#post-an-event)): 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;https://api.datadoghq.com/api/v1/events?api_key=<YOUR_API_KEY>
4) For the data, create two fields: text and title
5) For the text choose: 
    1) Member Email
    2) Title Verb
    3) Name
    4) Parent Name
6) For the title add: LaunchDarkly <Kind> update
7) Once you test this step, you should start seeing events in DataDog as you update your flag in the LaunchDarkly Feature Flag Dashboard

## Troubleshooting
Need help? Contact Datadog [Support](https://docs.datadoghq.com/help/)
