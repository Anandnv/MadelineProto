---
title: getAttachedStickerSets
description: Returns list of sticker sets attached to a file, currently only photos and videos can have attached sticker sets
---
## Method: getAttachedStickerSets  
[Back to methods index](index.md)


Returns list of sticker sets attached to a file, currently only photos and videos can have attached sticker sets

### Params:

| Name     |    Type       | Required | Description |
|----------|:-------------:|:--------:|------------:|
|file\_id|[int](../types/int.md) | Yes|File identifier|


### Return type: [StickerSets](../types/StickerSets.md)

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

$StickerSets = $MadelineProto->getAttachedStickerSets(['file_id' => int, ]);
```

Or, if you're into Lua:

```
StickerSets = getAttachedStickerSets({file_id=int, })
```

