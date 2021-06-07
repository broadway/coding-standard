broadway/coding-standard
========================

The coding standard of the Broadway project.

![build status](https://github.com/broadway/coding-standard/actions/workflows/ci.yml/badge.svg)

# Installation

```
$ composer require --dev broadway/coding-standard
```

# Configuration

## PHP CS fixer

1. create a `.php-cs-fixer.php` file referencing the `.php-cs-fixer.dist.php` template:

```php
# .php-cs-fixer.php

<?php

$config = require 'vendor/broadway/coding-standard/.php-cs-fixer.dist.php';

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
$ vendor/bin/php-cs-fixer fix --allow-risky=yes --diff --verbose
$ vendor/bin/docheader check {src,test}
```
