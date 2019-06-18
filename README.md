# french_anti-spam_discord-js
A french package for discord js to prevent spamming

```js
const antispam = require('anti-spam-discord');
antispam(client, {
    warnBuffer: 3, // Maximum ammount of messages allowed to send in the interval time before getting warned.
    maxBuffer: 5, // Maximum amount of messages allowed to send in the interval time before getting banned.
    interval: 2000, // Amount of time in ms users can send the maxim amount of messages(maxBuffer) before getting banned. 
    maxDuplicatesWarning: 7,// Maximum amount of duplicate messages a user can send in a timespan before getting warned.
    maxDuplicatesBan: 10, // Maximum amount of duplicate messages a user can send in a timespan before getting banned.
    deleteMessagesAfterBanForPastDays: 7, // Deletes the message history of the banned user in x days.
});
```
