
Redirect HTTP traffic to HTTPS for WordPress on Azure Web App on Linux
===
Once you install an SSL certificate on your website, you might still have some issues. The browser will display ‘info or Not secure’ icon on the address bar. You need to redirect all HTTP request to the HTTPS port.

You can now simply do this as follows: In your app page, select **TLS/SSL setting**. Then, in **HTTPS Only**, select **On** and **Save**.

 ![Image](/Redirect-HTTP-to-HTTPS-for-WordPress-on-Azure/media/Redirect_HTTP_traffic_to_HTTPS.jpg "icon")
 
 Test your work by navigating any of the following HTTP URLs that point to your website, and it should redirect to HTTPS automatically.
 
For example:

http://<app_name>.azurewebsites.net

http://<span></span>example.com

http://<span></span>www<span></span>.example.com
 
 
 
SSL Testing tools
--
If you want to check SSL certificate is installed properly, whether your domain has a modern IPv6, is DNSSEC-signed and check for common vulnerabilities, then you can use any of the following online tools.


https://<span>xn--</span>sikkerpnettet-vfb.dk/

https://<span>www</span>.digicert.com/help


Test your website and see where security can improve.
