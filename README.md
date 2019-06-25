# french_anti-spam_discord-js
A french package for discord js to prevent spamming

## npm install --save AlthaelFR/french_anti-spam_discord-js#master

```js
const Discord = require('discord.js');
const antispam = require('anti-spam-discord'); // A besoin de ce module.
const client = new Discord.Client();
 
client.on('ready', () => {
  // Configuration de l'anti-spam
   antispam(client, {
        warnBuffer: 3, // Message maximum autorisé dans l'intervale séléctionnée avant de se faire avertir.
        maxBuffer: 5, // Message maximum autorisé dans l'intervale séléctionnée avant de se faire ban.
        interval: 2000, // Intervalle en ms. 
        maxDuplicatesWarning: 7,// Nombre de message dupliqués maximum avant de se faire avertir.
        maxDuplicatesBan: 10, // Nombre de message dupliqués maximum avant de se faire ban.
        deleteMessagesAfterBanForPastDays: 7, // Supprime les messages du membres depuis en jours.
      });
      
  // Reste de ton code //
});
 
client.on('message', msg => {
  client.emit('checkMessage', msg); // Va vérifier qu'il ne spam pas.
  
  // Reste de ton code //
}
 
client.login('token');
```
