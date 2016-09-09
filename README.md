# Slim Mustache View

Mustache View package for the Slim Framework 3+.

## How to install

#### Using [Composer](http://getcomposer.org/)


```bash
$ composer require jahmie/slim-mustache-view
```

## How to use

```php
<?php
require 'vendor/autoload.php';

$app = new \Slim\Slim();
$container = $app->getContainer();
$container['view'] = function ($c) {
    $mustache = new \Slim\Mustache\Mustache(
        '/templates', // Template path
        array(
            'charset' => 'UTF-8',
        ),
        array(
            'extension' => '.html'
        )
    );
    return $mustache;
};
$app->get('/', function (Request $request, Response $response) {
    // The render method takes the reponse object,
    // template name and finally some data as an array.
    $response = $this->view->render($response, "hello", ["foo" => 'bar']);
    return $response;
});
```

## Authors

[Jamie Telin](https://github.com/jahmie/)

## License

The MIT License (MIT)

## Change log

### 1.0
First version y'all!
