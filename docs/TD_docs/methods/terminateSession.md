---
title: terminateSession
description: Terminates another session of logged in user
---
## Method: terminateSession  
[Back to methods index](index.md)


Terminates another session of logged in user

### Params:

| Name     |    Type       | Required | Description |
|----------|:-------------:|:--------:|------------:|
|session\_id|[long](../types/long.md) | Yes|Session identifier|


### Return type: [Ok](../types/Ok.md)

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

$Ok = $MadelineProto->terminateSession(['session_id' => long, ]);
```

Or, if you're into Lua:

```
Ok = terminateSession({session_id=long, })
```

