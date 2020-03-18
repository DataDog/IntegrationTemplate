## Overview
Monitoring solutions like DataDog provide companies with deep visibility and insights to their IT infrastructure environments.  These tools also provide notification capabilities to let administrators know when issues arise within the environment.  Rundeck can further enhance that notification with automated workflow capabilities to help diagnose, and optionally remediate the issue.  Below are a few example use cases:
- If a Windows/Linux service is down, attempt to restart it.
- If NTP sync is off restart the NTP service on that machine.
- Cleanup logs and other file waste when disk space becomes full.
- Restart services in response to hung work queues.
- Provision capacity in response to high utilization.

Use the instructions below to configure your first DataDog/Rundeck integration.

## Setup

### Preparations
Prepare at least 1 Rundeck Job that you’d like to trigger using a DataDog Alert.

### Rundeck Setup
1. In your Rundeck Project click the **Webhooks** navigation option.
2. Click **Add**.
3. Give the Webhook a Name.  (e.g. *DataDog-Restart Service*)
4. Click the **Choose Webhook Plugin** button and select **Run Job***
5. Select the job you’d like to run when this webhook is triggered.
6. [optional] On the Options line enter the following text:
`-raw ${raw} -event_type ${data.event_type}`
(This will make the full DataDog payload available as part of the job input options.)
7. Click **Create Webhook**.  The URL field will be automatically populated after the webhook is created.
![rundeck-setup][1]

### DataDog Setup
1. Open DataDog and Click Integrations | Integrations.
2. Search for “webhooks”.

![search-dd][2]


3. Click on the webhooks entry shown above.  It will open the configuration window.

![webhooks-config][3]

4. Click the New button and fill out the form:
  - Give the Webhook a Name (a)
  - Paste the URL from your Rundeck Webhook in the URL line. [Step 7 in section above] (b)
  - Click Save. (c)

![webhook-fill][4]

This Integration can be added to any alert notification in DataDog by adding the recipient of `@webhook-Rundeck_Restart_Service` _(name will vary based on what you named the webhook in step 4a)._ When the monitor triggers an alert the webhook will run the associated job.

_*Other plugins could be used as well (e.g. Advanced Run Job) depending on your use case._


## Data Collected

The Rundeck integration does not provide any metrics at this time.

### Events

The Rundeck integration does not include any events at this time.

### Service Checks

The Rundeck integration does not include any service checks at this time.

## Troubleshooting
Need help? Contact [Rundeck Support](https://support.rundeck.com).

## Further Reading

Learn more about automating your runbooks to reduce incident time [on our website](https://www.rundeck.com/).

[1]: ./assets/images/rundeck-setup.png
[2]: ./assets/images/dd-search.png
[3]: ./assets/images/webhooks-config.png
[4]: ./assets/images/webhook-fill.png
