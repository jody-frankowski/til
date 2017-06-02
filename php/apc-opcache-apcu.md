# APC, OPcache and APCu

PHP's `APC` allows you to cache opcode and store arbitrary keys in a key-value
store. Since 2012 it has been deprecated and split into two components, `OPcache`
and `APCu`. `OPcache` which is the opcode cache part is integrated into the core
of Zend since PHP 5.5, and `APCu` which is the key-value store part is available
as a PHP extension since 2013.
