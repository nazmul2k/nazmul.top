---
title: "How to Fix Uploaded File Exceeds the Upload Max Filesize in Wordpress"
date: 2025-02-09T11:39:53+06:00
draft: false
tags: ['cpanel']
---

When you tried to upload a file unto your WordPress backend you got this error saying `The uploaded file exceeds the upload_max_filesize directive in php.ini`

## What Are the Causes of the Problem The uploaded file exceeds the upload_max_filesize directive in php.ini
When you purchase a hosting package from your hosting provider, they by default set a limit on the maximum file size upload of a single file in order to save your web server resources. (Don’t worry, you will easily edit this default limit)

This maximum file size upload limit is defined in the `upload_max_filesize directive`. This `upload_max_filesize` directive itself is located into the `php.ini` file. This `php.ini` file is the default server configuration file for the PHP Applications.

This two things `upload_max_filesize` and `php.ini` are what you see in the error message.

N.B: This is not an WordPress error or this setting cannot be controlled via WordPress.

## How to check the upload_max_filesize limit
There are several ways to find the maximum upload size for single file limit via WordPress. If you go to `Media > Add New` there at the bottom you can see `Maximum upload file size : % MB`

Another way of seeing all the memory info and limits and also the other info about you WordPress website is go to `Tools > Site Health > Info > Server`

There you can find all the info about your server along with the **Upload Max File size**.

## How to solve the uploaded file exceeds the upload_max_filesize directive in php.ini
In order to solve this problem we just need to increase the maximum file size limit in `upload_max_filesize` directive which is located in the `php.ini` file.

There are numerous ways to do that. Some method may not work depending on your server configuration and your hosting provider. Choose the best method that work well for you.

Confused about which method will work well for you? Do not need to worry. I got you. The first method will work for you Insha-Allah if you have cPanel hosting.

## 1. Edit PHP configuration via cPanel
1. Log in to your cPanel
2. Go to “Select PHP Version”
3. Heads over options
4. There increase the max upload file size limit

## 2. Edit php.ini via cPanel
This method will word if you have cPanel based hosting manager. This is also a simple method like the first one.

1. Login to your cPanel.
2. Click on MultiPHP INI Editor
3. Then choose your WordPress website from the dropdown menu.
4. Finally you will get the options to edit some php.ini settings along with the upload_max_filesize directive.
5. Increase the value of the upload_max_filesize directive based on your need.

## 3. Modify or Create php.ini file via File Manager / FTP
If you can connect your web server via FTP or via a web based file manager provided by your web hosting company, you will be able to create a php.ini file or if there has existing one you can edit it to fix The uploaded file exceeds the `upload_max_filesize` directive in `php.ini`


1. Connect your site via FTP or browse your webserver files via file manager.
2. Locate your website’s root folder.
3. Here you will find a `php.ini` file or if you do not see any php.ini file then create one.
4. Edit the php.ini file.
5. If you are editing the existing php.ini file then try to find the below code and edit the file size (in MegaBytes).
6. If you do not find the code given below or created a new php.ini file then copy the code given below and paste at the end or your php.ini file.
7. You can edit the file size based on your need.
8. Save the file and check your website. It should work properly Insha-Allah.
```shell
upload_max_filesize = 512M
post_max_size = 100M
memory_limit = 750M
```
## 4. Edit .htaccess file via File Manager / FTP
This method is almost the same as method no. 3. You have to access to your website’s root folder via File Manager or FTP. Then instead of editing the php.ini file you have to edit the `.htaccess` file of the root folder of your website.

1. Connect your site via FTP or browse your webserver files via file manager.
2. Navigate to your website’s root folder.
3. Here you will find a .htaccess file.
4. Edit this .htaccess file
5. Paste the following code at the begining of your .htaccess file.
6. Change the file size values according to your need.
7. Save the file.
```shell
php_value upload_max_filesize 512M
php_value post_max_size 100M
php_value memory_limit 750M
```
After editing the `.htaccess` file please visit your website and make sure your website is running well. If you got an **internal server error** message after editing the `.htaccess` file, your server may be running **PHP in CGI Mode**. If so, that means you will not be able to use these commands into .htaccess file. To fix the internal server error problem, just remove those lines from the .htaccess file which you just added before. Your website should start working again.

Note: If your web server running on Nginx, you will not be able to find a .htaccess file. Which means this method will not work for your website. At that case, please use any other methods.

## 5. Modify wp-config.php file via File Manager / FTP
This method is also similar to the 3rd and 4th methods. First you have to login to your website’s root directory via File Manager or an FTP. Then instead of editing those PHP files you have to edit the wp-config.php file.

1. Connect your site via FTP or browse your webserver files via file manager.
2. browse to your website’s root folder.
3. Here you will find a wp-config.php file.
4. Edit this wp-config.php file
5. Paste the following code before the line /* That's all, stop editing! Happy publishing. */ of your wp-config.php file.
6. Change the file size values according to your need.
7. Save the file.
```shell
@ini_set('upload_max_size' , '512M' );
```
Note: Some method may not work for you according to your hosting server configuration and hosting company.

If none of the above method works for you, then most probably your hosting provider doesn’t allow users to edit the `upload_max_filesize` limit. In that case you have to contact your hosting provider and ask them to do the work for you.
