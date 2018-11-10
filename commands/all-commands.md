# All Commands

## Legend

`<required arg>` `[optional arg]`

Text arguments containing multiple words needs be to put in quotes \("arg here"\) or code ticks \(`arg here`\) if it's not the last argument and there's more than 1 text argument.

For example with the poll command if you want the question to have multiple words: `-poll "whats your favorite color" red blue green2`

## General ℹ️

### Help

**Aliases:** commands/h/how/command

Shows help about all or one specific command

**Usage:**

```text
Help [command:Text]
```

### Info

Responds with bot information

**Usage:**

```text
Info
```

### Invite

Responds with bot invite link

**Usage:**

```text
Invite
```

## Tools & Utilities 🔨

### Prefix

Shows command prefix of the current server, or the specified server

**Usage:**

```text
Prefix [Server ID:Whole number]
```

### Calc

**Aliases:** c/calculate

Calculator 2+2=5

**Usage:**

```text
Calc <Expression:Text>
```

### Ping

Shows the latency from the bot to the discord servers. Note that high latencies can be the fault of ratelimits and the bot itself, it's not a absolute metric.

**Usage:**

```text
Ping
```

### CurrentTime

**Aliases:** ctime/gettime

Shows current time in different timezones. [Available timezones](https://pastebin.com/ZqSPUhc7)

**Usage:**

```text
CurrentTime <Offset:Whole number>
CurrentTime <Zone:Text>
CurrentTime
```

### MentionRole

**Aliases:** mrole

Sets a role to mentionable, mentions the role, and then sets it back Requires the manage roles permission and the bot being above the mentioned role

**Usage:**

```text
MentionRole <Role:Text> [Message:Text]
```

### ListRoles

List roles, their id's, color hex code, and 'mention everyone' perms \(usefull if you wanna double check to make sure you didn't give anyone mention everyone perms that shouldn't have it\)

**Usage:**

```text
ListRoles
```

### Poll

Create very simple reaction poll. Example: \`poll "favorite color?" blue red pink

**Usage:**

```text
Poll <Topic:Text - Description of the poll> <Option1:Text> <Option2:Text> [Option3:Text] [Option4:Text] [Option5:Text] [Option6:Text] [Option7:Text] [Option8:Text] [Option9:Text] [Option10:Text]
```

### Undelete

**Aliases:** ud

Views your recent deleted messages, or all users deleted messages \(with "-a" and manage messages perm\) in this channel

**Usage:**

```text
Undelete
```

```text
[-a all:Switch]
```

### ViewPerms

Shows you or the targets permissions in this channel

**Usage:**

```text
ViewPerms [target:Mention/ID]
```

### Stats

Shows server stats \(if public stats are enabled\)

**Usage:**

```text
Stats
```

### CustomCommands

**Aliases:** cc

Shows a custom command specified by id or trigger, or lists them all

**Usage:**

```text
CustomCommands <ID:Whole number>
CustomCommands <Trigger:Text>
CustomCommands
```

### Logs

**Aliases:** log

Creates a log of the last messages in the current channel. This includes deleted messages within an hour \(or 12 hours for premium servers\)

**Usage:**

```text
Logs [Count:Whole number]
```

### Whois

**Aliases:** whoami

shows information about a user

**Usage:**

```text
Whois [User:User]
```

### Nicknames

**Aliases:** nn

Shows past nicknames of a user. Only shows up to the last 25 nicknames.

**Usage:**

```text
Nicknames [User:User]
```

### Usernames

**Aliases:** unames/un

Shows past usernames of a user. Only shows up to the last 25 usernames.

**Usage:**

```text
Usernames [User:User]
```

### Remindme

**Aliases:** remind

Schedules a reminder, example: 'remindme 1h30min are you alive still?'

**Usage:**

```text
Remindme <Time:Duration> <Message:Text>
```

### Reminders

Lists your active reminders

**Usage:**

```text
Reminders
```

### CReminders

Lists reminders in channel, only users with 'manage server' permissions can use this.

**Usage:**

```text
CReminders
```

### Delreminder

**Aliases:** rmreminder

Deletes a reminder.

**Usage:**

```text
Delreminder <ID:Whole number>
```

### Role

Toggle a role on yourself or list all available roles, they have to be set up in the control panel first, under 'rolecommands'

**Usage:**

```text
Role [Role:Text]
```

## Fun 🎉

### Define

**Aliases:** df

Look up an urban dictionary definition

**Usage:**

```text
Define <Topic:Text>
```

### Weather

**Aliases:** w

Shows the weather somewhere

**Usage:**

```text
Weather <Where:Text>
```

### Topic

Generates a conversation topic to help chat get moving.

**Usage:**

```text
Topic
```

### CatFact

**Aliases:** cf/cat/catfacts

Cat Facts

**Usage:**

```text
CatFact
```

### Advice

Dont be afraid to ask for advice!

**Usage:**

```text
Advice [What:Text]
```

### Throw

Throwing things is cool.

**Usage:**

```text
Throw [Target:User]
```

### Roll

Roll dices, specify nothing for 6 sides, specify a number for max sides, or rpg dice syntax. Example: `-roll 2d6`

**Usage:**

```text
Roll <Sides:Whole number>
Roll <RPG Dice:Text>
Roll
```

### CustomEmbed

**Aliases:** ce

Creates an embed from what you give it in json form: [https://docs.yagpdb.xyz/others/custom-embeds](https://docs.yagpdb.xyz/others/custom-embeds) Example: `-ce {"title": "hello", "description": "wew"`

**Usage:**

```text
CustomEmbed <Json:Text>
```

### SimpleEmbed

**Aliases:** se

A more simpler version of CustomEmbed, controlled completely using switches.

**Usage:**

```text
SimpleEmbed
```

```text
[-channel :Channel - Optional channel to send in]
[-title :Text]
[-desc :Text - Text in the 'description' field]
[-color :Text - Either hex code or name]
[-url :Text - Url of this embed]
[-thumbnail :Text - Url to a thumbnail]
[-author :Text - The text in the 'author' field]
[-authoricon :Text - Url to a icon for the 'author' field]
[-footer :Text - Text content for the footer]
[-footericon :Text - Url to a icon for the 'footer' field]
```

### WouldYouRather

**Aliases:** wyr

Get presented with 2 options.

**Usage:**

```text
WouldYouRather
```

### TopServers

Responds with the top 15 servers I'm on

**Usage:**

```text
TopServers [Skip:Whole number - Entries to skip]
```

### TakeRep

**Aliases:** -/tr/trep/-rep

Takes away rep from someone

**Usage:**

```text
TakeRep <User:User> [Num:Whole number]
```

### GiveRep

**Aliases:** +/gr/grep/+rep

Gives rep to someone

**Usage:**

```text
GiveRep <User:User> [Num:Whole number]
```

### SetRep

**Aliases:** SetRepID

Sets someones rep, this is an admin command and bypasses cooldowns and other restrictions.

**Usage:**

```text
SetRep <User:Mention/ID> <Num:Whole number>
```

### DelRep

Deletes someone from the reputation list completely, this cannot be undone.

**Usage:**

```text
DelRep <User:Mention/ID>
```

### RepLog

**Aliases:** replogs

Shows the rep log for the specified user.

**Usage:**

```text
RepLog <User:Mention/ID> [Page:Whole number]
```

### Rep

Shows yours or the specified users current rep and rank

**Usage:**

```text
Rep [User:User]
```

### TopRep

Shows top 15 rep on the server

**Usage:**

```text
TopRep [Offset:Whole number]
```

### sentiment

**Aliases:** sent

Does sentiment analysys on a message or your last 5 messages longer than 3 words

**Usage:**

```text
sentiment [text:Text]
```

### 8Ball

Wisdom

**Usage:**

```text
8Ball <What to ask:Text>
```

### Soundboard

**Aliases:** sb

Play, or list soundboard sounds

**Usage:**

```text
Soundboard [Name:Text]
```

### cah create

**Aliases:** c

Creates a cards against humanity game in this channel, add packs after commands, or \* for all packs. \(-v for vote mode without a card czar\)

**Usage:**

```text
create [packs:Text - Packs seperated by space, or * for all of them]
```

```text
[-v Vote mode - players vote instead of having a cardczar:Switch]
```

### cah end

Ends a cards against humanity game thats ongoing in this channel.

**Usage:**

```text
end
```

### cah kick

Kicks a player from the ongoing cards against humanity game in this channel.

**Usage:**

```text
kick <user:Mention/ID>
```

### cah packs

Lists available packs

**Usage:**

```text
packs
```

## Debug & Maintenance 🖥

### CurrentShard

**Aliases:** cshard

Shows the current shard this server is on \(or the one specified

**Usage:**

```text
CurrentShard [serverid:Whole number]
```

### MemberFetcher

**Aliases:** memfetch

Shows the current status of the member fetcher

**Usage:**

```text
MemberFetcher
```

### Yagstatus

**Aliases:** status

Shows yagpdb status, version, uptime, memory stats, and so on

**Usage:**

```text
Yagstatus
```

### roledbg

Debug debug debug autorole assignment

**Usage:**

```text
roledbg
```

## Moderation 👮

### Ban

**Aliases:** banid

Bans a member, specify a duration with -d

**Usage:**

```text
Ban <User:Mention/ID> [Reason:Text]
```

```text
[-d Duration:Duration]
```

### Kick

Kicks a member

**Usage:**

```text
Kick <User:Mention/ID> [Reason:Text]
```

### Mute

Mutes a member

**Usage:**

```text
Mute <User:User Mention> <Duration:Duration> <Reason:Text>
Mute <User:User Mention> <Reason:Text> <Duration:Duration>
Mute <User:User Mention> <Duration:Duration>
Mute <User:User Mention> <Reason:Text>
Mute <User:User Mention>
```

### Unmute

Unmutes a member

**Usage:**

```text
Unmute <User:User Mention> [Reason:Text]
```

### Report

Reports a member to the server's staff

**Usage:**

```text
Report <User:Mention/ID> <Reason:Text>
```

### Clean

**Aliases:** clear/cl

Delete the last number of messages from chat, optionally filtering by user, max age and regex. Specify a regex with "-r regex\_here" and max age with "-ma 1h10m" Note: Will only look in the last 1k messages

**Usage:**

```text
Clean <Num:Whole number>
Clean <Num:Whole number> <User:User Mention>
Clean <User:User Mention> <Num:Whole number>
```

```text
[-r Regex:Text]
[-ma Max age:Duration]
[-i Regex case insensitive:Switch]
```

### Reason

Add/Edit a modlog reason

**Usage:**

```text
Reason <ID:Whole number> <Reason:Text>
```

### Warn

Warns a user, warnings are saved using the bot. Use -warnings to view them.

**Usage:**

```text
Warn <User:User Mention> <Reason:Text>
```

### Warnings

**Aliases:** Warns

Lists warning of a user.

**Usage:**

```text
Warnings <User:Mention/ID>
```

### EditWarning

Edit a warning, id is the first number of each warning from the warnings command

**Usage:**

```text
EditWarning <Id:Whole number> <NewMessage:Text>
```

### DelWarning

**Aliases:** dw

Deletes a warning, id is the first number of each warning from the warnings command

**Usage:**

```text
DelWarning <Id:Whole number>
```

### ClearWarnings

**Aliases:** clw

Clears the warnings of a user

**Usage:**

```text
ClearWarnings <User:Mention/ID>
```

### automod toggle

**Aliases:** t

Toggles a ruleset on/off

**Usage:**

```text
toggle <ruleset name:Text>
```

## Rolemenu 🔘

### RoleMenu Create

**Aliases:** c

Set up a role menu. Specify a message with -m to use an existing message instead of having the bot make one

To get the id of a message you have to turn on developer mode in discord's appearances settings then right click the message and copy id.

**Usage:**

```text
Create <Group:Text>
```

```text
[-m Message ID:Whole number]
[-nodm Disable DM:Switch]
[-rr Remove role on reaction removed:Switch]
[-skip Number of roles to skip:Whole number]
```

### RoleMenu Remove

Removes a rolemenu from a message. The message won't be deleted and the bot will not do anything with reactions on that message

To get the id of a message you have to turn on developer mode in discord's appearances settings then right click the message and copy id.

**Usage:**

```text
Remove <Message ID:Whole number>
```

### RoleMenu Update

**Aliases:** u

Updates a rolemenu, toggling the provided flags and adding missing options, aswell as updating the order.

To get the id of a message you have to turn on developer mode in discord's appearances settings then right click the message and copy id.

**Usage:**

```text
Update <Message ID:Whole number>
```

```text
[-nodm Disable DM:Switch]
[-rr Remove role on reaction removed:Switch]
```

### RoleMenu ResetReactions

**Aliases:** reset

Removes all reactions on the specified menu message and re-adds them. Can be used to fix the order after updating it.

To get the id of a message you have to turn on developer mode in discord's appearances settings then right click the message and copy id.

**Usage:**

```text
ResetReactions <Message ID:Whole number>
```

### RoleMenu EditOption

**Aliases:** edit

Allows you to reassign the emoji of an option, tip: use ResetReactions afterwards.

To get the id of a message you have to turn on developer mode in discord's appearances settings then right click the message and copy id.

**Usage:**

```text
EditOption <Message ID:Whole number>
```
