---
title: messages.installStickerSet
description: messages.installStickerSet parameters, return type and example
---
## Method: messages.installStickerSet  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|:-------------:|---------:|
|stickerset|[InputStickerSet](../types/InputStickerSet.md) | Yes|
|disabled|[Bool](../types/Bool.md) | Yes|


### Return type: [Bool](../types/Bool.md)

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

$Bool = $MadelineProto->messages->installStickerSet(['stickerset' => InputStickerSet, 'disabled' => Bool, ]);
```

Or, if you're into Lua:

```
Bool = messages.installStickerSet({stickerset=InputStickerSet, disabled=Bool, })
```

