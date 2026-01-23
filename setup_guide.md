# 🛠️ Complete Setup Guide

This guide will walk you through the process of setting up the Albion Bot for your Discord server, from initial configuration to whitelisting and user registration.

## 1. Initial Configuration

Use the command `/albion_setup config` to define the core behavior of the bot. This command has several options that determine how users will interact with the bot and how their Discord profiles will be modified.

### ⚙️ Configuration Options Explained

| Option | Description |
| :--- | :--- |
| **`public`** | **Allow everyone to register?**<br>• **Yes:** Anyone can link their Albion account. They will receive the `public_role` (if configured) even if they aren't in a whitelisted guild/alliance.<br>• **No:** Only members of guilds or alliances you've specifically whitelisted can register. |
| **`public_role`** | **Public Role**<br>The Discord role given to users who register if `public` is set to **Yes**. This helps identify registered "guest" users. |
| **`edit_nick`** | **Change nickname?**<br>If enabled, the bot will automatically change the user's Discord nickname to match their Albion character name (including optional tags). |
| **`nick_tag_order`** | **Tag Order**<br>Determines if the Alliance tag or Guild tag appears first. (e.g., `[ALLY][GUILD] Name` vs `[GUILD][ALLY] Name`). |
| **`nick_ally_tag`** | **Alliance Tag Display**<br>Choose who can see the alliance tag in nicknames (Everyone, Only members, or Don't show). |
| **`nick_ally_tag_length`** | **Alliance Tag Length**<br>The maximum characters for the alliance tag (1-7). |
| **`nick_guild_tag`** | **Guild Tag Display**<br>Choose who can see the guild tag in nicknames. |
| **`nick_guild_tag_length`** | **Guild Tag Length**<br>The maximum characters for the guild tag (1-7). |
| **`purge_users`** | **Automatic Cleanup?**<br>If enabled, the bot will periodically check users and maintain their roles/nicknames based on their current guild status. |
| **`purge_mode`** | **Purge Behavior**<br>• **Full:** Strip all roles and reset nickname if user is not on any whitelist.<br>• **Soft:** Only remove specifically whitelisted roles, keeping the Public role and nickname. |
| **`purge_log_channel`** | **Log Channel**<br>A text channel where the bot will send detailed logs of every update/purge action taken, and a summary report after each cycle. |
| **`role_conflict`** | **Role Priority Mode**<br>How to handle users in both a whitelisted guild AND alliance:<br>• **Additive:** Give both roles.<br>• **Guild Only:** Prioritize guild role.<br>• **Alliance Only:** Prioritize alliance role. |

---

## ⚡ The "Public" vs "Purge" Interaction

It is important to understand how these two settings interact when automated maintenance is active.

> [!WARNING]
> If **`purge_users`** is **ENABLED** and you have at least one guild whitelisted (via `/albion_guild add`), the bot will purge any user who is NOT in one of those whitelisted guilds.

**What this means for Public users:**
If you enable **`public`** registration but also enable **`purge_users`**, a user who is not in a whitelisted guild will be allowed to register initially. However, during the next automated cleanup cycle, the bot will see that they are not on any whitelist and will **PURGE** them (removing their roles and resetting their nickname).

**Recommended Configuration:**
- **For Private/Guild Servers:** `public: No`, `purge_users: Yes`, `purge_mode: Full`.
- **For Open Servers (Community):** `public: Yes`, `purge_users: No`.
- **For Managed Servers with Guests:** `public: Yes`, `purge_users: Yes`, `purge_mode: Soft` (This keeps guests verified but updates their roles).

For a deep dive into the automated cleanup logic, see the [Purge System Guide](file:///home/vinanrra/Documents/Github/Albion-Online_Assistant_Docs/purge_system.md).


---

## 2. Whitelisting Guilds & Alliances

Whitelisting is how you tell the bot which Albion players belong to your community and which Discord roles they should receive.

### 🛡️ Whitelisting a Guild
Use `/albion_guild add` to add a guild to your whitelist.
1.  **Search:** Enter the name of the Albion Online guild.
2.  **Select Region:** Choose the region (Americas, Europe, or Asia).
3.  **Assign Role:** Select the Discord role that members of this guild should receive upon registration.
4.  **Tag:** Enter the 1-7 character tag to display in their nickname (e.g., `TC` for The Coalition).

### 🤝 Whitelisting an Alliance
Similar to guilds, use `/albion_alliance add`. Members of any guild within the whitelisted alliance will receive the specified role and tag.

> [!NOTE]
> **Safe Cleanup:** Removing a guild or alliance will trigger an automated prompt asking if you want to perform a cleanup of the associated users (stripping roles and unregistering them).

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

> [!TIP]
> **Role Hierarchy:** Ensure the bot's highest role is placed **above** the roles it needs to assign (like Guild roles) and above the users it needs to rename. If the bot's role is too low, it will fail to update users.

> [!IMPORTANT]
> **One Account Policy:** By default, the bot enforces consistency. A user cannot register with one character on one server and a different character on another server within the same region. This prevents "spy" accounts.

> [!NOTE]
> **Manual Overrides:** Use the `/albion_manage` commands if you need to manually register someone, force an update, or remove a registration without the user's involvement.
