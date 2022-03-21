Returns if the player is on duty or not.

## Event
``` lua
exports["jobs_creator"]:isPlayerOnDuty(playerId)
```

### Parameters

| Name              | Data Type | Description                 |
| -                 | -         | -                 |
| `playerId`        | integer    | Target player server ID  |

### Return
| Name              | Data Type | Description                 |
| -                 | -         | -                 |
| `isOnDuty`        | boolean    | **true** if the player is on-duty <br> **false** if the player is off-duty  |


## Example
``` lua
local playerId = 52

print("Player ID " .. playerId .. " is on duty: " .. tostring( exports["jobs_creator"]:isPlayerOnDuty(playerId) ))
```