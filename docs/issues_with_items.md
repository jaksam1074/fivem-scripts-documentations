# Issues with items

It may happen that if you have particular inventories, item addition or removal causes errors in server console

In this case, to try fixing the issue try doing the following steps:

## Step 1

1. Go in the script folder in `integrations/sv_integrations.lua` file
2. Set this option from 
```lua
SKIP_ITEM_EXISTS_CHECK = false
```
to 
``` lua
SKIP_ITEM_EXISTS_CHECK = true
```

## Step 2

1. If the script has a `default_config.json` file, edit this option in the `"server"` section from
```json
"canAlwaysCarryItem": false,
```
to
```json
"canAlwaysCarryItem": true,
```

Example screenshots:

Before: <br>
![Before](images/can_always_carry_item_before.jpg)

After: <br>
![After](images/can_always_carry_item_after.jpg)

### What to do if I don't have canAlwaysCarryItem option?
If you don't have the `canAlwaysCarryItem` option, you simply need to add it, be sure to add it at the **beginning** of the `server` part

Example

Before: <br>
![Before](images/no_can_always_carry_item_before.jpg)

After: <br>
![After](images/no_can_always_carry_item_after.jpg)