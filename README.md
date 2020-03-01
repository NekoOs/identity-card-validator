# PHP identity card validator

This library allows you to validate a format identity card according to country.

## Installation

Add package to your composer.json by running:

```
$ composer require nekoos/world-identity-cards
```

## Usage

Before using a validator, it must be created:

```php
use NekoOs\IdentityCard;

// create the identity card "manager" class
$identityCard = new IdentityCard();

// build a new format validator using the ISO 3166-1 country identifier
$validator = $identityCard->getFormatValidator('CO');
```

Then it can be used passing in string values for document type according to the country and identifier to the `test()` method:

```php
$validator->test('CC', '1140816758'); // outputs boolean
```

## Available countries

Country              | Identifier |
---------------------|------------|
Colombia             | CO         |
Peru                 | PE         |
Ecuador              | EC         |

### Available formats by country

There is currently no standard for this, therefore it is defined based on what is found in the government sites of each country:

#### Colombia

see https://www.datos.gov.co/api/id/shc6-n6i6.json

| type | description           |
|------|-----------------------|
| CC   | Cédula de Ciudadanía  |
| CE   | Cédula de Extranjería |
| PA   | Pasaporte             |
| RC   | Registro Civil        |
| TI   | Tarjeta de Identidad  |


## Questions and answers

**Q: There's an error!**

A: Please report an issue, or even better - create a pull request. I don't speak most of those languages so your help is much appreciated. Thanks!
