# Agent Check: Aqua

## Overview

This check monitors [Aqua][1].  
Collect data from Aqua Security, included in the Datadog Agent package, to track performance data and receive alerts concerning image vulnerability as well as irregularities in your runtime environment.


The Aqua check will alert the user if total high-severity vulnerability is reached, or if a container is running inside a host not registered by Aqua.  Aqua will also send data alerts regarding blocked events in runtime, and it is possible to trigger a webhook to scale infrastructure if more Aqua scanners are required.

## Setup

### Installation

The Aqua check is included in the [Datadog Agent][2] package, so you do not
need to install anything else on your server.

### Configuration

1. Edit the `aqua.d/conf.yaml` file, in the `conf.d/` folder at the root of your
   Agent's configuration directory to start collecting your aqua performance data.
   See the [sample aqua.d/conf.yaml][2] for all available configuration options.

2. [Restart the Agent][3]

### Validation

[Run the Agent's `status` subcommand][4] and look for `aqua` under the Checks section.

## Data Collected

### Metrics

aqua.images  
aqua.vulnerabilities  
aqua.running_containers  
aqua.audit.access  
aqua.scan_queue  
aqua.enforcers  

### Service Checks

Aqua sends one service check named `aqua.can_connect`

### Events

Aqua does not include any events.

## Troubleshooting

Need help? Contact [Datadog Support][5].

[1]: https://www.aquasec.com/
[2]: https://github.com/DataDog/integrations-core/blob/master/aqua/datadog_checks/aqua/data/conf.yaml.example
[3]: https://docs.datadoghq.com/agent/faq/agent-commands/#start-stop-restart-the-agent
[4]: https://docs.datadoghq.com/agent/faq/agent-commands/#agent-status-and-information
[5]: https://docs.datadoghq.com/help/
