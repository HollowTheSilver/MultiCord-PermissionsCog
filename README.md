# MultiCord Permissions Cog

Enterprise-grade hierarchical permission system for Discord bots with intelligent role detection.

## Features

- **9-Level Permission Hierarchy** - From `BANNED` (-1) to `BOT_OWNER` (200)
- **Intelligent Role Auto-Detection** - Automatically classifies and configures roles
- **Unicode Text Normalization** - Handles fancy Discord names with special characters
- **Guild-Specific Overrides** - Customize permissions per server
- **Audit Logging** - Complete trail of permission changes
- **Optional Database Persistence** - SQLite support with in-memory fallback

## Quick Start

```bash
# Install into a bot
multicord bot cog add permissions my-bot

# Restart the bot to load
multicord bot run my-bot
```

## Permission Levels

```
BOT_OWNER (200)     - Bot owner (highest authority)
BOT_ADMIN (150)     - Bot administrators (cross-server)
OWNER (100)         - Server owner / top administrators
LEAD_ADMIN (90)     - Senior administrators
ADMIN (80)          - Basic administrators
LEAD_MOD (65)       - Senior/Lead moderators
MODERATOR (50)      - Basic moderators
MEMBER (10)         - Trusted members, VIPs
EVERYONE (0)        - Default level (all members)
BANNED (-1)         - Explicitly banned from commands
```

## Commands

```
/permissions auto-configure    - Auto-detect and configure all roles
/permissions set-role @Role LEVEL   - Set a role's permission level
/permissions list-roles        - List all configured roles
/permissions check @User       - Check a user's permission level
```

## Configuration

Configure in your bot's `config.toml`:

```toml
[permissions]
use_database = true
db_path = "data/permissions.db"
```

## Required Permissions

- **Send Messages** - Send responses
- **Embed Links** - Rich embeds for info displays
- **Manage Roles** - Role classification

## License

MIT License - see [LICENSE](LICENSE)
