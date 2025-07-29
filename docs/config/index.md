# Plugin Configuration
## File location
Your configuration file (from now on, config.yml) is located in the ChatPointsTTV folder inside your plugins folder of your server.  
In other words, your config.yml file should be located in `plugins/ChatPointsTTV/config.yml`.

You may also notice there is a libs folder. It contains the plugin's dependencies, which are downloaded at runtime the first time the server runs with the plugin. Please do not remove it, otherwise the plugin will need to re-download them again the next time your server boots up.

## Configuration File
|         Key        | Description | Default
| ------------------ | ----------- | -------
| `CHANNEL_USERNAME` | Streamer channel(s)
| `CUSTOM_CLIENT_ID` | A custom ClientID that will be used to authenticate without login prompts (optional)
| `CUSTOM_ACCESS_TOKEN` | Generated Access Token to be used to authenticate without login prompts (optional)
| `AUTO_LINK_CUSTOM` | Whether the plugin should automatically try to authenticate using custom credentials when starting. <br> Allowed values: `true`, `false` | `true`
| `IGNORE_OFFLINE_STREAMERS` | Whether to ignore all events coming from offline streamers. <br> Allowed values: `true`, `false` | `false`
| `SHOW_CHAT` | If enabled, the stream chat will be displayed in the in-game chat (only for players with the [broadcast permission]()) <br> Allowed values: `true`, `false` | `true`
| `CHANNEL_POINTS_REWARDS` | Events related to Channel Point Redemptions. See further information in [Event Configurations](events_and_actions.md).
| `FOLLOW_REWARDS` | Events that will run whenever the streamer gets a new follower. See further information in [Event Configurations](events_and_actions.md).
| `CHEER_REWARDS` | Events related to Bit Cheering. See further information in [Event Configurations](events_and_actions.md).
| `SUB_REWARDS`| Events related to Subscriptions. See further information in [Event Configurations](events_and_actions.md).
| `GIFT_REWARDS` | Events related to Gifted Subscriptions. See further information in [Event Configurations](events_and_actions.md).
| `RAID_REWARDS` | Events related to Raids. See further information in [Event Configurations](events_and_actions.md).
| `MOB_GLOW` | If enabled, spawned mobs will have a permanent glow effect <br> Allowed values: `true`, `false` | `true`
| `DISPLAY_NAME_ON_MOB` | Whether spawned mobs will have the chatter's username displayed over their head. <br> Allowed values: `true`, `false`. | `true`
| `LOG_EVENTS` | If set to true, all events will be logged in a message in the server console. <br> Allowed values: `true`, `false` | `true`
| `INGAME_ALERTS` | Determines how should events display for players with the [broadcast permission](). <br> Allowed values: `none`, `chat`, `title`, `all` | `chat`
| `REWARD_NAME_BOLD` | Whether the event name should be displayed in bold in the in-game alerts. <br> Allowed values: `true`, `false`| `true`
| `COLORS` | Set the color for usernames and events for in-game alerts. <br> Allowed values: `AQUA`, `BLACK`, `BLUE`, `DARK_AQUA`, `DARK_BLUE`, `DARK_GRAY`, `DARK_GREEN`, `DARK_PURPLE`, `DARK_RED`, `GOLD`, `GRAY`, `GREEN`, `LIGHT_PURPLE`, `RED`, `WHITE`, `YELLOW` | [See template file](https://github.com/GospelBG/ChatPointsTTV/blob/b34fa4b71d46f934cafd37487b45d6cb6acaa92d/core/src/main/resources/config.yml#L106)
| `STRINGS` | This configuration section allows you to customize or translate the alert strings. | [See template file](https://github.com/GospelBG/ChatPointsTTV/blob/b34fa4b71d46f934cafd37487b45d6cb6acaa92d/core/src/main/resources/config.yml#L113)

