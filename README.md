
<p align="center">
  <a href="https://php.net" target="_blank"><img src="https://img.shields.io/static/v1?label=PHP&message=%3E=7.2&color=blue&style=flat-square" alt="PHP Version : >= 7.2"></a>
  <img src="https://img.shields.io/static/v1?label=License&message=MIT&color=brightgreen&style=flat-square" alt="License">
  <img src="https://github.com/Pharaonic/php-dot-array/actions/workflows/build.yml/badge.svg" alt="Tests">
  <br>
  <a href="https://packagist.org/packages/Pharaonic/php-dot-array" target="_blank"><img src="https://img.shields.io/static/v1?label=Packagist&message=pharaonic/php-dot-array&color=blue&logo=packagist&logoColor=white" alt="Source"></a>
  <a href="https://packagist.org/packages/pharaonic/php-dot-array" target="_blank"><img src="https://poser.pugx.org/pharaonic/php-dot-array/v" alt="Packagist Version"></a>
  <a href="https://packagist.org/packages/pharaonic/php-dot-array" target="_blank"><img src="https://poser.pugx.org/pharaonic/php-dot-array/downloads" alt="Packagist Downloads"></a>
</p>

<h3 align="center">Accessing arrays using dot notation and asterisk.</h3>
<br>

## Documentation

You can find the detailed documentation here in [Dot-Array Documentation](https://pharaonic.io/packages/php/dot-array).

The documentation below is taken from https://www.phpclasses.org/package/11408-PHP-Access-array-elements-using-path-strings-with-dots.html for ease of access (here).

### Install
Install the latest version using Composer:

`$ composer require pharaonic/php-dot-array`

### Usage
Initialize and create a new DotArray object:
```
use Pharaonic\DotArray\DotArray;

require_once __DIR__ . '/vendor/autoload.php';

$dot = new \Pharaonic\DotArray\DotArray;

// With existing array
$dot = new \Pharaonic\DotArray\DotArray($array);
```
OR You can use a helper function to create the object:

```$dot = dot();

// With existing array
$dot = dot($array);
```

### Methods
DotArray has the following methods:
```
set()
get()
toJson()
all()
delete()
clear()
has()
count()
isEmpty()
setArray()
setReference()
```

#### set()
Sets a given key / value pair:
```
$dot->set('users.raggi.created_at', date('r', time()));`

// ArrayAccess
$dot['users.raggi.created_at'] = date('r', time());
```

#### get()
Returns the value of a given key:
```
print_r($dot->get('users.*.name'));

// ArrayAccess
print_r($dot['users.*.name']);
Returns a given default value, if the given key doesn't exist:

print_r($dot->get('users.*.name', 'Raggi'));
```

#### toJson()
Returns the value of a given key (like get() method) as JSON:

echo $dot->toJson('users');
Returns all the stored items (like get() method) as JSON:

echo $dot->toJson();
```

#### all()
Returns all the stored items as an array:

$values = $dot->all();
```

#### delete()
Deletes the given key:
```
$dot->delete('users.*.name');

// ArrayAccess
unset($dot['users.*.name']);
```

#### clear()
Deletes all the stored items:

`$dot->clear();`

#### has()
Checks if a given key exists (returns boolean):
```
$dot->has('users.raggi.name');

// ArrayAccess
isset($dot['users.raggi.name']);
```

#### count()
Returns the number of the root Items:
```
$dot->count();

// Or use count() function [Countable Way]
count($dot);
```
Returns the number of items in a given key:

`$dot->count('users');`

#### isEmpty()
Checks if a given key is empty (returns boolean):
```
$dot->isEmpty('users.raggi.name');

// ArrayAccess
empty($dot['users.raggi.name']);
```
Checks the whole DotArray object:

`$dot->isEmpty();`

#### setArray()
Replaces all items in DotArray object with a given array:

`$dot->setArray($array);`

#### setReference()
Replaces all items in Dot object with a given array as a reference:

`$dot->setReference($array);`

## Contributing

Thank you for considering contributing to this package! Be one of Pharaonic team.

## License

This package is an open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
