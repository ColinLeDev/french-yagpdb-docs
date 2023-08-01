# Toutes les commandes

## Legende

`<argumment requis>` `[argument optionnel]`

Les arguments de type texte contenant plusieurs mots doivent être placés entre guillemets ("argument ici") ou accents graves (\`argument ici\`) si ce n'est pas le dernier argument ou s'il y a plus d'1 argument texte.

Par exemple avec la commande de sondage : `-poll "Quelle est votre couleur préférée" rouge bleu vert`

La plupart des commandes sous [#debug-and-maintenance](all-commands.md#debug-and-maintenance "mention"), ou les commandes sans une description complète sont destinées pour le propriétaire du bot, ou les administrateurs de serveur !

Si une commande est marquée avec la tilde : `~`, elles ne sont soit pas encore déployées dans le bot YAGPDB actuel, ou ont été désactivées dans le bot principal, mais le code est toujours présent dans la branche `main`.

## Général ℹ️

### Help

**Alias:** commands/h/how/command

Montre l'aide pour une commande spécifique

**Utilisation :**

```
Help [commande:Texte]
```

### Info

Répond avec les informations du bot

**Utilisation :**

```
Info
```

### Invite

Répond avec une invitation pour le bot

**Utilisation :**

```
Invite
```

## Outils & Utilitaires  🔨

### Calc

**Alias:** c/calculate

Calculatrice _2+2=5_

**Utilisation :**

```
Calc <Expression:Texte>
```

### CReminders

Liste les rappels dans ce salon, seulement les utilisateurs avec la permission **Gérer le serveur** (_Manage server_) peuvent l'utiliser.

**Utilisation :**

```
CReminders
```

### CurrentTime

**Alias:** ctime/gettime

Montre le temps actuel dans différents fuseaux horaires. [Available timezones](https://pastebin.com/ZqSPUhc7)

**Utilisation :**

```
CurrentTime <Décalage:Nombre entier>
CurrentTime <Zone:Texte>
CurrentTime
```

### CustomCommands

**Alias:** cc

Montre une commande personnalisée spécifiée par son ID ou son déclencheur, ou fait une liste de toutes les commandes

**Utilisation :**&#x20;

```
CustomCommands <ID:Nombre entier>
CustomCommands <Trigger:Text>
CustomCommands
```

```
[-file Renvoie la réponse dans un fichier:Switch]
[-color Utilise la coloration syntaxique (GO):Switch]
[-raw raw:Switch - Force une sortie brute]
```

### CustomEmbed

**Alias:** ce

Crée un embed depuis ce que vous avez fourni en format JSON : [custom-embeds.md](../reference/custom-embeds.md "mention") \
Exemple : `-ce {"title": "Bonjour", "description": "waw"}`

**Utilisation :**&#x20;

```
CustomEmbed <Json:Texte>
```

### DelReminder

**Alias:** rmreminder

Supprime un rappel. Vous pouvez supprimer des rappels d'autres utilisateurs, à condition que le rappel ait été créé dans le même serveur que celui dans lequel vous avez exécuté la commande. Il faut que vous ayez la permission **Gérer le salon** (_Manage Channel_) dans le salon dans lequel le rappel a été créé.

**Utilisation :**&#x20;

```
DelReminder <ID:Nombre entier>
```

```
[-a Tout:Switch]
```

### Evalcc

execute du code de commande personnalisée (jusqu'à 1 000 caractères)

**Utilisation :**&#x20;

```
Evalcc <code:Texte>
```

### fixscheduledccs

Corrige le temps de la prochaine exécution des CC avec le trigger **interval**, résout les problèmes liés aux exécutions manquées en raison d'un temps d'arrêt. Administrateurs du bot seulement

**Utilisation :**&#x20;

```
fixscheduledccs
```

### ListRoles

Liste les roles, leurs ID, leur couleur en format hexadécimal, et si le rôle a la permission **Mentionner @everyone** (_Mention Everyone_) (utile si vous voulez vérifier de nouveau que vous n'avez pas donné la permission de mentionner @everyone à un rôle alors que vous n'auriez pas dû)

**Utilisation :**&#x20;

```
ListRoles
```

```
[-nomanaged Ne liste pas les rôles gérés et les rôles de bots:Switch]
```

### Logs

**Alias:** log

Crée un historique des derniers messages dans le salon actuel. Cela inclut les messages supprimés dans l'heure (ou 12 heures pour les serveurs premium)

**Utilisation :**&#x20;

```
Logs [Count:Nombre entier]
```

### \~Nicknames

**Alias:** nn

Montre les surnoms passés d'un utilisateur. La commande montre uniquement les 25 derniers surnoms.

**Utilisation :**&#x20;

```
Nicknames [User:User]
```

### Ping

Montre la latence du bot sur le serveur Discord. Notez que les hautes latences peuvent être la faute de limites de taux ou du bot lui-même, ce n'est pas une mesure absolue.

**Utilisation :**&#x20;

```
Ping
```

### Poll

Crée des sondages très simples. Exemple: `poll "Couleur favorite ?" bleu rouge vert`

**Utilisation :**&#x20;

```
Poll <Sujet:Texte - Description du sondage> <Option1:Texte> <Option2:Texte> [Option3:Texte] [Option4:Texte] [Option5:Texte] [Option6:Texte] [Option7:Texte] [Option8:Texte] [Option9:Texte] [Option10:Texte]
```

### Prefix

Montre le préfixe du serveur actuel, ou du serveur spécifié

**Utilisation :**&#x20;

```
Prefix [ID du serveur:Nombre entier]
```

### Reminders

Liste vos rappels actifs

**Utilisation :**&#x20;

```
Reminders
```

### Remindme

**Alias:** remind/reminder

Programme un rappel, exemple: 'remindme 1h30min Toujours en vie ?'

**Utilisation :**&#x20;

```
Remindme <Temps:Duration> <Message:Texte>
```

```
[-channel salon:Channel]
```

### \~ResetPastNames

Réinitialise vos anciens noms/surnoms.

**Utilisation :**&#x20;

```
ResetPastNames
```

### Role

Ajoutez ou retirez-vous un rôle, ou listez les rôles disponibles, qui doivent définis dans le panneau de commande, sous le panneau ([self-assignable-roles.md](../tools-and-utilities/self-assignable-roles.md "mention"))

**Utilisation :**&#x20;

```
Role [Role:Texte]
```

### Settimezone

**Alias:** setz/tzset

Définissez votre fuseau horaire, utilisé pour de nombreuses choses, comme la conversion automatique. Ajoutez-y votre pays.

**Utilisation :**&#x20;

```
Settimezone [Fuseau Horaire:Texte]
```

```
[-u Montre le fuseau actuel:Switch]
[-d Supprime le fuseau enregistré:Switch]
```

### SimpleEmbed

**Alias:** se

Une version plus simple de la commande **CustomEmbed**, en utilisant seulement des options.\
Vous pouvez modifier des messages existants avec l'option `-message`.

**Utilisation :**&#x20;

```
SimpleEmbed
```

```
[-channel :Channel - Salon où envoyer le message]
[-message message:Nombre entier - ID du message à éditer]
[-content :Texte - Contenu du message]
[-title :Texte - Titre de l'embed]
[-desc :Texte - Texte dans le champs 'description']
[-color :Texte - Code hexadécimal ou nom]
[-url :Texte - URL de cet embed]
[-thumbnail :Texte - URL de l'image de la vignette]
[-image :Texte - URL de l'image]
[-author :Texte - le texte dans le champs 'author']
[-authoricon :Texte - URL pour une icône dans la champs 'author']
[-authorurl :Texte - URL pour le champs 'author']
[-footer :Texte - Contenu texte du pied de l'embed]
[-footericon :Texte - URL pour une icon du champs 'footer']
```

### Stats

Montre les statistiques du serveur (si les statistiques publiques sont activées). Cette commande est seulement disponible si la collecte des statistiques est activée, pas du côté utilisateur. Désactivé pour YAGPDB

**Utilisation :**&#x20;

```
Stats
```

### ToggleTimeConversion

**Alias:** toggletconv/ttc

Active/Désactive la conversion automatique pour les personnes qui ont un fuseau horaire enregistré, activé par défaut, modifiez tous les salons avec l'option `all`

**Utilisation :**&#x20;

```
ToggleTimeConversion [flags:Texte]
```

### Undelete

**Alias:** ud

Voir les 10 derniers messages supprimés. Par défaut, seul vos messages effacés sont affichés. Vous pouvez utiliser l'option `-a` pour voir les messages effacés de tous les utilisateurs, ou `-u` pour ceux d'un utilisateur spécifique. L'utilisation simultanée de `-a` et `-u` nécessite la permission **Gérer les messages** (_Manage Messages_). Note : `-u` prend le pas sur `-a` ce qui veut dire que `-a` utilisé avec `-u` montre uniquement les messages de l'utilisateur ciblé par l'option `-u`.

**Utilisation :**&#x20;

```
Undelete
```

```
[-a a:Switch - de tous les utilisateurs]
[-u u:Mention/ID - d'un utilisateur spécifique]
[-channel channel:Channel - Salon cible optionnel]
```

### \~Usernames

**Alias:** unames/un

Montre les derniers pseudos d'un utilisateur. Montre les 25 derniers pseudos.

**Utilisation :**&#x20;

```
Usernames [Utilisateur:User]
```

### ViewPerms

Vous montre les permissions de la cible dans le salon.

**Utilisation :**&#x20;

```
ViewPerms [cible:Mention/ID]
```

### Whois

**Alias:** whoami

Montre les informations sur un utilisateur

**Utilisation :**&#x20;

```
Whois [Utilisateur:Member]
```

## Fun 🎉

### Define

**Alias:** df

Regarde une définition dans un dictionnaire, vue paginée par défaut.

**Utilisation :**&#x20;

```
Define <Sujet:Texte>
```

```
[-raw raw:Switch - Sortie brute]
```

### Weather

**Alias:** w

Montre la météo à un endroit

**Utilisation :**&#x20;

```
Weather <Où:Text>
```

### Topic

Génère un sujet de conversation - en anglais - pour aider le chat à s'animer.

**Utilisation :**&#x20;

```
Topic
```

### CatFact

**Alias:** cf/cat/catfacts

Des petits faits sur les chats

**Utilisation :**&#x20;

```
CatFact
```

### DadJoke

Génère une blague de papa en utilisant l'API de icanhazdadjoke.

**Utilisation :**&#x20;

```
DadJoke
```

### DogFact

**Aliases:** dog/dogfacts

Fait sur les chiens

**Utilisation :**&#x20;

```
DogFact
```

### Advice

Ne soyez pas effrayé de demander un conseil !

**Utilisation :**&#x20;

```
Advice [Quoi:Texte]
```

### Throw

Jeter des choses est cool.

**Utilisation :**&#x20;

```
Throw [Cible:User]
```

### Roll

Roll dices, specify nothing for 6 sides, specify a number for max sides, or rpg dice syntax. \
Exemple: `-roll 2d6`

**Utilisation :**&#x20;

<pre><code>Roll &#x3C;Côtés:Whole number>
Roll &#x3C;<a data-footnote-ref href="#user-content-fn-1">RPG</a> Dice:Text>
Roll
</code></pre>

### WouldYouRather

**Alias:** wyr

2 options vous seront présentées.

**Utilisation :**&#x20;

```
WouldYouRather
```

```
[-raw raw:Switch - Sortie brute]
```

### Xkcd

Renvoie un comic xkcd, par défaut en retourne un aléatoire

**Utilisation :**&#x20;

```
Xkcd [Numéro du comic:Nombre entier]
```

```
[-l Dernier comic:Switch]
```

### Howlongtobeat

**Alias:** hltb

Information sur le jeu basée sur howlongtobeat.com. Les résultats sont classé par popularité, c'est leur choix. Sans l'option -p cela retourne le premier résultat. l'option -p donne une sortie paginée en utilisant le classement de Levenshtein, rangeant au plus 20 résultats

**Utilisation :**&#x20;

```
HowLongToBeat <Nom-du-jeu:Text>
```

```
[-c c:Switch - Sortie comptacte]
[-p p:Switch - Sortie paginée]
```

### Inspire

**Alias:** insp

Montre une citation de inspirobot.me...

**Utilisation :**&#x20;

```
Inspire
```

```
[-mindfulness mindfulness:Switch - Génère une citation pleine de sens !]
```

### Forex

**Alias:** Money

💱 Conversion d'une monnaie vers une autre.

**Utilisation :**&#x20;

```
Forex <Amount:Nombre décimal> <Depuis:Texte> <Vers:Texte>
```

### Roast

**Alias:** insult

Envoie une "pique" aléatoire

**Utilisation :**&#x20;

```
Roast [Target:User]
```

### TopServers

Répond avec les 15 plus gros serveurs sur lequel je suis

**Utilisation :**&#x20;

```
TopServers [Skip:Nombre entier - Entrée à sauter]
```

```
[-id serverID:Nombre entier]
```

### dictionary

**Alias:** owldict/owl/dict

Récupère la définition d'un mot anglais depuis le dictionaryapi.dev

**Utilisation :**&#x20;

```
dictionary <Query:Texte - Mot à rechercher>
```

### TakeRep

**Alias:** -/tr/trep/-rep

Enlève de la rep à quelqu'un

**Utilisation :**&#x20;

```
TakeRep <User:Utilisateur> [Num:Nombre entier]
```

### GiveRep

**Alias:** +/gr/grep/+rep

Donne de la rep à quelqu'un

**Utilisation :**&#x20;

```
GiveRep <User:Utilisateur> [Num:Nombre entier]
```

### SetRep

**Alias:** SetRepID

Définir la réputation de quelqu'un, c'est une commande administrateur et ne respecte pas les cooldowns et autres restrictions.

**Utilisation :**&#x20;

```
SetRep <Utilisateur:Mention/ID> <Nombre:Nombre entier>
```

### DelRep

Supprime quelqu'un de la liste de réputation complètement, ceci ne peut pas être annulé.

**Utilisation :**&#x20;

```
DelRep <Utilisateur:Mention/ID>
```

### RepLog

**Alias:** replogs

Montre l'historique de réputation d'un utilisateur.

**Utilisation :**&#x20;

```
RepLog <Utilisateur:Mention/ID> [Page:Nombre entier]
```

### Rep

Montre votre réputation et votre rang ou ceux de l'utilisateur mentionné

**Utilisation :**&#x20;

```
Rep [Utilisateur:User]
```

### TopRep

Montre le classement du serveur

**Utilisation :**&#x20;

```
TopRep [Décalage:Nombre entier]
```

```
[-user user:Mention/ID - Utilisateur à rechercher dans le classement]
```

### 8Ball

Posez une question à 8ball

**Utilisation :**&#x20;

```
8Ball [Question:Texte]
```

### Soundboard

**Alias:** sb

Jouer ou lister les sons du soundboard

**Usage:**

```
Soundboard [Nom:Texte]
```

### SoundboardReset

**Alias:** sbclose/sbreset

Réinitialise le Player du Soundboard

**Utilisation :**&#x20;

```
SoundboardReset
```

### cah Create

**Alias:** c

Creates a Cards Against Humanity game in this channel, add packs after commands, or \* for all packs. (-v for vote mode without a card czar).

**Usage:**

```
Create [packs:Text - Packs seperated by space, or * for all of them.]
```

```
[-v Vote mode - players vote instead of having a card czar.:Switch]
```

### cah End

Ends a Cards Against Humanity game that is ongoing in this channel.

**Usage:**

```
End
```

### cah Kick

Kicks a player from the ongoing Cards Against Humanity game in this channel.

**Usage:**

```
Kick <user:Mention/ID>
```

### cah Packs

Lists all available packs.

**Usage:**

```
Packs
```

## Debug & Maintenance 🖥

### allocstat

Memory statistics. Bot Admin Only

**Usage:**

```
allocstat
```

### banserver

Bans the specified server from using the bot. YAGPDB will leave the server, and leave whenever invited back. Bot Owner Only

**Usage:**

```
banserver <server:Whole number>
```

### ccreqs

Returns the number of concurrent requests currently going on. Bot Admin Only

**Usage:**

```
ccreqs
```

### createinvite

Maintenance command, creates an invite for the specified server. Bot Admin Only

**Usage:**

```
createinvite <server:Whole number>
```

### CurrentShard

**Aliases:** cshard

Shows the current shard this server is on (or the one specified

**Usage:**

```
CurrentShard [serverid:Whole number]
```

### dcallvoice

Disconnects from all the voice channels the bot is in. Bot Admin Only

**Usage:**

```
dcallvoice
```

### findserver

**Aliases:** findservers

Looks for a server by server name or the servers a user owns. Bot Admin Only

**Usage:**

```
findserver
```

```
[-name name:Text]
[-user user:Mention/ID]
```

### generatepremiumcode

**Aliases:** gpc

Generates premium codes. Bot Owner Only

**Usage:**

```
generatepremiumcode <Duration:Duration> <NumCodes:Whole number> <Message:Text>
```

### globalrl

Tests the global ratelimit functionality. Bot Owner Only

**Usage:**

```
globalrl
```

### IsGuildUnavailable

Returns wether the specified guild is unavilable or not

**Usage:**

```
IsGuildUnavailable <guildid:Whole number>
```

### leaveserver

Causes YAGPDB to leave the specified server. The bot may still be invited back with full functionality restored. Bot Owner Only

**Usage:**

```
leaveserver <server:Whole number>
```

### listflags

Lists feature flags for the current, or optional provided guild. Bot Owner Only

**Usage:**

```
listflags
```

### memstats

Full memory statistics. Bot Owner Only

**Usage:**

```
memstats
```

### Roledbg

Returns count of autorole assignments currently being processed

**Usage:**

```
Roledbg
```

### setstatus

Sets the bot's status and optional streaming url. Bot Admin Only

**Usage:**

```
setstatus [status:Text]
```

```
[-url url:Text]
```

### sleep

Maintenance command, used to test command queueing. Bot Admin Only

**Usage:**

```
sleep
```

### state botmember/guild/member

Responds with state debug info. Bot Admin Only

**Usage:**

```
state botmember
state guild

state member
[-fetch fetch:Switch - fetch the member if not in state]
```

### stateinfo

Responds with state debug info

**Usage:**

```
stateinfo
```

### testreddit

Tests the reddit feeds in this server by checking the specified post. Bot Owner Only

**Usage:**

```
testreddit <post-id:Text>
```

### toggledbg

Toggles Debug Logging. Restarting the bot will always reset debug logging. Bot Owner Only

**Usage:**

```
toggledbg
```

### topcommands

Shows command usage stats

**Usage:**

```
topcommands [hours:Whole number]
```

### topevents

Shows gateway event processing stats for all or one shard

**Usage:**

```
topevents [shard:Whole number]
```

### topgames

Shows the top games on this server

**Usage:**

```
topgames
```

```
[-all all:Switch]
```

### unbanserver

Removes the bot ban from the specified server. Bot Owner Only

**Usage:**

```
unbanserver <server:Text>
```

### Viewperms

Shows you or the targets permissions in this channel

**Usage:**

```
ViewPerms [target:Mention/ID]
```

### Yagstatus

**Aliases:** status

Shows yagpdb status, version, uptime, memory stats, and so on

**Usage:**

```
Yagstatus
```

## Moderation 👮

{% hint style="info" %}
All auto-moderation commands `automod ...` affect Automoderator v2.
{% endhint %}

### Ban

**Aliases:** banid

Bans a member, specify a duration with -d and specify number of days of messages to delete with -ddays (0 to 7)

**Usage:**

```
Ban <User:Mention/ID> <Duration:Duration> <Reason:Text>
Ban <User:Mention/ID> <Reason:Text> <Duration:Duration>
Ban <User:Mention/ID> <Duration:Duration>
Ban <User:Mention/ID> <Reason:Text>
Ban <User:Mention/ID>
```

```
[-ddays Days:Whole number]
```

### Unban

**Aliases:** unbanid

Unbans a user. Reason requirement is same as ban command setting.

**Usage:**

```
Unban <User:Mention/ID> [Reason:Text]
```

### Kick

Kicks a member

```
[-cl cl:Whole number - Messages to delete]
```

**Usage:**

```
Kick <User:Mention/ID> [Reason:Text]
```

### Mute

Mutes a member

**Usage:**

```
Mute <User:User Mention> <Duration:Duration> <Reason:Text>
Mute <User:User Mention> <Reason:Text> <Duration:Duration>
Mute <User:User Mention> <Duration:Duration>
Mute <User:User Mention> <Reason:Text>
Mute <User:User Mention>
```

### Unmute

Unmutes a member

**Usage:**

```
Unmute <User:User Mention> [Reason:Text]
```

### Timeout

**Aliases:** to

Timeout a member

**Usage:**

```
Timeout <User:Mention/ID> <Duration:Duration> <Reason:Text>
Timeout <User:Mention/ID> <Reason:Text> <Duration:Duration>
Timeout <User:Mention/ID> <Duration:Duration>
Timeout <User:Mention/ID> <Reason:Text>
Timeout <User:Mention/ID>
```

### RemoveTimeout

**Aliases:** untimeout/cleartimeout/deltimeout/rto

Removes a member's timeout

**Usage:**

```
RemoveTimeout <User:Mention/ID> [Reason:Text]
```

### Report

Reports a member to the server's staff

**Usage:**

```
Report <User:Mention/ID> <Reason:Text>
```

### Clean

**Aliases:** clear/cl

[Will not delete messages older than 2 weeks.](https://discord.com/developers/docs/resources/channel#bulk-delete-messages)\
\
Delete the last number of messages from chat, optionally filtering by user, max age and regex or ignoring pinned messages.\
**Warning:** Using `clean <userId> <amount>` does not work. This is because the user ID is interpreted as the amount. As it is over the limit of 100, it is treated as invalid. You can use `clean <amount> <userId>` instead or mention the user. Specify a regex with "-r regex\_here" and max age with "-ma 1h10m" You can invert the regex match (i.e. only clear messages that do not match the given regex) by supplying the `-im` flag.\
Note: Will only look in the last 1k messages

**Usage:**

```
Clean <Num:Whole number>
Clean <Num:Whole number> <User:User Mention>
Clean <User:User Mention> <Num:Whole number>
```

```
[-r r:Text - Regex]
[-im im:Switch - Invert regex match]
[-ma ma:Duration - Max age]
[-minage minage:Duration - Min age]
[-i i:Switch - Regex case insensitive]
[-nopin nopin:Switch - Ignore pinned messages]
[-a a:Switch - Only remove messages with attachments]
[-to to:Whole number - Stop at this msg ID]
[-from from:Whole number - Start at this msg ID]]
```

### Reason

Add/Edit a modlog reason

**Usage:**

```
Reason <ID:Whole number> <Reason:Text>
```

### Warn

Warns a user, warnings are saved using the bot. Use -warnings to view them.

**Usage:**

```
Warn <User:User Mention> <Reason:Text>
```

### Warnings

**Aliases:** Warns

Lists warning of a user.

**Usage:**

```
Warnings <User:Mention/ID>
```

### EditWarning

Edit a warning, id is the first number of each warning from the warnings command

**Usage:**

```
EditWarning <Id:Whole number> <NewMessage:Text>
```

### DelWarning

**Aliases:** dw/delwarn/deletewarning

Deletes a warning, id is the first number of each warning from the warnings command

**Usage:**

```
DelWarning <Id:Whole number> [Reason:Text]
```

### ClearWarnings

**Aliases:** clw

Clears the warnings of a user

**Usage:**

```
ClearWarnings <User:Mention/ID> [Reason:Text]
```

### TopWarnings

**Aliases:** topwarns

Shows ranked list of warnings on the server.

**Usage:**

```
TopWarnings [Page:Whole number]
```

```
[-id List UserIDs:Switch]
```

### GiveRole

**Aliases:** grole/arole/addrole

Gives a role to the specified member, with optional expiry

**Usage:**

```
GiveRole <User:Mention/ID> <Role:Text> [Duration:Duration]
```

### TakeRole

**Aliases:** rrole/takearole/trole

Removes the specified role from the target

**Usage:**

```
RemoveRole <User:Mention/ID> <Role:Text>
```

### automod Rulesets

**Aliases:** r/list/l

Lists all rulesets and their status

**Usage:**

```
Rulesets
```

### automod Toggle

**Aliases:** t

Toggles a ruleset on/off

**Usage:**

```
Toggle <ruleset name:Text>
```

### automod Logs

**Aliases:** log

Shows the log of the last triggered automod rules, optionally filtering by user

**Usage:**

```
Logs [skip:Whole number]
```

```
[-user :Mention/ID]
```

### automod ListViolations

**Aliases:** Violations/ViolationLogs/VLogs/VLog

Lists Violations of specified user /n old flag posts oldest violations in first page ( from oldest to newest ).

**Usage:**

```
ListViolations <User:Mention/ID> [Page Number:Whole number]
```

```
[-old Oldest First:Switch]
```

### automod ListViolationsCount

**Aliases:** ViolationsCount/VCount

Lists Violations summary in entire server or of specified user optionally filtered by max violation age. Specify number of violations to skip while fetching using -skip flag ; max entries fetched 500.

**Usage:**

```
ListViolationsCount [User:Mention/ID]
```

```
[-ma Max Violation Age:Duration]
[-skip Amount Skipped:Whole number]
```

### automod DeleteViolation

**Aliases:** DelViolation/DelV/DV

Deletes a Violation with the specified ID. ID is the first number of each Violation in the ListViolations command.

**Usage:**

```
DeleteViolation <ID:Whole number>
```

### automod ClearViolations

**Aliases:** ClearV/ClrViolations/ClrV

Clears Violations of specified user optionally filtered by Name, Min/Max age and other conditions. By default, more recent violations are preferentially cleared.

**Usage:**

```
ClearViolations <User:Mention/ID> [Violation Name:Text]
```

```
[-ma Max Violation Age:Duration]
[-mina Min Violation Age:Duration]
[-num Max Violations Cleared:Whole number]
[-old Preferentially Clear Older Violations:Switch]
[-skip Amount Skipped:Whole number]
```

## Rolemenu 🔘

alias: `rmenu`

### RoleMenu Create

**Aliases:** c

Set up a role menu. Specify a message with -m to use an existing message instead of having the bot make one

To get the id of a message you have to turn on developer mode in discord's appearances settings then right click the message and copy id.

**Usage:**

```
Create <Group:Text>
```

```
[-m Message ID:Whole number]
[-nodm Disable DM:Switch]
[-rr Remove role on reaction removed:Switch]
[-skip Number of roles to skip:Whole number]
```

### RoleMenu EditOption

**Aliases:** edit

Allows you to reassign the emoji of an option, tip: use ResetReactions afterwards.

To get the id of a message you have to turn on developer mode in discord's appearances settings then right click the message and copy id.

**Usage:**

```
EditOption <Message ID:Whole number>
```

### RoleMenu Listgroups

**Aliases:** list/groups

Lists all role groups.

**Usage:**

```
Listgroups
```

### RoleMenu Remove

Removes a rolemenu from a message. The message won't be deleted and the bot will not do anything with reactions on that message

To get the id of a message you have to turn on developer mode in discord's appearances settings then right click the message and copy id.

**Usage:**

```
Remove <Message ID:Whole number>
```

### RoleMenu ResetReactions

**Aliases:** reset

Removes all reactions on the specified menu message and re-adds them. Can be used to fix the order after updating it.

To get the id of a message you have to turn on developer mode in discord's appearances settings then right click the message and copy id.

**Usage:**

```
ResetReactions <Message ID:Whole number>
```

### RoleMenu Update

**Aliases:** u

Updates a rolemenu, toggling the provided flags and adding missing options, aswell as updating the order.

To get the id of a message you have to turn on developer mode in discord's appearances settings then right click the message and copy id.

**Usage:**

```
Update <Message ID:Whole number>
```

```
[-nodm Disable DM:Switch]
[-rr Remove role on reaction removed:Switch]
```

## Tickets 🎫

alias: `ticket`

### Tickets Open

**Aliases:** create/new/make

Opens a new ticket

**Usage:**

```
Open <subject:Text>
```

### Tickets AddUser

Adds a user to the ticket in this channel

**Usage:**

```
AddUser <target:Member>
```

### Tickets RemoveUser

Removes a user from the ticket

**Usage:**

```
RemoveUser <target:Member>
```

### Tickets Rename

Renames the ticket

**Usage:**

```
Rename <new-name:Text>
```

### Tickets Close

**Aliases:** end/delete

Closes the ticket

**Usage:**

```
Close [reason:Text]
```

### Tickets AdminsOnly

**Aliases:** adminonly/ao

Toggle admins only mode for this ticket

**Usage:**

```
AdminsOnly
```

## Events 🎟

alias: `event`

### Events Create

**Aliases:** new/make

Creates an event, You will be led through an interactive setup

**Usage:**

```
Create
```

### Events Edit

Edits an event

**Usage:**

```
Edit <ID:Whole number>
```

```
[-title :Text - Change the title of the event]
[-time :Text - Change the start time of the event]
[-max :Whole number - Change max participants]
```

### Events List

**Aliases:** ls

Lists all events in this server

**Usage:**

```
List 
```

### Events Delete

**Aliases:** rm/del

Deletes an event, specify the event ID of the event you wanna delete

**Usage:**

```
Delete <ID:Whole number>
```

### Events StopSetup

**Aliases:** cancelsetup

Force cancels the current setup session in this channel

**Usage:**

```
StopSetup
```

[^1]: RPG : Role-Play Game : Jeu de Rôle
