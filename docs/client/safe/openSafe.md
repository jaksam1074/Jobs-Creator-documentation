Triggered when opening a safe

## Event
``` lua
RegisterNetEvent("jobs_creator:safe:openSafe", function(markerId)

end)
```

### Parameters

| Name              | Data Type | Description                       |
| -                 | -         | -                                 |
| `markerId`            | int       | Marker ID  |

## Example (you can place it in the folder integrations/cl_integrations.lua of the script)
``` lua
RegisterNetEvent("jobs_creator:framework:ready", function() 
    -- Disables the default script safe
    exports["jobs_creator"]:disableScriptEvent("jobs_creator:safe:openSafe")
end)

-- Example to replace the script safe with an external one
RegisterNetEvent("jobs_creator:safe:openSafe", function(markerId)
    -- Example with Chezza's inventory
    TriggerEvent('inventory:open', {
        id = "marker_" .. markerId,
        type = "esx_job_creator_safe",
        title = 'Safe - ' .. markerId,
        weight = 1000,
        save = true,
        timeout = 1000
    })
end)
```