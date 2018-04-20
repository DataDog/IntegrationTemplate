# Datadog Integration Template

Adding an integration tile on to Datadog is easy! Just follow the steps below to use the template from this repo and submit a pull request to get someone from the integrations team to review.

## Steps

1. Fork this repo

2. Copy the `Integration` directory to `YourAppName`

  `cp -r Integration YourAppName`

3. Create your logo files on a white background canvas, exported to the PNG format, in 3 different sizes: 200x128px, 128x128px and 120x60px. Add the logo images to the  `YourAppName/logos/` directory. The file names should be as follows for the different sizes:

    - **200x128px:** saas_logos-bot.png
    - **128x128px:** avatars-bot.png
    - **120x60px:** saas_logos-small.png


5. Edit `YourAppName/README.md` with your application's information

  Your README file should provide the following sections:

  - **Overview**: Let others know what they can expect to do with your integration
  - **Setup**: Provide information about how to install and configure your integration
  - **Metrics**: Include a list of the metrics if your integration provides any
  - **Events**: Include a list of events if your integration provides any
  - **Service Checks**: Include a list of service checks if your integration provides any

  If you want to reference images, please add images into `YourAppName/images/` folder and use the following example to insert image.

  ```
  ![snapshot](https://raw.githubusercontent.com/DataDog/integrations-extras/master/YourAppName/images/snapshot.png)
  ```
  **NOTE:** Relative URLs for the images will **not** work. Copy the full URL above and replace `YourAppName` with the correct value. Once your PR has been approved and merged to the master branch, the image will display correctly.

6. Edit `YourAppName/manifest.json` with your app's details

  This JSON file provides metadata about your integration and should include:

  - **name**: The name of your integration (lowercase)
  - **manifest_version**: The version of this manifest file
  - **maintainer**: Provide a valid email address where you can be contacted regarding this integration
  - **display_name**: The name of your integration
  - **short_description**: Provide a description (under 150 characters). This is what populates the hover-over content on the tile
  - **metric_prefix**: The root namespace for your metrics, usually the same as the `name` key
  - **metric_to_check**: The metric to check if the integration is working or not
  - **creates_events**: Boolean true/false, depending on whether your integration sends events or not
  - **public_title**: Datadog-YourAppName Integration
  - **type:** Either `crawler` or `check`, if your integration is an agent check
  - **doc_link**: Link to the documentation page for your integration once it eventually gets published
  - **is_public**: **true** (don't change this value)
  - **has_logo**: **true** (don't change this value)
  - **categories**: Categories to sort your integration, [current categories can be found on integrations dedicated documentation page](https://docs.datadoghq.com/integrations/)

6. Edit `YourAppName/metadata.csv` to provide metrics you are collecting. Refer to the [this section](https://docs.datadoghq.com/developers/integrations/integration_sdk/#metadata-csv) for further details

6. Commit your changes, push and submit a pull request

Send an e-mail to dhruv.sahni@datadoghq.com if you have any questions.
