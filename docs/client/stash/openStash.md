# Replace default stash

Triggered when opening a stash

## Event
``` lua
RegisterNetEvent("jobs_creator:stash:openStash", function(markerId)

end)
```

### Parameters

| Name              | Data Type | Description                       |
| -                 | -         | -                                 |
| `markerId`        | int       | Marker ID  |

## Example (you can place it in the folder integrations/cl_integrations.lua of the script)
``` lua
RegisterNetEvent("jobs_creator:framework:ready", function() 
    -- Disables the default script stash
    exports["jobs_creator"]:disableScriptEvent("jobs_creator:stash:openStash")
end)

-- Example to replace the script stash with an external one
RegisterNetEvent("jobs_creator:stash:openStash", function(markerId)
    -- Example with Chezza's inventory
    TriggerEvent('inventory:open', {
        id = "marker_" .. markerId,
        type = "esx_job_creator_stash",
        title = 'Stash - ' .. markerId,
        weight = 1000,
        save = true,
        timeout = 1000
    })
end)
```