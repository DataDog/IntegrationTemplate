## Overview
**Required.**

The first thing in the Overview should be a representative image for the integration. Try to make it as interesting as possible.

The overview section is required and should be a paragraph or two with some bullets of what is interesting about this integration. For example, the following comes from the Docker integration.

Get metrics from Docker in real time to:

* Visualize your containers' performance.

![snapshot](https://raw.githubusercontent.com/DataDog/IntegrationTemplate/master/integration/images/snapshot.png)

* Correlate the performance of containers with the applications running inside.

There are three ways to setup the Docker integration: install the agent on the host, on a single priviledged container, and on each individual container.

## Setup

**Required**

This section should cover anything that you can configure in the Datadog interface or the agent configuration files. Anything that is required to setup the integration should be documented (along with screenshots).

**Note:** Please avoid linking to an external docs page or PDF file. Instead, copy the documentation here so it becomes easier for your users.

## Data Collected
### Metrics
See [metadata.csv](https://github.com/DataDog/integrations-extras/blob/master/YourAppName/metadata.csv) for a list of metrics provided by this integration.

**or**

The AwesomeApp integration does not provide any metrics at this time.

### Events

All AwesomeApp deployment events are sent to your [Datadog Event Stream](https://docs.datadoghq.com/graphing/event_stream/)

**or**

The AwesomeApp integration does not include any events at this time.

### Service Checks
List service checks that the integration provides here

**or**

The AwesomeApp integration does not include any service checks at this time.

## Troubleshooting
Need help? Contact [Datadog Support](http://docs.datadoghq.com/help/).

## Further Reading

Learn more about infrastructure monitoring and all our integrations on [our blog](https://www.datadoghq.com/blog/).
