# 👤 Registration & Whitelist

To use many of the bot's features (such as receiving roles, nicknames, or joining parties and tracking PvP statistics), you need to register your Albion Online character with the bot.

## 📝 How to Register

1.  **Start the Process:** Type the command `/albion_register start`.
2.  **Select Region:** Choose your server region (Americas, Europe, or Asia).
3.  **Enter Nickname:** Type your exact in-game character name.
4.  **Verification:** If multiple characters have similar names, select yours from the interactive selection menu. The bot will then verify your character and automatically assign whitelisted roles/nicknames if configured.

---

## 📋 Registration Commands

| Command | Parameter / Usage | Required Permission | Description |
| :--- | :--- | :--- | :--- |
| **`/albion_register start`** | `[region]` `[albion_nick]` | None (Everyone) | Starts the registration process for your character in a specific region. |
| **`/albion_register show`** | `[region]` (optional) | None (Everyone) | Shows your registration status and details. If region is omitted, shows all. |
| **`/albion_register remove`** | `[region]` | None (Everyone) | Unlinks your Discord account from your Albion character in the specified region. |
| **`/albion_register check`** | `[member]` `[region]` (optional) | None (Everyone) | Check the registration details of another server member. |
| **`/albion_register list`** | `[region]` | **Manage Roles** | Lists all registered users on this server for the specified region, sorted alphabetically. Supports pagination for large servers. |

---

## 🛡️ Whitelist & Roles

If your Albion Guild or Alliance is on the server's **whitelist** (configured by administrators), you will automatically receive the assigned roles and nickname tags (e.g., `[GUILD] Nickname` or `[ALLY] Nickname`) upon registration.

> ℹ️ **Tag Length Limit:** Guild and Alliance tags in nicknames are limited to a maximum of **7 characters** to comply with Discord nickname restrictions.

> ℹ️ **Automatic Guild Swapping:** If you change guilds or alliances in-game, the bot's automated background cycles will periodically update your Discord roles and tags to match your new guild status.

> ❗ **Multiple Roles:** If you belong to both a whitelisted guild and a whitelisted alliance, the roles you receive depend on the server's **Role Priority Mode** (Additive, Guild Only, or Alliance Only).

---

[⬅️ Back to Home](index.md)
