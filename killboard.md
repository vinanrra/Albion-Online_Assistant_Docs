# ⚔️ Albion Killboard Notifications

The Albion Killboard system allows you to receive real-time notifications of kills and deaths for specific **players**, **guilds**, or **alliances** directly in your Discord server.

## 🚀 Setup Guide

To enable killboard notifications, follow these simple steps:

### 1. Open the Killboard Control Panel
Use the command `/albion_killboard panel` to launch the interactive control panel dashboard.
*   **Permission:** Requires **Manage Roles** or **Manage Server** permission in Discord.
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

## 💰 Estimated Kill Value

When a tracked kill or death event occurs, the bot automatically estimates the total silver value of the victim's equipment and inventory:

*   **How it Works:** The bot extracts the item IDs, counts, and qualities from the victim's equipment slots (10 slots) and inventory. It queries the **Albion Online Data Project** REST API for the matching region's historical market prices (daily interval) over the last 7 days. It computes a **volume-weighted average price** across the major trade hubs (Caerleon, Lymhurst, Bridgewatch, Martlock, Thetford, Fort Sterling, Brecilien).
*   **Fallback Heuristic:** To ensure value is shown even if historical or quality-specific data is sparse (due to the crowdsourced nature of the data project), the bot uses the following fallback chain:
    1. Calculate the 7-day volume-weighted average for the item's target quality.
    2. If unavailable, fall back to the 7-day volume-weighted average for Quality 1 (Normal).
    3. If still unavailable, fall back to the 7-day volume-weighted average for Any Quality.
    4. If no historical data exists at all for the last 7 days, query the active current prices endpoint for the most recent non-zero minimum sell price (or maximum buy price) matching the fallbacks.
*   **Display:** The final estimated value is printed:
    1. In the central column of the custom killboard parchment image.
    2. Directly in the Discord embed notification description under "Participants".

---

[⬅️ Back to Home](index.md)
