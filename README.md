# phpquoteshellarg
php quote shell arguments function
... doing a better job than php's builtin escapeshellarg(): https://3v4l.org/Hkv7h

# installation
the script is just a standalone .php file, you can just copypaste it. 

another alternative is to use composer:
```
composer require 'divinity76/phpquoteshellarg'
```
# usage

```
<?php
require_once(__DIR__ . '/vendor/autoload.php');
use function Divinity76\quoteshellarg\quoteshellarg;

$str="æøå\x01";
var_dump(["str"=>$str,"escapeshellarg"=>escapeshellarg($str), "quoteshellarg"=>quoteshellarg($str)]);
```
may outputs something like
```
array(3) {
  ["str"]=>
  string(7) "æøå"
  ["escapeshellarg"]=>
  string(3) "''"
  ["quoteshellarg"]=>
  string(9) "'æøå'"
}
```
