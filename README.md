# php-pjaxr

## How to install php-pjaxr?

There are just two steps needed to install php-pjaxr:

1. Add php-pjaxr to your composer.json:

	```json
	{
        "require": {
            "iekadou/php_pjaxr": "~1.0",
        }
    }
	```

2. Set the current Pjaxr namespace in your View or anywhere before your templates get rendered:

    ```php
    Pjaxr::set_current_namespace('Pjaxr.Home');
	```

## How do i use php-pjaxr?

This example seems to show a huge overhead, actually only the if-else tags make it that big.

```php
// View:
if (!Pjaxr::matches('Pjaxr')) {
    // Do everything you need only for the whole site.
}
if (!Pjaxr::matches('Pjaxr.Home')) {
    // Do everything you need to handle the home page.
}

// Head-Template:
if (!Pjaxr::matches('Pjaxr')) {
    <html>
    <head>
    // Scripts and Stylesheets could be loaded here, no need to reload them when changing the page
    <script...
    <link...
<?php } else { ?>
    <pjaxr-head>
<?php }
...
if (!Pjaxr::matches('Pjaxr')) {
    </head>
<?php } else { ?>
    </pjaxr-head>
<?php }

// Body-Template:
if (!Pjaxr::matches('Pjaxr')) {
    <body>
        <header>...</header>
        <div id="site">
            ...
            <div id="page">
<?php } else { ?>
    <pjaxr-body>
<?php }

// Render everything you need in the page container.

if (!Pjaxr::matches('Pjaxr')) { ?>
            </div>
            ...//site content could still be here
            <footer></footer>
        </div>
    </body>
<?php } else { ?>
    </pjaxr-body>
<?php } ?>
```
If this seems to be too complex for you, try [twig](https://github.com/twigphp/Twig) in combination with [twig-pjaxr](https://github.com/iekadou/twig-pjaxr) for templating.

## What do you need for php-pjaxr?

1. [PHP](http://php.net) >= 5.3.29
2. [jquery-pjaxr](https://github.com/minddust/jquery-pjaxr)

## Projects using php-pjaxr

1. [pjaxr.io](https://github.com/iekadou/pjaxr-io)

If you are using twig-pjaxr, please contact me, and tell me in which projects you are using it. Thank you!

Happy speeding up your php project!

For further information read [php-pjaxr on iekadou.com](http://www.iekadou.com/programming/php-pjaxr)
