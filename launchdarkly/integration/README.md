# LaunchDarkly Integration

## Overview

This integration tracks metrics from [LaunchDarkly's relay proxy](https://docs.launchdarkly.com/docs/the-relay-proxy), such as number of proxied stream connections and proxied API route requests.

## Setup

The LaunchDarkly check is **NOT** included in the [Datadog Agent](https://app.datadoghq.com/account/settings#agent) package.

### Configuration

After you've configured the [relay proxy](https://github.com/launchdarkly/ld-relay#quick-setup), add the following section to your LaunchDarkly relay instance's `ld-relay.conf` file:

```
[datadog]
enabled=true
statsAddr="YOUR_STATS_ADDRESS"
```

## Data Collected

### Metrics

The relay collects metrics on the number of proxied stream connections and proxied API route requests. See [relay documentation](https://github.com/launchdarkly/ld-relay#exporting-metrics-and-traces) for more information.

## Troubleshooting

Need help? Contact Datadog [Support](https://docs.datadoghq.com/help/).