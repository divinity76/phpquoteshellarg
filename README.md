# phpquoteshellarg
php quote shell arguments function
because php's escapeshellarg() function is broken:
```
$str="æøå\x01";
var_dump(["str"=>$str,"escapeshellarg"=>escapeshellarg($str), "quoteshellarg"=>quoteshellarg($str)]);
=>
array(3) {
  ["str"]=>
  string(7) "æøå"
  ["escapeshellarg"]=>
  string(3) "''"
  ["quoteshellarg"]=>
  string(9) "'æøå'"
}
```
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
