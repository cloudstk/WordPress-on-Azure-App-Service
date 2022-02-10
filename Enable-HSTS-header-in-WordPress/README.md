
Enable HTTP Strict Transport Security (HSTS) in WordPress that’s running on Azure App Service
===
```
<ifModule mod_headers.c>
Header set Strict-Transport-Security "max-age=31536000; includeSubDomains; preload"  # Enforcing HSTS

</ifModule>
````
