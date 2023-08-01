# <samp>DiscordJS-V14-Bot-Template</samp>

The simplified Discord bot commands & events handler built with discord.js version 14 and written in JavaScript. This handler can load up to 4 different type of commands; Prefix, Slash, User context and Message context.

- The prefix commands are normal message commands that only starts with a specific guild prefix. By default, it's the prefix provided in the `config.js` file.
- The slash commands are built-in Discord commands and are more simplified than prefix commands. The prefix is always `/`.
- The user commands are built-in Discord commands, and to execute a user command, right-click on a Discord user profile, Apps, and then select a command.
- The message commands are built-in Discord commands, and to execute a message command, right-click on a message, Apps, and then select a command.

This project also handles components. For now, there are only Buttons and Select menus.

Did you like my project? Click on the star button (⭐️) right above your screen, thank you!

## Commands, events, and components structure

> **Note**
> This handler uses **CommonJS** modules system.

### Prefix:
```ts
module.exports = {
    structure: {
        name: string,
        description: string,
        aliases: string[],
        permissions: PermissionFlagBits
    },
    run: async (client, message, args) => Promise<void>
};
```

### Slash/User/Message:
```ts
module.exports = {
    structure: SlashCommandBuilder | ContextMenuCommandBuilder,
    run: async (client, interaction) => Promise<void>
};
```

### Event:
```ts
module.exports = {
    event: string,
    once?: boolean,
    // '...args' are the arguments of the event chosen (from discord.js).
    run: async (client, ...args) => Promise<void>
};
```

### Component:
```ts
module.exports = {
    customId: string,
    run: async (client, interaction) => Promise<void>
};
```

## Requirements
### Packages:
- **chalk** v2.4.2
- **discord.js** v^14.11.0
- **dotenv** v^latest
- **mongoose** v^latest

### Platforms:
- **Node.js** v^16.9.0

```
npm init -y
npm i chalk@2.4.2 discord.js@14 dotenv mongoose
```

## Setup
1. Install Visual Studio Code.
2. Download this project as a **.zip** file: [Click here](https://github.com/TFAGaming/DiscordJS-V14-Bot-Template/archive/refs/heads/main.zip)
3. Extract the .zip file into a normal folder.
4. Open VSCode, click on **Open Folder**, and select the new created folder.
5. Go to `src/` and rename `example.config.js` to `config.js` and fill all the required values.

```ts
client: {
  token: string, // <= Your bot token
  id: string // <= Your bot ID
},
handler: {
  prefix: string, // <= The bot prefix
  deploy: boolean, // <= Always load application commands to Discord? (true: Yes, false: No)
  commands: { // Toggle commands; true: Enable, false: Disable
    prefix: boolean, // <= Toggle prefix commands
    slash: boolean, // <= Toggle slash commands
    user: boolean, // <= Toggle user commands
    message: boolean // <= Toggle message commands
  },
  mongodb: { // MongoDB database
    uri: string, // <= Your MongoDB URI string,
    toggle: boolean // <= Connect to the database or not? (true: Yes, false: No)
  }
}
```

You can use ENV instead of `config.js` to keep your bot token and ID and your MongoDB URI in a safe place. Rename the file `.env.example` to `.env` and fill all the required values.

```apache
CLIENT_TOKEN = Your bot token
CLIENT_ID = Your bot ID
MONGODB_URI = Your mongodb URI string
```

6. To start your bot, run `node .` or `npm run start`.
7. Enjoy. =)

## Support
Join our Discord server if you need any help!

<a href="https://discord.gg/6xpF6YqVDd">
  <img src="https://discord.com/api/guilds/871642960188571709/widget.png?style=banner3">
</a>

## License
**GPL-3.0**, General Public License v3