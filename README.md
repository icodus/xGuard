# xGuard
Nginx Firewall

This is a kind of the famous [7G Firewall](https://exo.com/scripts/examples) by Jeff Starr fork. 

The code here is based on Jeff Cleverley's [GridPane Nginx Configs](https://gitlab.gridpane.net/gp-public/nginx-configs) but modified to better meet Nginx standards.

Should be a bit more reliable and a bit faster most probably. 

## Logging
*xG.log example:*

```
[17/Apr/2024:09:35:30]["bad_querystring_6" "bad_request_24"] 192.168.100.112 gem.domain.com "GET /sheller.js?v=fckeditor HTTP/2.0" 403 0.000 "" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/116.0.0.0 Safari/537.36"
```
## Whitelisting (not a part of this repository)
*all in one whitelist.conf example:*
```
#whitelist bad_querystring_6 and bad_referer_13 on gem.domain.com  
"~*(gem.domain.com):(.*)(bad_querystring_6|bad_referer_13)";
#whitelist static files everywhere
"~*(\.(jpg|css|png)):(.*)";
#whitelist bad_request_24 coming from 192.168.100.103  
"~*(192.168.100.103):(.*)(bad_request_24)";
#whitelist bad_querystring_6 and bad_request_24 if query string contains "page=seopress-google-analytics&code"
"~*(page=seopress-google-analytics&code):(.*)(bad_querystring_6|bad_request_24)";
```










   
