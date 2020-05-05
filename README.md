# Value Objects

A basic PHP value objects collection.

## Install

_Notice_: Only dev-master available for now.
Use at own risk.

```bash
composer require hyperized/value-objects:dev-master
```

## Examples

### Integer type

```php
<?php declare(strict_types=1);

use Hyperized\ValueObjects\Abstracts\Integers\Integer;

include 'vendor/autoload.php';

// Implement concrete class for as value object
class MyObject extends Integer {}

$myObject = MyObject::fromInteger(1337);

var_dump($myObject->getValue()); // int(1337)
```

Other types that are offered:

* NegativeInteger.
	* Validates value is below 0 (zero).
* PositiveInteger
	* Validates value is above 0 (zero).
* RangedInteger.
	* Validates value is higher than minimum.
	* Validates value is lower than maximum.
	* By default minimum value is `PHP_INT_MIN` and maximum value `PHP_INT_MAX`.
* Octal.
	* Validates value is octal.

### String type (ByteArray)

Strings are called ByteArrays due to string being a reserved word in PHP.

```php
<?php declare(strict_types=1);

use Hyperized\ValueObjects\Abstracts\Strings\ByteArray;

include 'vendor/autoload.php';

class MyObject extends ByteArray {}

$myObject = MyObject::fromString('Hello world!');
var_dump($myObject->getValue()); // string('Hello world');
```

## Licence

MIT

## Author

Gerben Geijteman <gerben@hyperized.net>
