
Enable HTTP Strict Transport Security (HSTS) in WordPress that’s running on Azure App Service
===
Requirements

To enable HSTS, you need to fulfill the following requirements:
- Have a valid SSL certificate
- Redirect all HTTP requests to HTTPS (including “www<span>.</span>” and all subdomains)
- Set the Strict-Transport-Security header policy and required parameters

HSTS Syntax is:
```
Strict-Transport-Security: max-age=<expire-time>
Strict-Transport-Security: max-age=<expire-time>; includeSubDomains #Optional
Strict-Transport-Security: max-age=<expire-time>; preload #Optinal

```

Max Age(max-age): This is essentially a "Time to live" field for the HSTS header.


Add the following code to your .htaccess file.
```
<ifModule mod_headers.c>

Header set Strict-Transport-Security "max-age=31536000; includeSubDomains; preload"  

</ifModule>
````

 
Verify HSTS Header
--
To verify whether you have fulfilled the requirements or not, you can submit your site at https://hstspreload.org/ to check HSTS preload status and eligibility for preloading.

**Note:** Be aware about the preload list. Once your website in the preload list, it cannot easily be undone. It may take months to remove from the preload list. Read here for more details about [the Preload removal.](https://hstspreload.org/#removal)


I hope that this article will help you to add an extra layer of security on your website.

---
**Useful links:**

[RFC 6797 (HTTP Strict Transport Security (HSTS)) by the IETF](https://datatracker.ietf.org/doc/html/rfc6797)

[Mozilla – The HTTP Strict-Transport-Security (HSTS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Strict-Transport-Security)

[OWASP Cheat Sheet Series](https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet.html)

[Wikipedia HSTS](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security)



