# Replace default armory

Triggered when opening an armory

## Event
``` lua
AddEventHandler("jobs_creator:armory:openArmory", function(markerId)

end)
```

### Parameters

| Name              | Data Type | Description                       |
| -                 | -         | -                                 |
| `markerId`            | int       | Marker ID  |

## Example (you can place it in the folder integrations/cl_integrations.lua of the script)
``` lua
RegisterNetEvent("jobs_creator:framework:ready", function() 
    -- Disables the default script armory
    exports["jobs_creator"]:disableScriptEvent("jobs_creator:armory:openArmory")
end)

-- Example to replace the script armory with an external one
RegisterNetEvent("jobs_creator:armory:openArmory", function(markerId)
    -- Example with Chezza's inventory
    TriggerEvent('inventory:open', {
        id = "marker_" .. markerId,
        type = "esx_job_creator_armory",
        title = 'Armory - ' .. markerId,
        weight = 1000,
        save = true,
        timeout = 1000
    })
end)
```