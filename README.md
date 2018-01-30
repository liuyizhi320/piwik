# piwik

* tracking javascript
https://developer.piwik.org/guides/tracking-javascript-guide

* custom code for js-file in other servers

```javascript
<!-- Piwik -->
<script type="text/javascript">
  var _paq = _paq || [];
  /* tracker methods like "setCustomDimension" should be called before "trackPageView" */
  _paq.push(["setCookieDomain", "*.xxx.com"]);
  _paq.push(["setDomains", ["*.xxx.com"]]);
  _paq.push(['trackPageView']);
  _paq.push(['enableLinkTracking']);
  (function() {
    var u="//piwik.ceair.com/piwik/";
    _paq.push(['setTrackerUrl', u+'piwik.php']);
    _paq.push(['setSiteId', '1']);
    var d=document, g=d.createElement('script'), s=d.getElementsByTagName('script')[0];
    g.type='text/javascript'; g.async=true; g.defer=true; g.src="//XXX.aliyuncs.com/piwik/piwik.js"; 
    s.parentNode.insertBefore(g,s);
  })();
</script>
<!-- End Piwik Code -->

```
* Database schema
https://developer.piwik.org/guides/persistence-and-the-mysql-backend

* proxy
https://piwik.org/faq/how-to-install/faq_98/

* Installation Q&A
https://piwik.org/faq/how-to-install/

* tracking-api
https://developer.piwik.org/api-reference/tracking-api

* Tracking API Clients SDK FOR IOS AND ANDROID
https://developer.piwik.org/guides/tracking-api-clients

* How do I select IP addresses or Visitor ID directly from the database?<br>
````sql
SELECT 
inet_ntoa(conv(hex(location_ip), 16, 10)) as ip, 
conv(hex(idvisitor), 16, 10) as visitorId 
FROM piwik_log_visit;
````

* user id
https://developer.matomo.org/guides/tracking-javascript-guide#user-id
