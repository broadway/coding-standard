broadway/coding-standard
========================

The coding standard of the Broadway project.

# Installation

```
$ composer require --dev broadway/coding-standard
```

# Configuration

## PHP CS fixer

1. create a `.php_cs` file referencing the `.php_cs.dist` template:

```php
# .php_cs

<?php

$config = require 'vendor/broadway/coding-standard/.php_cs.dist';

$config->setFinder(
    \PhpCsFixer\Finder::create()
        ->in([
            __DIR__ . '/src',
            __DIR__ . '/test',
        ])
);

return $config;

```

2. add `.php_cs.cache` to your `.gitignore`.

## docheader

1. copy the `.docheader.dist` template:

```
cp vendor/broadway/coding-standard/.docheader.dist ./.docheader
```

2. modify the `.docheader` file is necessary.

# Usage

```
$ vendor/bin/php-cs-fixer fix --config=".php_cs" --allow-risky=yes --diff --verbose
$ vendor/bin/docheader check {src,test}
```
