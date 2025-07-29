# Commands
The plugin is controlled with the `/twitch` command followed by one of the next arguments:

## Link
Generates a Twitch Device Code and starts the linking process.  

Example:
```
/twitch link
```

## Accounts
Displays a menu showing all connected accounts, with buttons to unlink accounts and stop the Twitch client.
TODO: add screenshot

Example:
```
/twitch accounts
```

## Start
Starts the Twitch Client and connects automatically to the previous accounts using the saved credentials. Otherwise, you will need to [link an account](#link).

Example:
```
/twitch start
```

## Stop
Stops the Twitch Client. This will disconnect you from the Twitch API and stop any incoming events. Your current account credentials will be saved and used the next time the Twitch Client starts.

Example:
```
/twitch stop
```

## Unlink
Unlinks all Twitch accounts and removes the stored credentials. You may pass an extra argument with a linked user name to unlink only that account.  
To temporally disconnect from Twitch's API, use [the stop command](#stop).

Example:
```
/twitch unlink GospelBG
```

## Status
Displays an information message about connection status, plugin version, listened an live channels and connected account.

Example:
```
/twitch status
```

## Reload
Resets the plugin and refreshes the configuration files.  

Example:
```
/twitch reload
```

## Test

* `/twitch test <event type> <...>`  
    Sends a custom test event locally. It is useful for testing your configuration.  
    
    **Valid event types**:  
    `channelpoints`, `cheer`, `follow`, `raid`, `sub`, `subgift`  

### Channel Points
Sends a custom Channel Points Redemption event. You can input the chatter and streamer user names, as well as adding a user input message.
Syntax: `/twitch test channelpoints <chatter username> <streamer username> <reward name> [user input]`

If you have a reward name that contains whitespaces you should enclose it with double quotes

Example:
```
/twitch test channelpoints gospelbg rubius "Blow me up!"
```

```
/twitch test channelpoints gospelbg rubius "Rename my current item" "The Un-aliver"
```

### Cheer
Sends a custom Cheer event. You can set a custom amount of Bits, as well as the cheerer and the streamer username.
Syntax: `/twitch test cheer <cheerer username> <streamer username> <bits>`

Example:
```
/twitch test cheer gospelbg kaicenat 500
```

### Follow
Sends a custom Follow event.  
Syntax: `/twitch test follow <follower username> <streamer username>`

Example:
```
/twitch test follow gospelbg mrbeast6000
```

### Raid
Sends a custom Raid Event with the specified amount of viewers.  
Syntax: `/twitch test raid <raider username> <streamer username> <viewer count>`
Example:
```
/twitch test raid gospelbg mrbeast6000 20000
```

### Subscription
Sends a custom subscription event.
Example:
```
/twitch test sub gospelbg mrbeast6000 TIER1
```

### Subscription Gift
Example:
```
/twitch test subgift gospelbg mrbeast6000 TIER1 10
```