# Replace default notifications

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

## Example (you can place it in the folder integrations/cl_integrations.lua of the script)
``` lua
RegisterNetEvent("jobs_creator:framework:ready", function() 
    -- Disables the default script notification (otherwise there would be 2 notifications)
    exports["jobs_creator"]:disableScriptEvent("jobs_creator:notify")
end)

RegisterNetEvent("jobs_creator:notify", function(message, uncoloredMessage)
    TriggerEvent("external_script:notify", message)
end)
```