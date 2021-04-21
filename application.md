---
layout: default
title: Application
nav_order: 3
has_children: false
has_toc: false
---
# Application

The Application `Flexible\Application` is the entry point to the framework. Think about it as a manager that glues all parts.

```php
<?php

use Flexible\Application;
use Flexible\Http\ServerRequest;

require __DIR__ . '/vendor/autoload.php';

$app = Application::create();

$app->router()->get('/', App\SomeController::class);

$app->emit(
    $app->handle(ServerRequest::fromGlobals())
);
```