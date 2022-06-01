# Manually start drugs effects

Trigger to start drug effects (you may prefer to trigger this from server side)

## Event
``` lua
TriggerEvent("advanced_drugs_creator:drugEffects", takingMethod, effects, effectsDuration)
```

### Parameters

| Name              | Data Type | Description                 |
| -                 | -         | -                             |
| `takingMethod`        | string | How the player will take the drug |
| `effects`             | table | An array of strings containing all effects you want to add |
| `effectsDuration`             | integer | Seconds the effects will last |

### Taking methods
`"pill"` <br>
`"drink"` <br>
`"smoke"` <br>
`"needle"` <br>

### Effects
`"visual_shaking"` <br>
`"drunk_walk"` <br>
`"fall"` <br>
`"pink_visual"` <br>
`"green_visual"` <br>
`"confused_visual"` <br>
`"armor50"` <br>
`"armor100"` <br>
`"health50"` <br>
`"health100"` <br>
`"sprint_faster"` <br>
`"swim_faster"` <br>
`"infinite_stamina"` <br>

## Example - Client side
``` lua
RegisterCommand("effects", function() 
    local takingMethod = "pill"
    local effects = {
        "drunk_walk",
        "swim_faster",
        "green_visual",
    }

    local effectsDuration = 120 -- seconds

    TriggerEvent("advanced_drugs_creator:drugEffects", takingMethod, effects, effectsDuration)
end)
```

## Example - Server side
``` lua
RegisterCommand("effects", function(playerId) 
    local takingMethod = "pill"
    local effects = {
        "drunk_walk",
        "swim_faster",
        "green_visual",
    }

    local effectsDuration = 120 -- seconds

    TriggerClientEvent("advanced_drugs_creator:drugEffects", playerId, takingMethod, effects, effectsDuration)
end)
```