# NextRainCloud #

A [Nextcloud](https://github.com/nextcloud/server) styled theme for 
[RainLoop](https://github.com/RainLoop/rainloop-webmail). 

The theme is optimized for RainLoop v1.11.1. 
If a new version is released, we try to update as soon as possible.

### Installation ###
There are two ways how to install this theme.

**How to find your RainLoop themes folder**  
For both of these ways, it's important that you know, 
where are the files of your RainLoop instance are located.
So here's a little guide how to find these files:

Most web servers store their files within the `/var/www` directory.
So switch into it and search for your RainLoop directory.
If you are using Nextcloud (and the RainLoop plugin),
go to your Nextcloud installation and into the `apps/rainloop` 
directory.

Now you should be within the RainLoop folder, 
so we are going to switch to the themes folder.
To do this just navigate to the following directory,
but replace `$VERSION$` with your RainLoop version:
```
app/rainloop/v/$VERSION$/themes
```
For example the version can be `1.11.1`, so the path would be:
```
app/rainloop/v/1.11.1/themes
```

**Way 1:**  
This way is recommend for servers with terminal access and Git installed.

* Step 1:  
  Go into your terminal and switch to the user who runs 
  the web server (Apache, Nginx) or php-fpm service.
  This user is in the most cases `www-data`.
* Step 2:  
  Switch into your **RainLoop theme folder**
* Step 3:  
  Run following command: `git clone https://github.com/LukWebsForge/NextRainCloud.git`.
  This will clone the theme into the themes folder.
* Step 4:  
  Congratulations, you installed the theme. 
  If you want to update the theme, just switch into 
  the theme's directory and run `git pull && git reset --hard`.
   
**Way 2:**  
This way is recommend for web servers, which you can only access using FTP.

* Step 1:  
  Download a [copy of the master branch](https://github.com/LukWebsForge/NextRainCloud/archive/master.zip).
* Step 2:  
  Unzip the copy and rename the folder `NextRainCloud-master` into `NextRainCloud`.  
  This is just optionally, but if you don't do it the name of the theme 
  will be displayed as NextRainCloud-master and this may be a little bit confusing. 
* Step 3:  
  Connect to your web server using FTP (or SFTP, FTPS)
  and switch to the **RainLoop theme folder**.
* Step 4:  
  Upload the whole folder (including the folder itself) into the theme directory.
* Step 5:  
  Congratulations, you installed the theme. 
  If you want to update the theme, just delete the folder 
  of the theme on the server and repeat all steps.
  
### Contributing ###
Issues and pull requests are welcome. 
Feel free to do anything you want.

If you want to help developing the theme,
I recommend you to setup a development environment.
 
**Setup a development environment**
* Step 1:  
  Clone and [install RainLoop](https://github.com/RainLoop/rainloop-webmail/blob/master/CONTRIBUTING.md) 
* Step 2:  
  Go to the folder `rainloop/v/0.0.0/themes`
* Step 3:  
  Fork this repository and copy the clone url of your fork.
* Step 4:  
  Add a git submodule using `git submodule add $CLONE-URL$`. 
  Replace `$CLONE-URL$` with the clone url for your fork.
  A clone url may be url like this `git@github.com:LukWebsForge/NextRainCloud.git`.
* Step 5:  
  Disable the caches of RainLoop.
  To do this go to the `data/_data_/_default_/` directory.
  Then edit the `configs/application.ini` file and change following values:
```ini
[cache]
enable = Off
http_expires = 1
[labs]
use_app_debug_css = On
```
  At the end delete the `cache` folder inside the `_default` directory.
  Now everything should change upon reload.