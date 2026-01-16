# 🛡️ Management & Configuration

Administrator-only commands to set up the bot and moderate the server.

## ⚙️ Initial Setup

### 1. Set Language
Use `/language` to select the bot's interface language.
*   **Supported:** English, Spanish, French, Italian, Portuguese (PT & BR), Russian.

### 2. Configure Registration
Use `/albion_setup config` to define how registration works.
*   **Public Registration:** Allow everyone to register or restrict to whitelisted guilds.
*   **Nickname Sync:** Automatically change Discord nicknames to match Albion character names.
*   **Tag Display:** Customize how [GUILD] and [ALLIANCE] tags appear in nicknames.

## 📋 Whitelisting

Whitelist guilds and alliances to automatically give members roles and tags.

*   **Guilds:** `/albion_guild add` / `/albion_guild list` / `/albion_guild remove`
*   **Alliances:** `/albion_alliance add` / `/albion_alliance list` / `/albion_alliance remove`

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
