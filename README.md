# Inviqa - Magento1 Coding Standard

## Installation & Usage
```bash
composer config repositories.inviqa-magento1cs vcs https://github.com/inviqa/magento-phpcs-coding-standard
composer require inviqa/magento1-coding-standard --update-with-dependencies --dev
```

### Composer Scripts

Utility configuration to wrapping `phpcs` arguments, require the package using Composer's CLI.

```bash
composer.phar require inviqa/magento-phpcs-coding-standard --dev --update-with-dependencies
```

Update your project's `composer.json` with the following root options

```json
{
    "config": {
        "bin-dir": "bin"
    },
    "scripts": {
        "sniff": "bin/phpcs -ns --standard=vendor/inviqa/magento-phpcs-coding-standard"
    }
}
```

Run Composer script

```sh
composer.phar sniff Magento/app/code/local/Acme/ExampleModule/{Block,Helper,Model}
```

## Requirements
PHP >= 5.6

## Development

A docker environment has been provided to update the composer dependencies - should composer / PHP not be available globally on the host development machine.

```bash
docker-compose up -d
docker-compose rn --rm composer bash
composer update | require acme/package
```

Commit the updated `composer.json` for peer review.

## Contribution
Please feel free to contribute new sniffs or any fixes or improvements for the existing ones.
