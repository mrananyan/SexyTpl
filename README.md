# Usage
* Create templates directory
```sh
 mkdir tpls
```
* Create index.tpl in tpls directory with this content
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>SexyTpl demostation </title>
</head>
<body>
Single: {varable}
<hr>
{bmw} {tesla}
</body>
</html>
```
* Create index.php with this content
```php
<?php
include __dir__ . '/tpl.php'; // load the lib
ob_start("tpl_clean"); // compress output (it's make your page faster || optional)
tpl_load('index'); // load index.tpl from "tpls" folder
tpl_set('{varable}', 'Single varable'); // set single var to tpl
tpl_set(array('{bmw}' => 'BMW is love', '{tesla}' => 'but Tesla is future'); // set array to tpl
tpl_make('_main'); // make html
echo $tpl_res['_main']; // output it
```
