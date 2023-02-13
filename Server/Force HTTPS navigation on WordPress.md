This will permanently redirect all _http://_ (non secure) request to the right _https://_ version. Place this code in .htaccess file before any other rules. 
```
RewriteCond %{HTTPS} off 
RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
```

Tested on Apache and Litespeed servers.