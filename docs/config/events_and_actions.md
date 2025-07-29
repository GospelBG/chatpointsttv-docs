## Events
By default, all events are disabled by default. To enable them, simply uncomment (remove the `# `) the respective lines for each event in your twitch.yml
ChatPointsTTV is able to listen to the following events:

### Twitch
- Channel Points Rewards
- Follows
- Cheers
- Subscriptions
- Subscription Gifts
- Raids

## Actions
You can set up in the configuration files any set of actions for each of the events above.  
You may use any of the following actions:

### Spawning entities
Command: `SPAWN <Entity Name>`  
Optional arguments: `[Amount] [Target Player]`  

Example action command: `SPAWN Creeper 5 GospelBG`

This action will spawn a certain number (by default 1) of the specified entity to the target player, if specified. If the field is ommited, it will apply to all targeted players

### Giving items
Command: `GIVE <Item Name>`  
Optional arguments: `[Amount] [Target Player]`

Example action command: `GIVE Diamond 1`

This action will give an item. It an amount is not set, players will recieve just 1 item. If no specific player is set, items will be given to all targeted players

### Giving potion effects
Command `EFFECT <Effect Name> <Strength> <Duration (in seconds)>`
Optional arguments: `[Target Player]`

Example action command: `EFFECT SPEED 2 60`

This action will apply a potion effect to all players, or just to a specific one, if a Target Player is set in the command.

### Removing items
Command: `REMOVE <"ALL" / "RANDOM" / "HAND">`
Optional arguments: `[TARGET PLAYER]`

This action removes a single/all iems from a player's inventory, if a Target Player is specified. Otherwise this action will be performed on all targeted players.

### Inventory shuffling
Command: `SHUFFLE <"ALL" / Target Player>`

This action shuffles the position of all items of a player's inventory.

### Running commands
Command: `RUN <Player to run as / "TARGET" / "CONSOLE"> <Command>`  

This action will run a command as the server console, a specific target player, or as every targeted player on the server (with the [Target Permission](permissions.md/#target) set).  

Example action command: `RUN CONSOLE tp @a GospelBG`

### Explosions
Command: `TNT <Amount>`
Optional arguments: `[Fuse Time (ticks)] [Target Player]`

This action will spawn an exploding TNT that will explode in the specified amount of ticks (if set to 0, it will explode instantly).

Example action command: `TNT 3 0 GospelBG`

### Miscellaneous
#### Delays
Command `WAIT <Seconds>`

This action will stop the execution of an event's actions for the specified amount of time, before running the next action in the list.

#### Custom in-game message
Command `CUSTOM_MSG <Message>`

This action will override the default in-game alert message set in the localizations file with the specified message. To display a title splash message with a subtitle, use `\n` to split your message. This will be ignored and ommited in chat alert messages.  
You may use any Color Code to format your message

## Configuration Examples
You must set your actions in your Twitch configuration file as shown:
### Follow Events
For follow events, there is no threshold or condition to be met, and for this reason actions for follow event must be set as a list directly inside `FOLOW_REWARDS`.  
You still can set streamer-specific actions, in the same way as it's done for any other event type

Example:
```yaml
FOLLOW_REWARDS:
    - SPAWN CREEPER 1
    - EFFECT BLINDNESS 1 5
```

Example with streamer-specific actions
```yaml
FOLLOW_REWARDS:
    gospelbg:
        - GIVE DIAMOND 1
    default:
        - SPAWN CREEPER 1
        - EFFECT BLINDNESS 1 5
```

### Other Events
Example:
```yaml
CHANNEL_POINTS_REWARDS:
    Something is missing!:
        - SHUFFLE ALL
        - DELETE RANDOM
    Waterdrop!:
        - RUN TARGET /tp ~ ~100 ~
        - GIVE WATER_BUCKET
```

Example with streamer-specific actions:
```yaml
GIFT_REWARDS:
    1:
        Steve:
            GIVE Diamond 1 Steve
    5:
        Alex:
            DELETE ALL Alex
    100:
        TNT 10 1
```