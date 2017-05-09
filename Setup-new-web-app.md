Setting up and configuring a new web app to run a custom server.js
=======================================================


1. Using your new ftp credentials log into your navigate to the site folder and then the wwwroot folder.  This is where you public site
  lives. Once here at least for initial setup we can safely delete all files except for the following:

     * a.server.js
     * c.package.json
     * d.the public folder (however the example.xt can be deleted)


2.  Edit the package.json file to reflect your application and if you want to change the name of your server.js file make sure to update our start
  script here.  We can also update the version of node we are using as well
3.  Create a process.json file.  This file needs to include some information and as is follows:


          "name"        : "worker",
          "script"      : "./server",
          "instances"   : 1,
          "merge_logs"  : true,
          "log_date_format" : "YYYY-MM-DD HH:mm Z",
          "watch": true,
          "watch_options": {
            "followSymlinks": true,
            "usePolling"   : true,
            "interval"    : 5
          }
 
 where "script" also reflects your server.js our whatever entry point name you want it to be. If you change the server.js name you should also edit this in your web.config file. 
 
 Your server is now setup to run a custom implemented server.js file. 
