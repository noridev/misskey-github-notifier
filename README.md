# misskey-github-notifier
GitHub notifier for Misskey based client

## Configuration
Make a file called `config.json` and put your JSON into it to configure the bot.

### GitHub webhook
1. Go to the settings of your repo -> Webhooks -> Add Webhook
2. For Payload URL, put the URL or IP you'll be hosting the bot on followed by `/github`
3. For content type, select `application/json`
4. Make a random string of characters (~25 chars) and put it under Secret. Put the same string under `hookSecret` in `config.json`.

### Misskey bot
1. Go to a bot-friendly Misskey instance and make a new account. Put the instance URL (including the https:// part) under `instance` in `config.json`. Please mark the account as a bot.
2. On the profile, hit the 3 dots -> Edit Profile 
3. Go to API -> Generate Token
4. Put the token into `i` in `config.json`

### Config schema

``` json
{
	"port": 3001,
	"proxy": "",
	"hookSecret": "",
	"i": "",
	"instance": ""
}
```

- **port**: Port on listen for webhooks

- **hookSecret**: Webhook secret key from GitHub repository

- **i**: CherryPick(or Misskey based client)'s user API token to post events

- **instance**: URL of the instance to publish (do not include /)

*2.* Build and run
----------------------------------------------------------------

### 1. Install dependencies
	 
`npm i`

### 2. Build

`NODE_ENV=production yarn build`

### 3. Run

`NODE_ENV=production npm start`

### 4. Done!
Now, whenever a new event occurs in the GitHub repository, a note is published by the specified user!
