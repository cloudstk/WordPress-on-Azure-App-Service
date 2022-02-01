
Restrict WordPress admin access by IP addresses that’s running on Azure web app container.
=======
This article will explain how to restrict WordPress admin access by IP addresses using .htaccess file.

Let’s walk through the process step-by-step.

**Step 1:**
-----------

**Back up your site** before editing .htaccess file. If something goes wrong during editing, you can quickly restore back the website.

**Step 2:**
-----

Log in to FTP/SFTP server. Once authenticated, you can see a similar screen, as shown in figure 1.0, the .htaccess file is located in the root directory of your WordPress site.

 ![Image](/Restrict-WordPress-admin-access-by-IP/media/htaccess_file_location.jpg "icon")
 
  Figure 1.0: .htaccess file location

**Step 3:**
----

Insert the code below into the wwwroot/.htaccess file, remember to replace the IP “xx.xx.xx.xx” with a specific IP address that you allow to access WordPress Admin login page. If you want to add more IP addresses to allow access WP-ADMIN area, copy “SetENVIf X-Client-IP "xx.xx.xx.xx" line. You can add as many IP addresses as you want. If your IP address is not static, It may not be the best option for you.
```
<Files wp-login.php>
 Order Deny,Allow
 Deny from all
 SetENVIf X-Client-IP "xx.xx.xx.xx" AllowAccess
 Allow from env=AllowAccess
</Files>
```


The rule above will allow you to access the WordPress login page for specified IPs address. All other IP addresses will get redirected to the 403 Forbidden Error page instead of the login page,as shown as figure 2.0

 ![Image](/Restrict-WordPress-admin-access-by-IP/media/403_Forbidden_err_page.jpg "icon")
 
 Figure 2.0: 403 Forbidden Error page
 
 In this article, we have learnt how to provide an extra layer of WordPress security to your login pages (WP-admin folder and wp-login.php file) by using limit login access to IP addresses.
 
 
Hope it helps. Happy learning. :-) 

 
