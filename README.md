# DEPRECATION NOTICE
This repository is no longer active. Creation of new Datadog integrations should follow the instructions laid out in the [integration documentation](https://docs.datadoghq.com/developers/integrations/new_check_howto/?tab=configurationtemplate).

# Datadog Integration Tile Template

This repository is meant to help create tiles for Integrations which do *not* contain Python checks. Any Integrations which contain Python code - typically those that are run via the Agent - should use the [standard tooling][1] for generating tile templates.

## Steps

1. Download or fork the [DataDog/IntegrationTemplate][4] repository

2. Copy the `Integration` directory to `MyCheck`
    ```
    cp -r Integration MyCheck
    ```

3. Follow the [Final Touches][1] instructions for the following elements *only*:
    * [Add images and logos][2]
    * `manifest.json` and `metadata.csv` from [Metadata][3]

4. Edit `MyCheck/README.md` and provide the following sections:

    * **`## Overview`**: Let others know what they can expect to do with your Integration
    * **`## Setup`**: Information about how to install and configure your Integration
    * **`## Metrics`**: List of the metrics (if any)
    * **`## Events`**: List of events (if any)
    * **`## Service Checks`**: List of service checks (if any)

5. Commit your changes, push and submit a pull request

## Need help?

Our friendly, knowledgeable solution engineers are [here to help][5]!

[1]: https://docs.datadoghq.com/developers/integrations/new_check_howto/#final-touches
[2]: https://docs.datadoghq.com/developers/integrations/new_check_howto/#add-images-and-logos
[3]: https://docs.datadoghq.com/developers/integrations/new_check_howto/#metadata
[4]: https://github.com/DataDog/IntegrationTemplate/
[5]: https://docs.datadoghq.com/help/
