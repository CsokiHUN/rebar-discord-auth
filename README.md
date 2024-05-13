# Discord Auth for Rebar Framework

this plugin allows a user to login and automatically register on your server with an discord ID.

they are required using discord

## Features
- Login and automatically register with Discord.
- Whitelist and server check with [Discord Integration](https://github.com/unfloned/rebar-discord)

## Requires
- [Rebar Framework](https://github.com/Stuyk/rebar-altv)

optional:
- [Discord Integration](https://github.com/unfloned/rebar-discord) when in config file is set:
    - SERVER_ID or 
    - WHITELIST_ROLE_ID


## API

if you need to listen for when a player is successfully logged in you can use the `discord-auth-api`


```ts
import * as alt from 'alt-server';
import { useRebar } from '@Server/index.js';

const Rebar = useRebar();
const api = Rebar.useApi();

function handleLogin(player: alt.Player) {}

async function init() {
    // Get the API
    const auth = api.getAsync('discord-auth-api');
    
    // Hook in your event
    auth.onLogin(handleLogin);
}

init();
```

## Installation

From the main directory of your `Rebar` Framework.

```
git clone https://github.com/unfloned/rebar-discord-auth.git src/plugins/discord-auth
```

check `server/config.ts` to fill up all information needed.

That's all.

if you wish to save the plugin in your own repository, go to `src/plugins/discord-auth` folder and delete the `.git` folder.

### Usage with [rebar-character-select](https://github.com/Stuyk/rebar-character-select)

just change from `auth-api` to `discord-auth-api` in `rebar-character-select/server/index.ts` line 223 and 224.