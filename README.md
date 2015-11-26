# Inviqa Fork
This fork adds Zend Standard Configuration

#ECG Magento Code Sniffer Coding Standard

[![SensioLabsInsight Medal](https://insight.sensiolabs.com/projects/a06c37c6-0d79-4476-aff5-12d8ce1d8c53/big.png "SensioLabsInsight Medal")](https://insight.sensiolabs.com/projects/a06c37c6-0d79-4476-aff5-12d8ce1d8c53)

ECG Magento Code Sniffer Coding Standard is a set of rules and sniffs for [PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer) tool.

It allows automatically check your code against some of the common Magento and PHP coding issues, like:
- raw SQL queries;
- SQL queries inside a loop;
- direct instantiation of Mage and Enterprise classes;
- unnecessary collection loading;
- excessive code complexity;
- use of dangerous functions;
- use of PHP superglobals;

and many others.


#Installation & Usage

Before starting using our coding standard install [PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer).

Clone or download this repo somewhere on your computer or install it with [Composer](http://getcomposer.org/).
To do so, add the dependency to your `composer.json` file by running `composer require magento-ecg/coding-standard`.

Run CodeSniffer:

```sh
phpcs --standard=/path/to/Ecg/standard /path/to/code
```
PHP CodeSniffer will automatically scan Magento PHP files. To check design templates, you can specify `phtml` in the `--extensions` argument: `--extensions=php,phtml`.

#Scrutinizer
To add a custom CodeSniffer standard in your Scrutinizer build process see documentation here: https://scrutinizer-ci.com/docs/tools/php/code-sniffer.  
You need to add the lines below to the Scrutinizer build file:
```
tools:
    php_code_sniffer:
        config: { standard: 'Ecg' }
```
```
checks:
    php:
        custom_coding_standard:
            git_repository: 'https://github.com/inviqa/magento-phpcs-coding-standard.git'
            git_version: 'origin/master'
            ruleset_path: 'ruleset.xml'
```

*Note:* `custom_coding_standard` must be the first entry under `checks.php`. If other checks are performed first the original ECG standard will be loaded, which results in a conflict.

#Requirements

PHP 5.4 and up.

Checkout the `php-5.3-compatible` branch to get the PHP 5.3 version.

#Contribution

Please feel free to contribute new sniffs or any fixes or improvements for the existing ones.
