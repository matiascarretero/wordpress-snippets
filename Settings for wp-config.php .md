## Settings for wp-config.php
### Disable or change posts revisions setttings
Disable or limit the number of posts revisions that WordPress stores in the database. For [WP_POST_REVISIONS](https://wordpress.org/documentation/article/revisions/#revision-options) you can set:
- true (default), -1: store every revision
- false, 0: do not store any revisions (except the one autosave per post)
- (int) > 0: store that many revisions (+1 autosave) per post. Old revisions are automatically deleted.
```php
define('WP_POST_REVISIONS', false); // Disable posts, pages and custom post types revisions
define('WP_POST_REVISIONS', 3); // Enable, disable or change the number of revisions
define('AUTOSAVE_INTERVAL', 300); // Number of seconds to wait before a revision while you are editing a post. Default value is 60.
```
### Try to increase PHP memory limit from WordPress
This setting is usually overwriten by php.ini or hosting control panel settings. You can try if it works:
```php
define('WP_MEMORY_LIMIT', '256M'); // Use letter M for megabytes 
```
### Change the number of days to delete trash
```php
define('EMPTY_TRASH_DAYS', 1)
```
### Set the time to autosave posts while editing
```php
define('AUTOSAVE_INTERVAL', 300);
```
### Disable file editing for themes and plugins
```php
define ( 'DISALLOW_FILE_EDIT', true );
```

### Allow administrators to upload any file type
Just works for administrators. It is useful tu upload .svg files.
```php
define( 'ALLOW_UNFILTERED_UPLOADS', true );
```

### Debugging
WordPress hides PHP errors and warnings for default. You can temporaly enable this errors with one of the following methods:
```php
// Change $debug to true to enable error displaying and logging. Set to false to hide them.
$debug = true;
if($debug) {
	define( 'WP_DEBUG', true );
	define( 'WP_DEBUG_DISPLAY', true );
	define( 'WP_DEBUG_LOG', true );
	ini_set('display_errors',1);
	ini_set('display_startup_errors',1);
	error_reporting(E_ALL);
} else {
	define('WP_DEBUG', false);
	ini_set('display_errors',0);
	ini_set('display_startup_errors',0);
	error_reporting(0);
}
```

```php
// To debug specific URLs, you could append parameter enable_debug to the URL just like this: https://domain.com/?enable_debug=my_secret_key 
if ( !empty( $_GET['enable_debug'] ) && $_GET['enable_debug'] === 'my_secret_key' ) { // Change 'my_secret_key' to something different
	define( 'WP_DEBUG', true );
	define( 'WP_DEBUG_DISPLAY', true );
	define( 'WP_DEBUG_LOG', true );
	ini_set('display_errors',1);
	ini_set('display_startup_errors',1);
	error_reporting(E_ALL);
} 
```