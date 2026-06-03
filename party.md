# 🎉 Party Management

Organize signups for raids, fame farms, and other group activities.

## 🔨 Creating a Party

To start a new party signup:
1.  Run the command `/party create`.
2.  Fill out the **Title**, **Description**, **Roles** (e.g., Tank, Healer, DPS), and **Footer**.
3.  The bot will create a new message and a **dedicated thread (Party Chat)**.

## 👥 Joining & Leaving

Users can manage their party signup directly using commands inside the party thread:
*   **Join:** `/party join` (Launches a dropdown menu to select and sign up for any available role/slot)
*   **Leave:** `/party leave` (Removes yourself from your signed-up slot. If you occupy multiple slots, a dropdown selection will appear)

## 👑 Leader Controls

The person who creates the party becomes the **Leader**. The Leader has special controls inside the Party Chat thread:

*   **Add User:** `/party add user:@Member` (Manually assigns a server member to a slot via a role dropdown menu)
*   **Kick User:** `/party kick [user]` (Removes a member from their slot. If no user is specified and multiple members occupy a slot, a dropdown will let you choose who to kick)
*   **Transfer Leadership:** `/party leader member:@NewLeader` (Transfers the party ownership to another member)
*   **Edit Party:** `/party edit` (Opens a menu to edit the party title, description, start time, and slot roles)
*   **Delete Party:** `/party delete` (Deletes the recruitment message and archives the thread)
*   **Finish Party:** `/party finish` (Completes the party, locks signups, archives the thread, and compiles/posts the PvP stats summary of the event)

## 📊 Event Statistics & Analytics

When a Leader finishes a party using `/party finish`, the bot will automatically generate an embedded summary of the **PvP Statistics** for the event!

**What is tracked in the event summary?**
*   Total Kills, Deaths, Fame, and Estimated Silver Value.
*   Top 5 Damage Dealers, Healers, Killers, and Players with the most Deaths.

**How does it work?**
1.  Members **must** have registered their Albion characters using `/albion register`.
2.  Members **must** join the party slots with their registered Discord accounts.
3.  *(Note: The bot **automatically** tracks PvP events for your party members during the event, even on public servers. No extra setup required.)*

### Event Stats & Analytics Commands:
*   **/party stats [member]**: View event stats for yourself or another server member (total events attended/hosted, most played roles, and a **Reliability Rating** that recovers over time).
*   **/party leaderboard [type] [timeframe]**: View the top organizers or top attendees in the server. Run without parameters for interactive select menus.
*   **/party analytics [type]**: View server-wide trends such as peak hours (`time`) and role popularity (`roles`).

## 📋 Party Templates

Save common party setups (e.g., "Standard 7-man Raid") to quickly load them later.

*   **/party template list**: See all saved templates.
*   **/party template create**: Save current configuration as a template.
*   **/party create use_template:True**: Start a new party using a saved template.

## ⚙️ Configuration

Use the **/party_settings** command to configure party recruitment behavior for the server. It opens an interactive setup panel:
*   **Multi-Candidate**: Allow or restrict users from signing up for multiple roles/slots in the same party.
*   **Pre-Registration**: Require users to register their Albion character first before they are allowed to join a party.
*   **Summary Enabled**: Toggle whether to maintain a real-time live list of upcoming events.
*   **In-Event Channel**: Toggle whether to show the upcoming events summary within the event channel itself.
*   **Centralized Channel**: Select a text channel where a live summary of all upcoming guild events will be continuously updated.

---

> ⭐ Use the **Party Chat** thread for all communication related to the event!

---

[⬅️ Back to Home](index.md)

