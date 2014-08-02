FileCache
==========

A simple PHP class for caching


Usage
-------------------

```php
<?php

require 'vendor/autoload.php';

$cache = new FileCache();

$id = "user/10";
$data = array(
    'name' => 'John',
    'age'  => 20,
    'sex'  => 'f',
);

$cache->save($id, $data);

$user = $cache->get($id);

print_r($user);

```

output:

```
Array
(
    [name] => John
    [age] => 20
    [sex] => f
)
```

Cache files are stored in /tmp/cache directory by default.
It will be saved under the folder hierarchy of 2.

```
$ tree /tmp/cache
/tmp/cache
└── a2
    └── 24
        └── a224b17e63b8eb3103a8c4679b7de2072b598c99.cache
```

