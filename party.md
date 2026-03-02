# 🎉 Party Management

Organize signups for raids, fame farms, and other group activities.

## 🔨 Creating a Party

To start a new party signup:
1.  Run the command `/party create`.
2.  Fill out the **Title**, **Description**, **Roles** (e.g., Tank, Healer, DPS), and **Footer**.
3.  The bot will create a new message and a **dedicated thread (Party Chat)**.

## 👥 Joining & Leaving

Users can join specific slots directly using commands:
*   **Join:** `/party join slot:1`
*   **Leave:** `/party leave`

## 👑 Leader Controls

The person who creates the party becomes the **Leader**. The Leader has special controls inside the Party Chat thread:

*   **Add User:** `/party add slot:2 user:@Member`
*   **Kick User:** `/party kick slot:2`
*   **Transfer Leadership:** `/party leader member:@NewLeader`
*   **Edit Party:** `/party edit` (Update title, roles, etc.)
*   **Delete Party:** `/party delete` (Deletes the party message and archives the thread)

## 📋 Party Templates

Save common party setups (e.g., "Standard 7-man Raid") to quickly load them later.

*   **/party template list**: See all saved templates.
*   **/party template create**: Save current configuration as a template.
*   **/party create use_template:True**: Start a new party using a saved template.

---

> ⭐ Use the **Party Chat** thread for all communication related to the event!

---

[⬅️ Back to Home](index.md)

