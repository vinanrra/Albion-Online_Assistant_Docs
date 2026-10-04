# 🛠️ Complete Setup Guide

This guide will walk you through the process of setting up the Albion Bot for your Discord server, from initial configuration to whitelisting and user registration.

## 1. Initial Configuration

Use the command `/albion_setup config` to launch the interactive configuration dashboard UI. The dashboard allows administrators to configure the following settings:

### ⚙️ Configuration Settings Explained

| Dashboard Setting | Description |
| :--- | :--- |
| **`public`** | **Allow everyone to register?**<br>• **Yes:** Anyone can link their Albion account. They will receive the `public_role` (if configured) even if they aren't in a whitelisted guild/alliance.<br>• **No:** Only members of guilds or alliances you've specifically whitelisted can register. |
| **`public_role`** | **Public Role**<br>The Discord role given to users who register if `public` is set to **Yes**. This helps identify registered "guest" users. |
| **`edit_nick`** | **Change nickname?**<br>If enabled, the bot will automatically change the user's Discord nickname to match their Albion character name (including optional tags). |
| **`nick_tag_order`** | **Tag Order**<br>Determines if the Alliance tag or Guild tag appears first. (e.g., `[ALLY][GUILD] Name` vs `[GUILD][ALLY] Name`). |
| **`nick_ally_tag`** | **Alliance Tag Display**<br>Choose who can see the alliance tag in nicknames (Everyone, Only members, or Don't show). |
| **`nick_ally_tag_length`** | **Alliance Tag Length**<br>The maximum characters for the alliance tag (1-7). |
| **`nick_guild_tag`** | **Guild Tag Display**<br>Choose who can see the guild tag in nicknames. |
| **`nick_guild_tag_length`** | **Guild Tag Length**<br>The maximum characters for the guild tag (1-7). |
| **`purge_users`** | **Automatic Cleanup?**<br>If enabled, the bot periodically audits users and maintains their roles/nicknames based on guild status:<br>• **Private Servers (`public: No`):** Purges any registered member who is not found in a whitelisted guild or alliance.<br>• **Hybrid Servers (`public: Yes`):** Preserves guest registrations (users registered without whitelisted guild/alliance affiliations), while actively detecting and purging former guild/alliance members who leave the whitelisted roster. |
| **`purge_mode`** | **Purge Behavior**<br>• **Full:** Strip all roles and reset nickname if user is not on any whitelist.<br>• **Soft:** Only remove specifically whitelisted roles, keeping the Public role and nickname. |
| **`purge_log_channel`** | **Log Channel**<br>A text channel where the bot will send detailed logs of every update/purge action taken, and a summary report after each cycle. |
| **`role_conflict`** | **Role Priority Mode**<br>How to handle users in both a whitelisted guild AND alliance:<br>• **Additive:** Give both roles.<br>• **Guild Only:** Prioritize guild role.<br>• **Alliance Only:** Prioritize alliance role. |

---

## ⚡ The "Public" vs "Purge" Interaction (Hybrid Server Support)

It is important to understand how these settings interact when automated maintenance is active.

### 🛡️ Private Servers (`public: No`)
If your server is private (`public: No`) and **`purge_users`** is **ENABLED**, the bot requires every registered member to be found on an active `/albion_guild` or `/albion_alliance` whitelist. Any registered member who leaves or is not part of a whitelisted guild/alliance will be purged according to your configured `purge_mode`.

### 🌐 Hybrid Public Servers (`public: Yes`)
If your server is public (`public: Yes`) and **`purge_users`** is **ENABLED**, the bot operates in **Hybrid Mode**:
* **Guest Registrations Preserved:** Community members who register without belonging to any whitelisted guild or alliance are recognized as guests. They keep their verification and `public_role` and will **NOT** be purged.
* **Leavers Detected & Purged:** If a user was previously registered as part of a whitelisted guild or alliance and subsequently leaves the roster, the bot actively detects their departure and purges them according to your configured `purge_mode`.

**Recommended Configuration:**
- **For Private/Guild Servers:** `public: No`, `purge_users: Yes`, `purge_mode: Full`.
- **For Open Servers (Community):** `public: Yes`, `purge_users: No`.
- **For Hybrid Hubs (Guild + Community Guests):** `public: Yes`, `purge_users: Yes`, `purge_mode: Soft` or `Full` (Guests remain registered, but former guild members lose access upon departure).

For a deep dive into the automated cleanup logic, see the [Purge System Guide](purge_system.md).


---

## 2. Whitelisting Guilds & Alliances

Whitelisting is how you tell the bot which Albion players belong to your community and which Discord roles they should receive.

### 🛡️ Whitelisting a Guild
Use `/albion_guild add` to add a guild to your whitelist.
1.  **Search:** Enter the name of the Albion Online guild.
2.  **Select Region:** Choose the region (Americas, Europe, or Asia).
3.  **Assign Role:** Select the Discord role that members of this guild should receive upon registration.
4.  **Tag:** Enter the tag to display in their nickname (max 7 characters, e.g., `TC` for The Coalition).

### 🤝 Whitelisting an Alliance
Similar to guilds, use `/albion_alliance add`. Members of any guild within the whitelisted alliance will receive the specified role and tag.

> ℹ️
> **Safe Cleanup:** Removing a guild or alliance will trigger an automated prompt asking if you want to perform a cleanup of the associated users (stripping roles and unregistering them).

### ⚔️ Setting up Killboard (Optional)
If you want to track kills and deaths for your guild, alliance, or specific players:
1.  Use `/albion_killboard panel` to open the control panel (requires **Manage Server** permission by default, unless configured otherwise via Discord Integrations).
2.  Use the green and red buttons to select the text channels for kills and deaths.
3.  Click **Add Tracking** to select the region/type and enter the players/guilds you want to monitor.

For more details, see the [Killboard Guide](killboard.md).

---

## 3. User Registration Process

Once you have configured the bot and whitelisted at least one guild or alliance, your members can begin registering.

1.  **The Command:** Users type `/albion_register start`.
2.  **Region & Nick:** They select their server region and type their exact Albion character name.
3.  **Character Selection:** If multiple characters have similar names, the user selects theirs from a menu.
4.  **Automatic Sync:** Success! The bot will now:
    *   Verify if they are in a whitelisted guild/alliance.
    *   Assign the corresponding Discord roles.
    *   (Optional) Update their nickname with the proper tags and capitalization.

---

## ℹ️ Pro Tips for Administrators

> ⭐ **Role Hierarchy & Permissions:** Ensure the bot's highest role is placed **above** the roles it needs to assign (like Guild roles) and above the users it needs to rename. Commands enforce default permissions (such as **Manage Roles** or **Manage Server**) unless customized by server administrators using Discord's command permissions system (**Server Settings → Integrations → Albion Assistant**).
>
> ⚠️ **Admin & Owner Limitations:** Due to Discord's security model, the bot **cannot** change nicknames or manage roles for the **Server Owner** or any user with **Administrator** permissions. This is a built-in protection to prevent bots from locking out or modifying server owners and high-privileged accounts.

> ℹ️
> **Manual Overrides:** Use the `/albion_manage` commands if you need to manually register someone, force an update, or remove a registration without the user's involvement.

---

[⬅️ Back to Home](index.md)

