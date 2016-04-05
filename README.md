# Datadog Integration Template

## Steps
To add a new tile to Datadog integration page, please follow the steps below

1. Fork this repo
2. Copy Integration directory to YourAppName (cp -r Integration YourAppName)
3. Create your logo files on a white background canvas in 3 different sizes, 200x128px, 128x128px and 120x60px. Add images to your Images directory.
4. (Optional) If you want user to see a default dashboard, please signup for datadog and create a screenboard

  > Goto https://app.datadoghq.com/dash/list and click on "Create dashboard" and select "ScreenBoard". Once you are done editing, please save and add the link to mainfest.json file.

  > The link will look like this: https://app.datadoghq.com/screen/0000/boardname

5. Edit YourAppName/description.html to provide your application's information
6. Edit YourAppName/metrics.csv to provide metrics you are collecting. See [metrics](#Metrics) for more detail and example
6. Commit, push and submit pull request

If you want to reference images, please add images into "YourAppName/Images/" folder and use the following example to insert image.

```
<img src="${img_path("yourapp-snapshot.png")}" />
```

## Metrics
There are columns in metrics.csv file, here is a description and acceptable value for each
* **metric_name:** This is the name of metric. You should name this yourappname.metric_name.
* **metric_type:** This can be any one of `{'gauge', 'counter', 'rate', 'count'}`. See more [here](http://docs.datadoghq.com/guides/metrics/#counters).
* **interval:** Leave blank
* **unit_name:** The unit for your metric. For example, if you put `connections` here, your metric will be shown like " 50 connections"
* **per_unit_name:** The base unit for your metric. For example, if you put `second` here, your metric will be shown like "50 connections/second"
* **description:** This is a text description of your metric
* **orientation:** This can be -1, 0 or 1. For example, `system.cpu.user`: the lower it is, the better it is. Its orientation should be -1. On the contrary `system.cpu.idle`: the higher it is, the better it is. Its orientation should be 1. 0 means no values are better or worse.
* **integration:** This is the name of your integraiton. In this case it should be `yourappname`, same to what you use in your metric namespace
* **short_name:** A short name for your metric. For example, short name for `postgresql` is `pg`


## Important notices
1. Do not try to add new css rules, the preview.css is only for preview purpose, all the rules within will be ignored


Send e-mail to ilan@datadoghq.com if you run into any problems.
