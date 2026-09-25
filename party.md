# 🎉 Party Management

Organize signups for raids, fame farms, and other group activities with advanced controls, real-time stats, and dedicated communication channels.

## 🔨 Creating a Party

To start a new party signup:
1.  Run the command `/party create`.
2.  Fill out the modal form with **Title**, **Description**, **Roles** (e.g., Tank, Healer, DPS), and **Footer**.
3.  **use_template** (optional): Select `True` to load a previously saved party template to pre-fill the form.
4.  The bot will publish a recruitment message with interactive buttons and automatically create a **dedicated thread (Party Chat)** for communication.

> ⚠️ **Character Limit:** The total size of the party embed (sum of Title, Description, Roles, and Footer) cannot exceed Discord's **6000 character limit**. The creation/edit modal will validate this and show an error if exceeded.

---

## 👥 Interactive Action Panel

Every published event features an **Interactive Action Panel** directly below the recruitment embed. This allows users to sign up without using slash commands:

*   🟢 **Join Role**: Opens a paginated select menu listing all available slots/roles (displays up to 20 slots per page with **◀ Prev** and **Next ▶** buttons to bypass Discord's 25-option limit).
*   🔴 **Leave Slot**: Removes you from the event. If you occupy multiple slots, opens an ephemeral menu to choose which slot to leave.
*   ⚙️ **Manage Event**: Opens a private management dashboard (visible only to the Event Leader and Guild Administrators).

### ⏳ Start Time Lock & Management Window
*   Once the scheduled event start time is reached, the **Join Role** and **Leave Slot** buttons are disabled.
*   The **Manage Event** button remains active for **30 minutes** after the start time, allowing the leader to make adjustments.
*   After 30 minutes, all action buttons are removed from the recruitment message, and a notification is sent to the event thread indicating the management window has closed.

---

## 🛠️ Event Management Dashboard (Leader / Admin Only)

Clicking the **Manage Event** button opens a private, interactive dashboard:
*   **Edit Details:** Opens a modal to modify the title, description, roles, footer, or thread name.
*   **Edit Time:** Reschedules the event time using date/hour/minute selectors. (Rescheduling an event to the future automatically restores active signups and action buttons!).
*   **Kick Member:** Opens a dropdown to remove a member from a specific slot.
*   **Add Member:** Search for a Discord member and select a role slot to manually assign them.
*   **Finish Event:** Initiates party completion, locking signups and archiving the event after a 15-minute stats compilation grace period.
*   **Delete Event:** Permanently deletes the party, its thread, recruitment message, and all signups with a confirmation prompt.

---

## 💬 Party Thread Commands

While inside the party thread (Party Chat), members, leaders, and administrators can also use slash commands to manage participation:

### Member Commands
*   `/party join`: Join the party by selecting a role from a dropdown. (Disabled after start time).
*   `/party leave`: Leave your slot. If you occupy multiple, select which one to leave. (Disabled after start time).

### Leader & Admin Commands
*   `/party add [user]`: Manually add a member to a role slot (Leader Only).
*   `/party kick [user]`: Remove a user from a specific slot. If no user is specified and a slot has multiple members, a dropdown selector appears (Leader Only).
*   `/party leader [user]`: Transfer event leadership to another Discord member (Leader Only).
*   `/party edit`: Open the edit menu to modify the details or time of the party (Leader Only).
*   `/party delete`: Delete the recruitment message, the database entry, and the active thread (Leader or Admin).
*   `/party finish`: Initiates party completion immediately (Leader Only). Locks signups (changing the embed title status to `🏁 [FINISHING]`) and continues tracking PvP event stats for a 15-minute grace period to capture late API data before posting the final report.

---

## 📊 Event Statistics & Analytics

The bot tracks server participation, activity patterns, and PvP performance based on whitelisted events.

### PvP Stats Summary
When a party is finished, the bot generates a detailed PvP statistics report showing:
*   Total kills, deaths, fame, and estimated silver value.
*   Top 5 Damage Dealers, Healers, Killers, and Players with the most Deaths.
*   *Prerequisites:*
    1. Members must be registered with their Albion characters (`/albion_register start`).
    2. Members must join the party slots with their registered Discord accounts.
    3. *(Note: The bot automatically tracks PvP events for your party members during the event, even on public servers without a configured killboard!)*

### Stats Commands
*   `/party stats [member]`: View event participation, activity patterns (peak day/hour), hosted vs joined counts, and aggregated PvP performance (total/avg kills, deaths, assists, damage, healing, fame, silver) for yourself or a selected member.
*   `/party leaderboard [type] [timeframe]`: View the top organizers or top attendees in the server (e.g. hosts or participants; 7d, 30d, or all time).
*   `/party analytics [type]`: View server-wide trends including peak hours (`time`) and role popularity (`roles`). Whitelisted Premium servers receive high-fidelity graphic charts (pie/bar graphs).

---

## 📋 Party Templates

Templates allow you to save common team compositions (e.g. "Standard 10-man ZvZ") to quickly create them later.

### Template Commands
*   `/party template create [name]`: Create a new template with the given name.
*   `/party template edit`: Opens a paginated dropdown select menu to choose and edit a template.
*   `/party template show`: View details of a specific template.
*   `/party template list`: List all templates saved in the server.
*   `/party template delete`: Delete a template via a dropdown selector.
*   `/party template manage`: Clean up and manage server templates (requires **Manage Server** permission by default, unless configured otherwise via Discord Integrations).
*   `/party template capture [name]`: Capture the currently active party's slots and save them as a new template.
*   `/party create use_template:True`: Start a new party creation using a saved template.

---

## ⚙️ Server Settings

Administrators can configure party behavior using `/party_settings` (requires **Manage Server** permission by default, unless customized via Discord's command permissions system) to open an interactive configuration panel:
*   **Multi-Candidate:** Allow or restrict users from signing up for multiple roles/slots in the same party.
*   **Pre-Registration:** Require users to have registered their Albion characters using `/albion_register start` before they can sign up for parties.
*   **Summary Enabled:** Toggle whether the bot maintains a live summary list of all upcoming events.
*   **In-Event Channel:** Toggle whether to display the upcoming events summary within the event channel itself.
*   **Centralized Channel:** Select a text channel where a live summary of all upcoming guild events will be continuously updated.

---

[⬅️ Back to Home](index.md)
