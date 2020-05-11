# R shiny app data storage

I have been recently working in `RMarkdown` without moving between many other text languages (such as word or others). Over the past 6months, `RMarkdown` has developed rapidly in `conjuction` with Shiny. 

One hard thing about shiny is data storage. These are my notes working through Deans shiny tutorial on `persistant data storage` [here](https://deanattali.com/blog/shiny-persistent-data-storage/). And this amazing shiny app below, all done by Dean as far as I can tell.

**INSERT IFRAME HERE....https://daattali.com/shiny/persistent-data-storage/**



### Remote vs. Local storage

> Before diving into the different storage methods, one important distinction to understand is *local storage* vs *remote storage*.

> Local storage means saving a file on the same machine that is running the Shiny application. Functions like `write.csv()`, `write.table()`, and `saveRDS()` implement local storage because they will save a file on the machine running the app. Local storage is generally faster than remote storage, but it should only be used if you always have access to the machine that saves the files.

> Remote storage means saving data on another server, usually a reliable hosted server such as Dropbox, Amazon, or a hosted database. One big advantage of using hosted remote storage solutions is that they are much more reliable and can generally be more trusted to keep your data alive and not corrupted.

> When going through the different storage type options below, keep in mind that if your Shiny app is hosted on shinyapps.io, you will have to use a remote storage method for the time being. RStudio plans to implement persistent storage on shinyapps.io soon. In the meantime, using local storage is only an option if you’re hosting your own [Shiny Server](http://www.rstudio.com/products/shiny/shiny-server/). If you want to host your own server, [here is a guide](https://deanattali.com/2015/05/09/setup-rstudio-shiny-server-digital-ocean) that describes in detail how to set up your own Shiny Server.

# Persistent data storage methods

Using the above Shiny app, we can store and retrieve responses in many different ways. Here we will go through seven ways to achieve data persistence that can be easily integrated into Shiny apps. For each method, we will explain the method and provide a version of `saveData()` and `loadData()` that implements the method. To use a method as the storage type in the example app, run the app with the appropriate version of `saveData()` and `loadData()`.

As a reminder, you can see all the seven different storage types being used, along with the exact code used, [in this live Shiny app](https://daattali.com/shiny/persistent-data-storage/).

#### Summary

Here is a summary of the different storage types we will learn to use.

| Method            | Data type            | Local storage | Remote storage | R package    | Example code... |
| :---------------- | :------------------- | :-----------: | :------------: | :----------- | --------------- |
| Local file system | Arbitrary data       |      YES      |                | -            |                 |
| Dropbox           | Arbitrary data       |               |      YES       | rdrop2       |                 |
| Amazon S3         | Arbitrary data       |               |      YES       | aws.s3       |                 |
| SQLite            | Structured data      |      YES      |                | RSQLite      |                 |
| MySQL             | Structured data      |      YES      |      YES       | RMySQL       |                 |
| Google Sheets     | Structured data      |               |      YES       | googlesheets |                 |
| MongoDB           | Semi-structured data |      YES      |      YES       | mongolite    |                 |



### I have used `dropbox` for now (so it is private...)

Code and running rules coming....