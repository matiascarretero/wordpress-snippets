## Security improvements
You can add these rules to .htaccess in your WordPress root folder. Each line with # is the explanation of the rule.
```
# Prevent xmlrpc.php access
<files xmlrpc.php>
order allow,deny
deny from all
</files>

# Prevent wp-config.php access
<files wp-config.php>
order allow,deny
deny from all
</files>

# Prevent wp-readme.html access
<files readme.html="">
Order allow,deny
Deny from all
</files>

# Prevent username enumeration
RewriteCond %{QUERY_STRING} author=d
RewriteRule ^ /? [L,R=301]
```