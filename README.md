# WordPress Snippets
This is a collection of snippets and functions for WordPress developers. It has PHP + JS + CSS code ready to copy and paste in your projects.

With most of this snippets, you can skip installing plugins that provides the same functionality. And this is the goal of this repo.

## How to use 📕
**PHP** snippets should be pasted in your custom or [child theme](https://developer.wordpress.org/themes/advanced-topics/child-themes/) functions.php file. If you are developing your own plugin file, you have more freedom of choise. Anyway, you **should not** edit core WordPress files (i.e. anything in root or wp-includes folder).

**CSS** snippets can be added to your custo theme style.css file or placed in a new .css file in your theme. You have to [enqueue this new file](https://developer.wordpress.org/reference/functions/wp_enqueue_style/) with this code in your functions.php:
```php
wp_enqueue_style('custom-css', get_stylesheet_directory_uri().'/style.css');
```

For **JS** code, you can:
1) Add to your main script .js file, and make sure you [enqueue that file](https://developer.wordpress.org/reference/functions/wp_enqueue_script/). I.e. for a custom theme, you might place this code in functions.php
    ```php
    wp_enqueue_script('custom-js', get_stylesheet_directory_uri() . '/script.js');
    ```
2) Place code in a new .js file and enqueue it the same way as shown before.

## Need more snippets? 🤷‍♂️ 
Try these repositories I have found. There are a lot of snippets to be discovered!
- [senlin/Code-Snippets](https://github.com/senlin/Code-Snippets): A lot of snippets, well categorized and almost everything you will need for your project.
- [taniarascia/wp-functions](https://github.com/taniarascia/wp-functions): Last updated on 2019-10 but snippets still working.
- [dalenguyen/wordpress-snippets](https://github.com/dalenguyen/wordpress-snippets): Mostly PHP snippets for developers. Last updated 2022-10.
