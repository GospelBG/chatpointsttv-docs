To set permissions, the use of an external permissions plugin is required.  
ChatPointsTTV makes use of 3 permissions:

## Manage
It allows a player to run plugin commands (`/twitch`).  
By default, it is only granted to players with OP status.  

Permission ID: `chatpointsttv.manage`

## Broadcast
Players with this permission will recieve alert messages from incoming events in the form of chat messages and/or title screens. This behaviour can be set in the configuration files.  
By default, all players have this permission.  

Permission ID: `chatpointsttv.broadcast`

## Target
Players with this permission will be considered a "target player" when no target player is set in an action (or, in the case of `RUN` actions, it is set to `TARGET`).  
By default, no players have this permission and **must be set manually**.  

Permission ID: `chatpointsttv.target`