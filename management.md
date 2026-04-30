# 🛡️ Management & Configuration

Moderation commands and administrative settings. Most of these commands require the **Manage Roles** permission.

## ⚙️ Initial Setup

### 1. Set Language
Use `/language` to select the bot's interface language.
*   **Permission:** Requires **Administrator** permission.
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

## ⚔️ Killboard Notifications

Configure real-time tracking of kills and deaths for guilds and alliances.
*   **Channel:** `/albion_killboard channel` - Set the target text channel.
*   **Tracking:** `/albion_killboard add` / `/albion_killboard remove` - Manage tracked entities.
*   **Overview:** `/albion_killboard status` - View current settings.
*   For more details, see the [Killboard Guide](killboard.md).

## 📋 Whitelisting

Whitelist guilds and alliances to automatically give members roles and tags. Commands in this group require the **Manage Roles** permission.

*   **Guilds:** `/albion_guild add` / `/albion_guild list` / `/albion_guild remove` / `/albion_guild edit`
*   **Alliances:** `/albion_alliance add` / `/albion_alliance list` / `/albion_alliance remove` / `/albion_alliance edit`

> ℹ️ **Tag Length Limit:** Guild and Alliance tags are limited to a maximum of **7 characters**.

> ℹ️ **Automated Cleanup:** When you remove a guild or alliance from the whitelist, the bot will automatically prompt you to decide whether to remove or keep the users registered under that entity.

## 🛠️ User Management

Manage registered users directly without requiring them to perform actions. These commands require the **Manage Roles** permission.

*   **List:** `/albion_manage list [region] [member] [albion_guild]`
    *   **Description:** View all registrations for a specific Albion region.
    *   **Filters:** You can filter results by a specific Discord **member** or an **Albion guild name**.
*   **Update:** `/albion_manage update [region] [member]`
    *   **Description:** Force a data refresh for a specific user. This will re-check their current Albion guild/alliance, update their roles, and sync their nickname if enabled.
*   **Delete:** `/albion_manage delete [region] [member]`
    *   **Description:** Manually unregister a user from the bot. This removes their linked Albion data and any roles assigned by the bot.
*   **Register:** `/albion_manage register [region] [member] [albion_player]`
    *   **Description:** Register a user on their behalf. You can provide the **Albion Nickname** or the **Player ID**. If multiple players match a nickname, a selection menu will appear.

## 🚫 Blacklist

Prevent specific users, guilds, or alliances from interacting with the bot. Commands in this group require the **Manage Roles** permission.

*   **Add:** `/albion_blacklist add` - Search for a character, guild, or alliance to block. Optionally provide a `discord_id` and `reason`.
*   **Edit:** `/albion_blacklist edit` - Update an existing blacklist entry's reason or associated Discord member.
*   **Remove:** `/albion_blacklist remove` - Unblock an entity.
*   **List:** `/albion_blacklist list` - See all current blocks for a region.
*   **Show:** `/albion_blacklist show` - View detailed information about a specific entry, including who added it and when.

> ℹ️
> When adding a blacklist entry, you can now provide an optional **Discord ID**. If provided, the bot will show the linked user in the blacklist details and it serves as additional metadata for administrators.

## 🗺️ Map Editing

Administrators can update resource levels for Avalon maps to keep information current.

*   **Command:** `/ava edit map_name:MapName ...`
    *   **Permission:** Restricted to an **Authorized ID List**.

## 🔐 Permissions & Access

To ensure security and proper management, the bot follows these permission rules. Use the table below to determine which role or permission you need to execute specific commands.

### Permissions Table

| Command Group | Required Discord Permission | Notes |
| :--- | :--- | :--- |
| `/language` | **Administrator** | Changes the bot's interface language for the entire server. |
| `/albion_setup` | **Manage Roles** | Configures registration, nickname sync, and maintenance. |
| `/albion_guild` | **Manage Roles** | Manages the whitelisted Albion guilds. |
| `/albion_alliance` | **Manage Roles** | Manages the whitelisted Albion alliances. |
| `/albion_manage` | **Manage Roles** | Administrative control over registered users. |
| `/albion_blacklist`| **Manage Roles** | Manages the server-wide blacklist. |
| `/albion_killboard`| **Manage Server** | Configures and manages killboard tracking. |
| `/ava edit` | **Authorized ID List** | Restricted to specific users defined in the bot config (`ALLOWED_EDIT_IDS`). |
| `/broadcast` | **Bot Owner Only** | Restricted to the global Bot Owner ID (now uses a Modal form). |

### Key Requirements

1.  **Server Administration:** Commands requiring **Manage Roles** or **Administrator** are generally accessible to the Server Owner and any user with those specific permissions.
2.  **Guild Context:** All administrative and configuration commands must be used within a Discord Server (Guild). They will not work in Direct Messages (DMs).
3.  **Role Hierarchy:** For the bot to manage roles or nicknames, the **"Albion Assistant"** role must be positioned **higher** than the roles it is trying to assign or the users it is trying to manage in the Discord Server Settings.
4.  **Admin & Owner Accounts:** The bot **will fail** to add/remove roles or change nicknames for the **Server Owner** or users with **Administrator** permissions. This is due to Discord's built-in security hierarchy, which prevents any user (including bots) from modifying accounts with higher or maximum administrative privileges.
5.  **Authorized Map Editors:** The `/ava edit` command is not tied to Discord permissions but to a hardcoded list of Discord User IDs in the bot's environment variables.

---

> ⚠️ If a command fails despite you having the correct permissions, check the **Integration Settings** in your Server Settings to ensure Discord hasn't overridden the bot's default command permissions.

---

> ⚠️ These commands require **Manage Roles** permissions in the Discord server (some may still require Administrator depending on Discord's internal override).

---

[⬅️ Back to Home](index.md)