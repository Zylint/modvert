# Modvert-Zylint

A powerful Discord moderation bot with a simple configuration system.

## Features

- Server Setup & Configuration
- Moderation Commands (kick, ban, mute, etc.)
- Temporary Ranks
- Channel Lockdown
- Warning System
- Message Snipe
- Logging System
- Welcome Messages

## Setup Guide

### Prerequisites

1. Node.js v16.9.0 or higher
2. A Discord Bot Token
3. Administrator permissions in your Discord server

### Installation

1. Clone this repository
2. Install dependencies:
```bash
npm install
```
3. Configure the bot:
   - Add your bot token to `src/data/botConfig.json`:
   ```json
   {
       "token": "your-bot-token-here"
   }
   ```
   - Run the bot: `npm start`
   - Use `/setup` command to configure the bot in your server

### Required Permissions

The bot needs these permissions:
- Administrator (recommended)
Or these individual permissions:
- Manage Roles
- Manage Channels
- Kick Members
- Ban Members
- Manage Messages
- View Channels
- Send Messages
- Read Message History

## Commands

### Setup
- `/setup`
  - Sets up: Mod role, Log channel, Welcome channel (optional)
  - Requires: Administrator

### Moderation
- `/kick <user> [reason]`
  - Kicks a user
  - Requires: Kick Members or Mod Role

- `/ban <user> [reason] [deleteMessages]`
  - Bans a user
  - Optional: Delete 1-7 days of messages
  - Requires: Ban Members or Mod Role

- `/mute <user> <duration> [reason]`
  - Mutes a user temporarily
  - Duration format: 1h, 1d, etc.
  - Requires: Moderate Members or Mod Role

- `/warn <user> <reason>`
  - Warns a user
  - Logs warning in database
  - Requires: Mod Role

- `/temprank <user> <role> <duration>`
  - Gives temporary role
  - Automatically removes after duration
  - Requires: Manage Roles or Mod Role

- `/lockdown <type> [target] [reason]`
  - Locks channel, category, or server
  - Types: channel, category, server
  - Requires: Manage Channels or Mod Role

- `/purge <amount> [user]`
  - Deletes messages (1-100)
  - Can target specific user
  - Requires: Manage Messages or Mod Role

### Information
- `/serverinfo`
  - Shows server details
  - No special permissions needed

## Troubleshooting

### Common Issues

1. Bot Won't Start
   - Check token in botConfig.json
   - Verify Node.js version (16.9.0+)
   - Run npm install again

2. Commands Not Working
   - Verify bot permissions
   - Check role hierarchy
   - Look for console errors
   - Check log channel

3. Permission Errors
   - Ensure bot role is high enough
   - Verify channel permissions
   - Check moderator role setup

### Error Messages

- "Interaction Failed": Check permissions and syntax
- "Not Configured": Run /setup first
- "Missing Permissions": Check user/bot permissions

## License

This project uses a custom license that:
- Prohibits any commercial use
- Requires attribution
- Allows free use and modification for non-commercial purposes
- Requires sharing modifications under the same terms

See the [LICENSE](LICENSE) file for full terms.

## Contributing

Feel free to:
1. Fork the repository
2. Create a feature branch
3. Submit a pull request

Note: All contributions must follow the license terms.

## Support

For support:
1. Check this documentation
2. Review console logs
3. Open a GitHub issue with:
   - Error messages
   - Steps to reproduce
   - Bot configuration
