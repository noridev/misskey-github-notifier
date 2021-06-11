# misskey-github-notifier
GitHub notifier for Misskey based client

----------------------------------------------------------------

*1.* Configure
----------------------------------------------------------------

### Created inside the .config folder

Copy and edit example.json
```
cp example.json config.json
```

or you can create your own.

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
