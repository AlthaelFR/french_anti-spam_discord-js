# french_anti-spam_discord-js
A french package for discord js to prevent spamming

## npm install --save AlthaelFR/french_anti-spam_discord-js#master

```js
const Discord = require('discord.js');
const antispam = require('anti-spam-discord'); // Requiring this module.
const client = new Discord.Client();
 
client.on('ready', () => {
  // Module Configuration Constructor
   antispam(client, {
        warnBuffer: 3, // Maximum ammount of messages allowed to send in the interval time before getting warned.
        maxBuffer: 5, // Maximum amount of messages allowed to send in the interval time before getting banned.
        interval: 2000, // Amount of time in ms users can send the maxim amount of messages(maxBuffer) before getting banned. 
        maxDuplicatesWarning: 7,// Maximum amount of duplicate messages a user can send in a timespan before getting warned.
        maxDuplicatesBan: 10, // Maximum amount of duplicate messages a user can send in a timespan before getting banned.
        deleteMessagesAfterBanForPastDays: 7, // Deletes the message history of the banned user in x days.
      });
      
  // Rest of your code
});
 
client.on('message', msg => {
  client.emit('checkMessage', msg); // This runs the filter on any message bot receives in any guilds.
  
  // Rest of your code
}
 
client.login('token');
```
