# Running hubot on your RockOnPi 

Hubot is a robot that you can easily code for RocketOnPi.

On your Pi server, hubot can easily:

* listen to messages on any Rocket.Chat channel - perhaps for commands
* send messages to any Rocket.Chat channel - perhaps to report status
* interface with almost ANYTHING you have connected to your Pi - anything that can be interface via node.js

Please see [hubot](https://hubot.github.com/) for background information.


### STEPS

##### INSTALL hubot

1. register a new user named bot on your Rocket.Chat, set its password, you can also set its avatar if you like
1. login as your pi user, use another console session from the running Rocket.Chat;  you have 4 cores on a Pi 2, most hubot scripts use very few CPU cycles
1. add the binary path `PATH=$PATH:$HOME/meteor/dev_bundle/bin`
1. install hubot generator via `sudo npm install -g yo generator-hubot`; this will take quite a while on a Pi 2
1. now generate a new hubot with `yo hubot` - and then answer the questions; this will generate a hubot in the hubot directory
1. `cd hubot` and take a look at all the scripts in the `scripts` directory; you can add any new hubot scripts here
1. setup your environment variables, according to hubot-rocketchat requirements, see [hubot-rocketchat](https://github.com/RocketChat/hubot-rocketchat)   -- for example:
```
export ROCKETCHAT_ROOM=''
export LISTEN_ON_ALL_PUBLIC=true
export ROCKETCHAT_USER=bot
export ROCKETCHAT_PASSWORD=<your bot user password>
export ROCKETCHAT_AUTH=password
```

#####  Run hubot
1.  now run your hubot, it will log the bot user into your Rocket.Chat and start it listening to commands:   `bin/hubot -a rocketchat`
1.  login to Rocket.Chat (not as bot), and issue the command `bot help` in GENERAL,  the bot should reply with a list of commands that it knows;  congrats, you now have HubotOnPi running!

#####  Bot away!
1.  the only information you'll need to create your own powerful bot is on [this single page](https://github.com/github/hubot/blob/master/docs/scripting.md) ;  you will not need to know Rocket.Chat programming at all
2.  any new hubot you write and placed into the `scripts` subdirectory will be automatically activated the next time you start hubot

#####  Next steps
It is an open world of possibilities, limited only by your imagination.

For me personally, it is an intermediate step in integrating my on-board Raspberry Pi camera with Rocket.Chat.  I'll be writing up a bot that takes a command similar to `bot snappix`  and shell out to take and post a picture to the channel.    So remote monitoring of a room at home, anywhere from my mobile phone, will become a breeze.


