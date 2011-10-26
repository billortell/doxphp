# Dox PHP

Dox for PHP is a documentation engine for PHP inspired by the [Dox](https://github.com/visionmedia/dox) for JavaScript.

# Installation

Clone this repository and put the `doxphp` under bin directory in your executable path.

# Usage

Dox PHP operates over stdio:

```shell
$ doxphp < test.php
...JSON...
```

test.php

```php
<?php

/**
 * Greets the world
 *
 * @param string $world - the world to greet
 *
 * @return void
 */
function hello($world) {
  echo "Hello ${world}";
}
```

output

```js
[
  {
      "tags": [
          {
              "type"        : "param"
            , "types"       : ["string"]
            , "name"        : "world"
            , "description" : "- the world to greet"
          }
        , {
              "type"  : "return"
            , "types" : ["void"]
          }
      ]
    , "description" : "Greets the world"
    , "isPrivate"   : false
    , "isProtected" : false
    , "isPublic"    : true
    , "isAbstract"  : false
    , "isFinal"     : false
    , "isStatic"    : false
    , "code"        : "function hello($world)"
    , "type"        : "function"
    , "name"        : "hello()"
  }
]
```

# Supports

* classes and interfaces
* functions and methods (produces slightly different results)
* namespaces (who phpdocs them really?)
* class variables and constants (sweet!)

# Renderers

* doxphp2sphinx

```bash
$ doxphp < test.php | doxphp2sphinx  > test.rst
```

test.rst:

```rst
.. php:function:: hello

   Greets the world

   :param string $world: - the world to greet

   :returns void:
```

# TODO

implement more renderers
