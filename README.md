# PHP Quality Tools

[![Latest Version on Packagist](https://img.shields.io/packagist/v/daniel-werner/php-quality-tools.svg?style=flat-square)](https://packagist.org/packages/daniel-werner/php-quality-tools)
[![Build Status](https://img.shields.io/travis/daniel-werner/php-quality-tools/master.svg?style=flat-square)](https://travis-ci.org/daniel-werner/php-quality-tools)
[![Quality Score](https://img.shields.io/scrutinizer/g/daniel-werner/php-quality-tools.svg?style=flat-square)](https://scrutinizer-ci.com/g/daniel-werner/php-quality-tools)
[![Total Downloads](https://img.shields.io/packagist/dt/daniel-werner/php-quality-tools.svg?style=flat-square)](https://packagist.org/packages/daniel-werner/php-quality-tools)

This package installs the most common quality tools for php: [PHP Code Sniffer](https://github.com/squizlabs/PHP_CodeSniffer),
 [PHP Mess Detector](https://phpmd.org/), [PHP Static Analysis Tool](https://github.com/phpstan/phpstan) and [PHP Coding Standards Fixer](https://github.com/FriendsOfPHP/PHP-CS-Fixer),
 with some reasonable predefined configurations for Laravel using PSR2 coding standard. This package can be used with any
 php project it is not specifically a Laravel package.

 The purpose of the package is to allow the developers to qucikly install and configure
 all the necessary quality tools for the project.

## Installation

You can install the package via composer:

```bash
composer require daniel-werner/php-quality-tools
```

After the composer install, run the following command to copy the default xml settings for the tools and
to set up the scripts in the `composer.json`.

```bash
vendor/bin/phpqt-install
```

The install script will try to guess the source code directory in your project,
if it is a Laravel application it'll use the `app` directory, if it is a package
it'll use the `src` directory, otherwise the current directory.

You can pass the source code directory as the first argument of the install script, like this:

```bash
vendor/bin/phpqt-install my-app
```

After installation the xml configurations can be found in your projects root directory,
 you can customize the phpcs and phpmd condguration by changing the settings in the xml files.

## Usage

The package defines the following script in the `composer.json`:
- `composer inspect`: this command runs the PHP Code Sniffer and the PHP Static Analysis Tool.
This will analyze your code style and run the phpstan with the default minimum level=0
- `composer inspect-fix`: this command will try to fix the problem found by the inspection
by running the `php-cs-fixer` and the `phpcbf`.
- `composer insights`: runs the PHP Mess Detector to find any potential issues in your code.

### Testing

``` bash
composer test
```

### Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information what has changed recently.

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.

### Security

If you discover any security related issues, please email vernerd@gmail.com instead of using the issue tracker.

## Credits

- [Daniel Werner](https://github.com/daniel-werner)
- [All Contributors](../../contributors)

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.

## PHP Package Boilerplate

This package was generated using the [PHP Package Boilerplate](https://laravelpackageboilerplate.com).
