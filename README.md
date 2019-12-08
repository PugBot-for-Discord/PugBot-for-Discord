# PugBot for Discord

PugBot for discord is a bot for managing pickup games.

## Installing

### Pre-Requisites 
- Create an AWS EC2 or similar linux box
  - Instuctions on getting started can be found here https://aws.amazon.com/ec2/
    - Once setup, install all files and folders to your home directory
- Create and setup two (2) discord bots
  - Instructions on this can be found here https://discordpy.readthedocs.io/en/latest/discord.html
    - Two bots are needed; one is to run the pickup games (token) and the other handles the banning/unbanning process (banHammerToken)
- Create a mongoDB to hold the last pickup and server + alias information. 
  - Instructions on this can be found here https://www.mongodb.com/blog/post/getting-started-with-python-and-mongodb
- Modify your discord server (discordServerID) to include the following channels/roles:
  - Channels:
    - admin channel (adminChannelID)
    - banned channel (bannedChannelID)
    - red team channel (redteamChannelID) - players on this team are moved to this channel once the game has begun
    - blue team channe (blueteamChannelID) - players on this team are moved to this channel once the game has begun
    - ready up channel (readyupChannelID) - players join this channel when pickup fills to prove they are present and ready
    - pickup chat channel (singleChannelID) - to avoid clutter in general chat, all pickup chatter happens in this channel
    - general chat channel (requestChannelID) - players can request access to the pickup chat channel through this channel
  - Roles:
    - admin role (adminRoleID) + (adminRoleMention) - role assigned to pickup admins
    - player role (playerRoleID) - role given to players when they have access to the pickup chat channel
    - pool role (poolRoleID) - role given to players when they add to the pickup
    - timeout role (timeoutRoleID) - role given to banned players 
    
### Getting Started
- Setup the mongoDB by running `python3 ./mongodb.py`
  - You will need to modify this file to match your game configuration
- Rename `config.py.example` to `config.py`
  - You will need to modify this file to match your game and bot configurations
- Run the bot with the provided script `./runbot.sh`

## Requirements

- Python 3.5+
- [discord](https://github.com/Rapptz/discord.py)
- [pymongo](https://api.mongodb.com/python/current/)
- [requests](https://github.com/requests/requests)
