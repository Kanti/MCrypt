# MCrypt helper object

## install via Composer
command line:
```bash
composer require kanti/mcrypt ~1
```
composer.json:
```json
"kanti/mcrypt": "~1"
```

## how to use it
```php
<?php
require_once "vendor/autoload.php";

$key = "Password";
$data = file_get_contents(__FILE__);
$options = array();

$jsonString = Kanti\MCrypt::encrypt($key, $data, $options);
$data = Kanti\MCrypt::decrypt($key, $jsonString);

var_dump($jsonString);
var_dump($data);
```
#### $options

|option|default|
|----:|:----:|
|algorithm|``MCRYPT_RIJNDAEL_256``|
|mode|``MCRYPT_MODE_CBC``|
|iv|``php mcrypt_create_iv(mcrypt_get_iv_size($algorithm, $mode), MCRYPT_DEV_URANDOM)``|
