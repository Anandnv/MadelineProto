---
title: resetAuth
description: Logs out user. If force == false, begins to perform soft log out, returns authStateLoggingOut after completion. If force == true then succeeds almost immediately without cleaning anything at the server, but returns error with code 401 and description "Unauthorized"
---
## Method: resetAuth  
[Back to methods index](index.md)


Logs out user. If force == false, begins to perform soft log out, returns authStateLoggingOut after completion. If force == true then succeeds almost immediately without cleaning anything at the server, but returns error with code 401 and description "Unauthorized"

### Params:

| Name     |    Type       | Required | Description |
|----------|:-------------:|:--------:|------------:|
|force|[Bool](../types/Bool.md) | Yes|If true, just delete all local data. Session will remain in list of active sessions|


### Return type: [AuthState](../types/AuthState.md)

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

$AuthState = $MadelineProto->resetAuth(['force' => Bool, ]);
```

Or, if you're into Lua:

```
AuthState = resetAuth({force=Bool, })
```

