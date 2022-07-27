# Quick setup

## - Pre-configuration

### Permissions

Put the bot role above the roles that it's gonna be able to give, check image.

![image](https://user-images.githubusercontent.com/4247187/181045362-c5ccb68e-bd9f-4d93-bb92-5d743750376a.png)

The bot will be able to give the following roles:
 - Member
 - Test

### Allow roles to use /slash commands

#### Bot configuration
Go to Server Settings > Integrations > Albion Assistant

![image](https://user-images.githubusercontent.com/4247187/181276275-6ba7837b-9fc0-4e08-b23f-2e7715b35cff.png)

![image](https://user-images.githubusercontent.com/4247187/181276405-63950209-fbd5-4f28-ba0c-91b344bd8bbe.png)

##### Per role
At Roles & Members you will be able which roles will be able to use Albion Assistant /slash commands

If you want to allow to use slash commands everywhere leave everywhere green

![image](https://user-images.githubusercontent.com/4247187/181276950-a6d8ab0a-6503-46c6-a198-e42c76bc4447.png)

If you want to restrict the usage to only some roles change @everyone to red and click `Add roles or Members`, add the roles you want to personalize and allow them like the photo:

![image](https://user-images.githubusercontent.com/4247187/181277247-9db3c0dc-893b-436d-9a5e-bccbdf7a6e50.png)

##### Per channel

At Channels, if you leave # All channels green, roles with permissions will be able to use the bot at every channel

![image](https://user-images.githubusercontent.com/4247187/181277603-2fe55463-5abb-42db-b59a-6d5f47ca1de8.png)

If you want to only allow some channels, put # All channels to red and click `Add channels`

![image](https://user-images.githubusercontent.com/4247187/181277773-e2550041-2fbf-409d-b429-78b4e94f8483.png)

Like this i will allow only to use Albion Assistant /slash commands at #spam-bot

#### Allow roles to use /slash commands

Go to Server Settings > Roles > Select the role

![image](https://user-images.githubusercontent.com/4247187/181276275-6ba7837b-9fc0-4e08-b23f-2e7715b35cff.png)

And allow the role to use /slash commands

![image](https://user-images.githubusercontent.com/4247187/181278372-327f27d4-f680-49fa-a214-e76b81f59089.png)

## - Setup the bot

First you will need to configure the bot using: `/setup config`, the bot will need some parameters.
If you need info about any parameter check [/setup docs](/docs/setup/index.md)

![image](https://user-images.githubusercontent.com/4247187/180800612-4bc50cbf-aa15-41d2-afd4-f95e3892172c.png)

Click in each parameter and the bot will show a list of each possible paramater:

![image](https://user-images.githubusercontent.com/4247187/180801330-08a451c2-5e33-4c66-90ce-e22644d3cd9b.png)


Example of `/setup config`:

![image](https://user-images.githubusercontent.com/4247187/180801036-3de048f4-2b71-4802-a290-abe2c1295051.png)

Send the command and the bot will show a resume of all your settings if everything it's correct click "Confirm" if not "Cancel"

![image](https://user-images.githubusercontent.com/4247187/180801760-7cc1c824-0245-4a3c-98bb-688928dc2082.png)

If you need to edit a settings, you will need to run again `/setup config`

## - Manage guilds

If you need info about any parameter check [/guild docs](/docs/guild/index.md)

### - Add/Modify a guild

First you will need to configure the guild using: `/guild add`, the bot will need some parameters.

![image](https://user-images.githubusercontent.com/4247187/180802319-a0769c2a-c697-4959-8860-0c9488a228d9.png)

Send the command and the bot will show a resume of all your settings if everything it's correct click "Confirm" if not "Cancel"

![image](https://user-images.githubusercontent.com/4247187/180802496-86eeccc9-581c-4f94-87c7-9d5b36986c62.png)

If you need to edit a guild, you will need to run again `/guild add`

### - Remove a guild

To remove a guild use `/guild remove`, the bot will need some parameters.

![image](https://user-images.githubusercontent.com/4247187/180802858-3ea86815-fa89-40df-9bda-09c9b521c8d4.png)

Send the command and the bot will show a resume of all your settings if everything it's correct click "Confirm" if not "Cancel"

![image](https://user-images.githubusercontent.com/4247187/180802961-6e7490ef-26e7-4d63-8730-96a329a086e5.png)


## - Configure an alliance

Same as guild but using `/alliance`
If you need info about any parameter check [/alliance docs](/docs/alliance/index.md)

## - Blacklist

If you need info about any parameter check [/blacklist docs](/docs/blacklist/index.md)

## - Manage blacklist

### Add/Modify

First you will need to add the blacklist user/guild/alliance using: `/blacklist add`, the bot will need some parameters.
IMPORTANT choose the correct type (User, Guild or Alliance) if wrong the bot will show an error

![image](https://user-images.githubusercontent.com/4247187/180803539-b9b10f82-e186-4867-8352-bdd1ffd14dbb.png)

Send the command and the bot will show a resume of all your settings if everything it's correct click "Confirm" if not "Cancel"
![image](https://user-images.githubusercontent.com/4247187/180803863-c5c7c051-4e06-4181-92be-589df3290c5f.png)


### Remove

![image](https://user-images.githubusercontent.com/4247187/180803921-9d0d07ab-3320-4abe-b320-20595a96b747.png)
