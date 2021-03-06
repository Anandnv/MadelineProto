---
title: getFile
description: Returns information about a file, offline request
---
## Method: getFile  
[Back to methods index](index.md)


Returns information about a file, offline request

### Params:

| Name     |    Type       | Required | Description |
|----------|:-------------:|:--------:|------------:|
|file\_id|[int](../types/int.md) | Yes|Identifier of the file to get|


### Return type: [File](../types/File.md)

### Example:


```
$MadelineProto = new \danog\MadelineProto\API();
if (isset($token)) {
    $this->bot_login($token);
}
if (isset($number)) {
    $sentCode = $MadelineProto->phone_login($number);
    echo 'Enter the code you received: ';
    $code = '';
    for ($x = 0; $x < $sentCode['type']['length']; $x++) {
        $code .= fgetc(STDIN);
    }
    $MadelineProto->complete_phone_login($code);
}

$File = $MadelineProto->getFile(['file_id' => int, ]);
```

Or, if you're into Lua:

```
File = getFile({file_id=int, })
```

