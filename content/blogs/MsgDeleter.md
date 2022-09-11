---
title: "MsgDeleter"
date: 2022-09-11T10:55:40+05:30
draft: false
tags: ["discord","discord.js"]
author: "Me"
---
# MessageDeleter Discord Bot

## I recently created a discord bot that deletes a user's messages using Discord.js

#### I had a lot of fun making the bot and it only took me couple of hours

You can find the code at its [Github](https://github.com/TheCoderSimp/MsgDeleter)

I got the idea when I was browsing [Stack Overflow](https://stackoverflow.com) and found a snippet of code that was:
```javascript
client.on('message', message => {
   if (message.content.startsWith("||say ")) {

      let input = message.content.split(" ").slice(1).join(" ") // Removes the prefix

      message.delete() // Deletes the message
      message.channel.send(input))//.then(msg=>msg.delete({timeout:"5000"}) <- if you want delete it with delay and sends the finished text
   }
});
```
### You can find the question and answer [here](https://stackoverflow.com/questions/45395255/discord-js-delete-single-message). I was nor the one to ask the question neither the one to answer it

I was interested by this and thought that I could use this to annoy my friends
So what I did what I used a boolean variable. Whenever the required command executed, the variable will become true/false accordingly.

#### So based on this, I wrote a if statement to check if the user is sending a message and if the boolean is true
```javascript
if(variableWhichICantName === true){
        if(message.author.username === config.username || !message.author.id === config.user_id){ 
//I used both user id and username cuz i was running into problems using just the user id
            message.delete()
            console.log(`${message.author.username} is messaging again`)
        }
    }
```

And yes.. the boolean variable's name is indeed variableWhichICantName 💀💀

Here is the if-else statements I used for the bot's on and off command

```javascript
if(message.content === `${config.prefix} on`){
        if(variableWhichICantName === true){
          message.reply("Command is already running")
        }else{
          variableWhichICantName = true
        message.reply("Ok I pull up 😤")
        console.log("Status:", variableWhichICantName)
        }
    }else if (message.content === `${config.prefix} off` && message.author.username !== config.username){
        // I used the message.author.username !== config.username so that I can ensure the person cannot execute the off command
        if(variableWhichICantName === false){
          message.reply("Command is not running")
        }else{
        variableWhichICantName = false
        message.reply("But I wanna pull up 😢 ||its off dw||")
        console.log("Status:", variableWhichICantName)
        }
    }
```

As we have reached the 69th line of this blog, I'll stop here XD.
# Farewell comrade (im not a communist)