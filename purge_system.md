# 🧹 Automated Purge System

The Purge System is a powerful maintenance tool designed to keep your Discord server's roles and nicknames in perfect sync with the game. It periodically audits all registered users and ensures they only have the permissions they currently deserve.

## ⚙️ How it Works

The bot runs a background cycle (every few hours, as configured by the bot owner) that performs the following steps for every registered user:

1.  **API Audit**: The bot queries the Albion Online API to check the user's current Guild and Alliance.
2.  **Whitelist Comparison**: It compares this data against your server's `/albion_guild` and `/albion_alliance` whitelists.
3.  **Action Determination**:
    *   **Level 1: Update**: If the user moved from one whitelisted guild/alliance to another, the bot updates their roles and nickname tags immediately.
    *   **Level 2: Purge**: If the user is no longer in any whitelisted entity (neither guild nor alliance), the bot triggers a purge based on your configured **Purge Mode**.

> [!TIP]
> **Role Priority**: During updates, the bot respects your **Role Conflict Mode** setting. If a user is in both a whitelisted guild and alliance, the bot will filter roles based on your priority (Additive, Guild Only, or Alliance Only).

---

## 🌓 Purge Modes

You can choose how aggressive the cleanup should be using `/albion_setup config`.

### 1. Full Purge (Mode: 1)
This is the "Zero Tolerance" mode. If a user is not in a whitelisted guild/alliance, the bot assumes they should no longer have access to your private areas.
*   **Discord Action**: Strips **ALL** roles (including the Public/Verified role) and **resets their nickname** to default.
*   **Database Action**: Deletes their registration record. They must register again if they rejoin a whitelisted guild.
*   **Best For**: Private competitive guilds and "Hardcore" communities.

### 2. Soft Purge (Mode: 2)
This mode is designed for large community servers or alliances that allow "Guest" or "Public" members to stay, but only want to give special roles to active members.
*   **Discord Action**: Removes only the specific **Guild and Alliance roles** provided by the whitelist. It **KEPPS** the Public role and keeps their nickname as it was.
*   **Database Action**: Retains the registration record.
*   **Best For**: Open community hubs, coalition servers, and social alliances.

---

## 📝 Logging & Reporting

If you configure a `purge_log_channel`, the bot provides full transparency into its automated actions.

### Action Logs
As the bot processes users, it sends real-time updates:
*   🔄 **Update**: User moved guilds but is still whitelisted.
*   ❌ **Full Purge**: User completely removed.
*   ⚠️ **Soft Purge**: Special roles removed, but user remains.

### Cycle Report
At the end of every audit cycle, the bot sends a summary embed:
*   **Checked**: Total number of users audited.
*   **Updated**: Residents who changed their tags/roles.
*   **Purged**: Users who lost access.
*   **Errors**: Any issues (usually Discord permission problems).

---

## 💡 Examples & Use Cases

### Scenario A: The Competitive Guild
**Goal**: Only current members should see the guild channels.
*   **Setup**: `public: No`, `purge_users: Yes`, `purge_mode: Full`.
*   **Result**: When a player is kicked from the guild in-game, they lose all access to your Discord automatically within hours.

### Scenario B: The Community Hub
**Goal**: Everyone can chat in `#general`, but only members get access to `#war-room`.
*   **Setup**: `public: Yes`, `public_role: @Verified`, `purge_users: Yes`, `purge_mode: Soft`.
*   **Result**: If a player leaves your guild, they lose the `@Veteran` role and access to `#war-room`, but they keep the `@Verified` role and can still chat in public channels.

---

## ⚡ Manual Cleanup (Instant)

While the automated purge system runs periodically, the bot also provides an **instant cleanup option** when you manually remove a guild or alliance from the whitelist.

- **Trigger**: Using `/albion_guild remove` or `/albion_alliance remove`.
- **The Prompt**: The bot will immediately ask if you want to:
    1. **Remove Users**: Permanently unregister all users from that entity and strip their roles.
    2. **Keep Users**: Remove the entity from the whitelist but keep all current members registered.
- **Log**: These manual actions are also recorded in your `purge_log_channel`.

---

> [!CAUTION]
> **Permissions**: For the purge system to work, the Bot's role must be higher in the Discord settings than all the roles it is trying to manage. It also needs the **Manage Nicknames** permission.

---

[⬅️ Back to Home](index.md)

