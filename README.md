# PugBot for Discord

PugBot for discord is a bot for managing pickup games.

## Installing

### Pre-Requisites 
- You will need to create an AWS EC2 or similar linux box
  - Instuctions on getting started can be found here https://aws.amazon.com/ec2/
- You will also need to setup two (2) discord bots
  - Instructions on this can be found here https://discordpy.readthedocs.io/en/latest/discord.html
    - Two bots are needed; one is to run the pickup games and the other handles the banning/unbanning process
- Install all files and folders to your home directory
    
### Getting Started
- Create a mongoDB to hold the last pickup and server + alias information. If you are unsure how to do this, a quick start tutorial can be found at the link provided below.
- Setup the mongoDB by running `python3 ./mongodb.py`
  - You will need to modify this file to match your game configuration
- Rename `config.py.example` to `config.py`
  - You will need to modify this file to match your game and bot configurations
- Run the bot with the provided script `./runbot.sh`

## Requirements

- Python 3.5+
- [discord](https://github.com/Rapptz/discord.py)
- [pymongo](https://www.mongodb.com/blog/post/getting-started-with-python-and-mongodb)
- [requests](https://github.com/requests/requests)
