Triggered when searching in a player inventory 

## Event
``` lua
RegisterNetEvent("jobs_creator:actions:search:searchPlayer", function(targetServerId)

end)
```

### Parameters

| Name              | Data Type | Description                 |
| -                 | -         | -                             |
| `targetServerId`         | integer    | The target player server ID  |

## Example
``` lua
RegisterNetEvent("jobs_creator:esx:ready", function() 
    -- Disables the default script search (otherwise there would be 2 searches)
    exports["jobs_creator"]:disableScriptEvent("jobs_creator:actions:search:searchPlayer")
end)

RegisterNetEvent("jobs_creator:actions:search:searchPlayer", function(targetServerId)
    TriggerEvent("external_script:searchInPlayerInventory", targetServerId)
end)
```