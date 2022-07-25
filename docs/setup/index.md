# /setup

## /setup config

This command will allow you to configure/edit bot settings

| Parameter | Function |
| --- | --- |
| `public` | Allow everyone to register (usefull for Disords servers like Faction, HCE, Avas...), if guild/alliance isn't configured tags will be get from Albion API |
| `public_role` | Role to give if server it's public, if guild/alliance are configured too will give those roles too |
| `admin_role` | Role that will be able to fully configure the bot |
| `mod_role` | Role that will be able to manage users (list registered users/guild/alliance, blacklist and manually register add/remove users) |
| `globalBlacklistWarning` | WIP - Enable this if you want to show a notification if the user was blacklisted at other Discord |
| `publicBlacklist` | WIP - Enable this if you want other Discord servers to be able to check your blacklist when globalBlacklistWarning it's enable |
| `purgeUsers` | Enable this if you want to remove role from users that left the configured guilds and guilds that left the configured alliances |
| `editNick` | Enable this if you want the bot to change the nickname to Albion Online ingame name |
| `nickAllyTag` | Configure when to add alliance tag before name |
| `nickAllyTagLenght` | Maximun alliance tag lenght |
| `nickGuildTag` | Configure when to add guild tag before name  |
| `nickGuildTagLenght` | Maximun guild tag lenght |
| `nickTagOrder` | Tag to show first in the name |

## /setup show

This command will allow you to show bot settings if configured

## /setup delete

This command will allow you you to remove all your Discord data from the bot
