# 🛡️ Management & Configuration

Administrator-only commands to set up the bot and moderate the server.

## ⚙️ Initial Setup

### 1. Set Language
Use `/language` to select the bot's interface language.
*   **Supported:** English (en), Spanish (es), French (fr), Italian (it), Portuguese (pt), Brazilian Portuguese (pt-br), Russian (ru), Turkish (tr), German (de).

### 2. Configure Registration
Use `/albion_setup config` to define how registration works.
*   **Public Registration:** Allow everyone to register or restrict to whitelisted guilds.
*   **Nickname Sync:** Automatically change Discord nicknames to match Albion character names.
*   **Tag Display:** Customize how [GUILD] and [ALLIANCE] tags appear in nicknames.

## 📋 Whitelisting

Whitelist guilds and alliances to automatically give members roles and tags.

*   **Guilds:** `/albion_guild add` / `/albion_guild list` / `/albion_guild remove`
*   **Alliances:** `/albion_alliance add` / `/albion_alliance list` / `/albion_alliance remove`

## 🛠️ User Management

Manage registered users directly without requiring them to perform actions.

*   **List:** `/albion_manage list` - View all registrations with optional member/guild filters.
*   **Update:** `/albion_manage update` - Force a data refresh and role/nick sync for a user.
*   **Delete:** `/albion_manage delete` - Manually unregister a user.
*   **Register:** `/albion_manage register` - Register a user on their behalf using Nickname or Player ID.

## 🚫 Blacklist

Prevent specific users, guilds, or alliances from interacting with the bot.

*   **Add:** `/albion_blacklist add`
*   **Remove:** `/albion_blacklist remove`
*   **List:** `/albion_blacklist list`

## 🗺️ Map Editing

Administrators can update resource levels for Avalon maps to keep information current.

*   **Command:** `/ava edit map_name:MapName ...`

---

> [!WARNING]
> These commands require **Administrator** permissions in the Discord server.
