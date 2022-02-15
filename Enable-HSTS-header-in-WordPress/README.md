
Enable HTTP Strict Transport Security (HSTS) in WordPress that’s running on Azure App Service
===

Add the following code to your .htaccess file.
```
<ifModule mod_headers.c>
Header set Strict-Transport-Security "max-age=31536000; includeSubDomains; preload"  # Enforcing HSTS

</ifModule>
````
Requirements
In order for HSTS to work as expected, you neet to:
- Have enabled HTTPS before HSTS so browers can accept your HSTS setting
 
Verify HSTS Header

