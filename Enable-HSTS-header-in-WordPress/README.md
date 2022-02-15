
Enable HTTP Strict Transport Security (HSTS) in WordPress that’s running on Azure App Service
===
Requirements
In order for HSTS to work as expected, you neet to:
- Have enabled HTTPS before HSTS so browers can accept your HSTS setting

The configurable parameters for HSTS are:
- Enable HSTS(Strict-Transport-Security): On/Off.
- Max Age(max-age): This is essentially a "Time to live" field for the HSTS header.

Add the following code to your .htaccess file.
```
<ifModule mod_headers.c>
Header set Strict-Transport-Security "max-age=31536000; includeSubDomains; preload"  # Enforcing HSTS

</ifModule>
````

 
Verify HSTS Header

