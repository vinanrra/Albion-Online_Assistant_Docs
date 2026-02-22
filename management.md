# 🛡️ Management & Configuration

Moderation commands and administrative settings. Most of these commands require the **Manage Roles** permission.

## ⚙️ Initial Setup

### 1. Set Language
Use `/language` to select the bot's interface language.
*   **Supported:** English (en), Spanish (es), French (fr), Italian (it), Portuguese (pt), Brazilian Portuguese (pt-br), Russian (ru), Turkish (tr), German (de), Korean (ko), Chinese (zh-cn), Vietnamese (vi), Danish (da).

### 2. Configure Registration
Use `/albion_setup config` to define how registration works.
*   **Public Registration:** Allow everyone to register or restrict to whitelisted guilds.
*   **Nickname Sync:** Automatically change Discord nicknames to match Albion character names.
*   **Tag Display:** Customize how [GUILD] and [ALLIANCE] tags appear in nicknames.

### 3. Automated Maintenance (Purge)
Define how the bot should handle users who are no longer in whitelisted guilds.
*   **Purge Modes:** Choose between **Full** (complete removal) or **Soft** (remove only specific roles).
*   **Role Priority:** Decide which role to keep if a user is in both a whitelisted guild and alliance.
*   **Log Channel:** Set a channel to receive real-time action logs and cycle reports.
*   For more details, see the [Purge System Guide](file:///home/vinanrra/Documents/Github/Albion-Online_Assistant_Docs/purge_system.md).

## 📋 Whitelisting

Whitelist guilds and alliances to automatically give members roles and tags.

*   **Guilds:** `/albion_guild add` / `/albion_guild list` / `/albion_guild remove` / `/albion_guild edit`
*   **Alliances:** `/albion_alliance add` / `/albion_alliance list` / `/albion_alliance remove` / `/albion_alliance edit`

> [!IMPORTANT]
> **Tag Length Limit:** Guild and Alliance tags are limited to a maximum of **7 characters**.

> [!NOTE]
> **Automated Cleanup:** When you remove a guild or alliance from the whitelist, the bot will automatically prompt you to decide whether to remove or keep the users registered under that entity.

## 🛠️ User Management

Manage registered users directly without requiring them to perform actions.

*   **List:** `/albion_manage list` - View all registrations with optional member/guild filters.
*   **Update:** `/albion_manage update` - Force a data refresh and role/nick sync for a user.
*   **Delete:** `/albion_manage delete` - Manually unregister a user.
*   **Register:** `/albion_manage register` - Register a user on their behalf using Nickname or Player ID.

## 🚫 Blacklist

Prevent specific users, guilds, or alliances from interacting with the bot.

*   **Add:** `/albion_blacklist add` - Search for a character, guild, or alliance to block. Optionally provide a `discord_id` and `reason`.
*   **Edit:** `/albion_blacklist edit` - Update an existing blacklist entry's reason or associated Discord member.
*   **Remove:** `/albion_blacklist remove` - Unblock an entity.
*   **List:** `/albion_blacklist list` - See all current blocks for a region.
*   **Show:** `/albion_blacklist show` - View detailed information about a specific entry, including who added it and when.

> [!NOTE]
> When adding a blacklist entry, you can now provide an optional **Discord ID**. If provided, the bot will show the linked user in the blacklist details and it serves as additional metadata for administrators.

## 🗺️ Map Editing

Administrators can update resource levels for Avalon maps to keep information current.

*   **Command:** `/ava edit map_name:MapName ...`

---

[⬅️ Back to Home](index.md)


---

> [!WARNING]
> These commands require **Manage Roles** permissions in the Discord server (some may still require Administrator depending on Discord's internal override).
