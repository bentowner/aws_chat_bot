# Quickstart to Building Bots on AWS
I summarized the info provided on <a href="">Create and Deploy a Chat Bot to AWS Lambda in Five Minutes!</a>



## Prerequisites

The Claudia Bot Builder works with the Node.JS 4.3.2 AWS Lambda installation. It requires using the Claudia.JS deployment tool, which you can install using NPM:  
 
```bash
npm install claudia -g
```
The Claudia Bot Builder support requires version 1.4.0 or later.

## Creating a simple text bot

Create a new folder, then, add the claudia-bot-builder library as a project dependency:
```bash
npm init
npm install claudia-bot-builder -S
```

For this particular bot, generate some dynamic content using the huh excuse generator. Add that as a project dependency:
Bash
```bash
npm install huh -S
```
Now create the bot. Create a file called bot.js and paste the following content:
JavaScript
```javascript
var botBuilder = require('claudia-bot-builder'),
    excuse = require('huh');

module.exports = botBuilder(function (request) {
  return 'Thanks for sending ' + request.text  + 
      '. Your message is very important to us, but ' + 
      excuse.get();
});
```

That’s pretty much it. You can now deploy the bot to AWS and configure it for Facebook Messenger, by using Claudia:
Bash
```bash
claudia create --region us-east-1 --api-module bot --configure-fb-bot
```

Now would be a good time to configure a new Facebook page and a messenger application, as explained in the <a href="https://developers.facebook.com/docs/messenger-platform/quickstart"> Facebook Messenger Getting Started Guide</a>. 

## Deploying to other platforms

The Claudia Bot Builder can also help you set up this bot for all the other platforms. Just run claudia update and provide the additional configuration option:

+ For Slack slash commands, use –configure-slack-slash-command
+ For Skype, use –configure-skype-bot
+ For Telegram, use –configure-telegram-bot

	