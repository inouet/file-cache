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
$lifetime = 3600; // cache lifetime (default: 3600)
$cache->save($id, $data, $lifetime);

$user = $cache->get($id);
// return false if cache is expired or does not exist

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

Delete cache

```

$cache->delete($id);

```

### Change cache directory

set parameter "cache_dir" to constructor 

```
<?php

$options = array('cache_dir' => __DIR__.'/cache');

$cache = new FileCache($options);
$cache->save("key", "value");
$ tree ./cache
./cache
└── 31
    └── f3
        └── 31f30ddbcb1bf8446576f0e64aa4c88a9f055e3c.cache

2 directories, 1 file

```
