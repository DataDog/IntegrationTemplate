# Datadog Integration Template

## Steps
To add a new tile to Datadog integration page, please follow the steps below

1. Fork this repo
2. Copy Integration directory to YourAppName (cp -r Integration YourAppName)
3. Create your logo files in 3 different sizes, 200x128px, 128x128px and 125x80px. Add images to your Images directory.
4. (Optional) If you want user to see a default dashboard, please signup for datadog and create a screenboard
> Goto https://app.datadoghq.com/dash/list and click on "Create dashboard" and select "ScreenBoard". Once you are done editing, please save and add the link to mainfest.json file.
> The link will look like this: https://app.datadoghq.com/screen/0000/boardname 
5. Edit YourAppName/description.html to provide your application's information
6. Commit, push and submit pull request

If you want to reference images, please add images into "YourAppName/Images/" folder and use the following example to insert image.
```
<img src="${img_path(" yourapp-snapshot.png ")}" />
```

## Important notices
1. Do not try to add new css rules, the preview.css is only for preview purpose, all the rules within will be ignored 


Send e-mail to will@datadoghq.com if you run into any problems.