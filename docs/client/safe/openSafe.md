Triggered when opening a safe

## Event
``` lua
AddEventHandler("esx_job_creator:safe:openSafe", function(markerId)

end)
```

### Parameters

| Name              | Data Type | Description                       |
| -                 | -         | -                                 |
| `markerId`            | int       | Marker ID  |

## Example
``` lua
AddEventHandler("esx_job_creator:esx:ready", function() 
    -- Disables the default script safe
    exports["esx_job_creator"]:disableScriptEvent("esx_job_creator:safe:openSafe")
end)

-- Example to replace the script safe with an external one
AddEventHandler("esx_job_creator:safe:openSafe", function(markerId)
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