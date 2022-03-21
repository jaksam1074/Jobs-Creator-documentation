Triggered after notifying player client side

## Event
``` lua
RegisterNetEvent("jobs_creator:notify", function(message, uncoloredMessage)

end)
```

### Parameters

| Name              | Data Type | Description                 |
| -                 | -         | -                             |
| `message`         | string    | Message of the notification  |
| `uncoloredMessage`         | string    | Message of the notification but without ~r~, ~g~, etc.  |

## Example
``` lua
RegisterNetEvent("jobs_creator:esx:ready", function() 
    -- Disables the default script notification (otherwise there would be 2 notifications)
    exports["jobs_creator"]:disableScriptEvent("jobs_creator:notify")
end)

RegisterNetEvent("jobs_creator:notify", function(message, uncoloredMessage)
    TriggerEvent("external_script:notify", message)
end)
```