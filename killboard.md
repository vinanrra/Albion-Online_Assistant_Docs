# ⚔️ Albion Killboard Notifications

The Albion Killboard system allows you to receive real-time notifications of kills and deaths for specific **players**, **guilds**, or **alliances** directly in your Discord server.

## 🚀 Setup Guide

To enable killboard notifications, follow these simple steps:

### 1. Open the Killboard Control Panel
Use the command `/albion_killboard panel` to launch the interactive control panel dashboard.
*   **Permission:** Requires **Manage Server** (`manage_guild=True`) permission in Discord by default (unless customized in **Server Settings → Integrations**).
*   This command returns an interactive interface with buttons to manage all settings.

### 2. Configure Notification Channels
Using the control panel buttons, you can set separate target channels for kills and deaths:
*   🟢 **Setup Kills Channel**: Set the channel where kills by tracked entities will be posted.
*   🔴 **Setup Deaths Channel**: Set the channel where deaths of tracked entities will be posted.
*   *Note:* Ensure the bot has permissions to `Send Messages` and `Embed Links` in the selected channels.

### 3. Add Entities to Track
Click the ➕ **Add Tracking** button in the control panel to start monitoring a player or guild.
1.  **Select Type:** Choose between **Guild** or **Player**.
2.  **Select Region:** Choose the region (Americas, Europe, or Asia).
3.  **Enter Name:** Type the exact in-game name. If multiple matching entities are found, the bot will show a selection dropdown menu.

### 4. Verify Your Configuration
Click the 📊 **Status** button in the control panel to see:
*   The configured channels for kills and deaths.
*   The lists of all tracked guilds, alliances, and players.

---

## 🛠️ Control Panel Operations

The control panel features the following buttons for easy management:

| Button | Action | Description |
| :--- | :--- | :--- |
| **`Setup Kills Channel`** | Configure target channel | Sets the Discord channel where automatic kill notifications are posted. |
| **`Setup Deaths Channel`** | Configure target channel | Sets the Discord channel where automatic death notifications are posted. |
| **`Add Tracking`** | Track new entity | Adds a player or guild from a specific region to the tracking list. |
| **`Remove Tracking`** | Untrack entity | Opens a selector listing tracked entities so you can remove them. |
| **`Status`** | View settings | Displays the active channels and lists of all tracked entities. |
| **`Reset`** | Clear config | Wipes all killboard settings and tracking data for the server. |

---

## 💰 Estimated Kill Value & PvP Tracking

When a tracked kill or death event occurs, the bot automatically estimates the total silver value of the victim's equipment and inventory:

*   **Market Price Valuation:** The bot extracts the item IDs, counts, and qualities from the victim's equipment slots and inventory. It queries the **Albion Online Data Project** REST API for historical market prices over the last 7 days and computes a **volume-weighted average price** across the cities.
*   **7-Day Database Cache & Rate Protection:** Market valuations are cached locally in the database for 7 days with proactive sliding-window rate limiting and fallback shields to ensure ultra-fast, resilient image generation.
*   **Player Profit & Loss Tracking:** Combat events processed by the killboard engine automatically update player combat statistics, allowing members to inspect their net gains and losses via `/albion_stats user`.

---

[⬅️ Back to Home](index.md)
