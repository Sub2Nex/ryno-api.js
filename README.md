![npm install](https://project.ryno-bot.xyz/404)<br/>
[Do you need my help? Visit our Discord server.](https://project.ryno-bot.xyz/support)

# Installation
```console
npm i ryno-api.js --save
yarn add ryno-api.js
```


# Usage
```js
const Topics = require('./ryno-api.index');
const dbl = new Topics("ryno-api Bot Token");


dbl.on("ready", (bot) => {
    console.log(`Bot named ${bot.username} successfully finded on Topics.`)
    dbl.checkVote("yourbotid").then(value => console.log("Vote Control: "+ value))

    /*
        let guildCount = 1234;
        let shardCount = 5;
        dbl.stats(guildCount, shardCount, () => console.log("Stats updated on Topics."));
    */
})


/*
    Get with Bot: 
    dbl.on("vote", ({ user, bot }) => {
        console.log(`${user.username} voted ${bot.username}`)
    })
*/
dbl.on("vote", ({ user }) => {
    console.log(`${user.username} voted.`)
})
```

# Detailed

### Define Module
```js
const Topics = require('./ryno-api.index');
const dbl = new Topics("ryno-api Bot Token");
```

### Let's add an event to see if it works.
```js
dbl.on("ready", (bot) => {
    console.log(`Bot named ${bot.username} successfully finded on Topics.`)
})

// => Bot named GithubBot successfully finded on Topics.
```

### Let's update bot data
```js
dbl.on("ready", (bot) => {
    console.log(`Bot named ${bot.username} successfully finded on Topics.`)
    let guildCount = 1234;
    let shardCount = 5;
    dbl.stats(guildCount, shardCount, () => console.log("Stats updated on Topics."));
})

// => Bot named GithubBot successfully finded on Topics.
// => Stats updated on Topics.
```

### Let's check if a user has voted.
```js
dbl.on("ready", (bot) => {
    console.log(`Bot named ${bot.username} successfully finded on Topics.`)
    dbl.checkVote("714451348212678658").then(value => console.log("Vote Control: "+ value))

    /*
        let guildCount = 1234;
        let shardCount = 5;
        dbl.stats(guildCount, shardCount, () => console.log("Stats updated on Topics."));
    */
})

// => Bot named GithubBot successfully finded on Topics.
// => Vote Control: false
```

### Let's check if there is a user who voted for our bot instantly.
```js
dbl.on("vote", ({ user }) => {
    console.log(`${user.username} voted.`)
})

// => GithubMaster1234 voted.
```
```js
// WITH BOT
dbl.on("vote", ({ user, bot }) => {
    console.log(`${user.username} voted ${bot.username}`)
})

// => GithubMaster1234 voted GithubBot.
```

---
<h6 align="center">Developed with 🐈 by The Ryno Project</h6>
