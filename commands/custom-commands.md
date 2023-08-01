---
description: Les commandes personnalisées
---

# Custom Commands

Les commandes personnalisées - Custom Commands abrégées en CCs en anglais -, vous permette de créer vos propres commandes. Le système de CC de YAGPDB est plutôt complexe et peut être utilisé pour faire des systèmes avancés, mais les CC sont quand même limitées et si votre système est extrêmement spécifique, il faudra peut-être considérer l'utilisation d'un autre bot, ou la création du votre. Vous pouvez aussi consulter le [cette page en anglais](https://learn.yagpdb.xyz/the-custom-command-interface). Les commandes personnalisées ont des limites qui sont expliquées [ici](https://docs.yagpdb.xyz/reference/custom-commands-limits).

## Custom Commands - Commandes personnalisées

Pour créer votre première commande personnalisée, allez sur votre panneau de commande, puis cliquez sur **Commands** puis **Custom Commands**.

![La page de création d'une commande personnalisée](../.gitbook/assets/image\_custom\_commands.png)

### Les types de déclencheur

* **Command**: Avec ce déclencheur, le message déclencheur doit commencer par le préfixe de votre serveur (`-` par défaut) suivi par le texte déclencheur.
* **Starts with**: Quand le message commence par le texte déclencheur.
* **Contains**: Quand le message contient le déclencheur.
* **Regex**: Ce déclencheur vous permet d'utiliser une [expression régulière](#user-content-fn-1)[^1]. (Vous pouvez consulter la page [regex.md](../reference/regex.md "mention") pour de l'aide).
* **Exact match**: Quand le message entier correspond à votre déclencheur.
* **Reaction:** La CC est déclenchée par la réaction à un message.
* **Hourly interval**: Une commande avec ce déclencheur s'exécutera après un temps spécifié en heures, vous pouvez exclure certaines heures et jours de la semaine. Un salon soit être sélectionné pour que ce déclencheur fonctionne.
* **Minute interval**: Comme pour le "**Hourly interval**", sauf que le temps est en minute et doit être au minimum de 5 minutes.

#### Case Sensitivity - Sensibilité à la casse

Comme vous l'avez sûrement remarqué, il y a une option _Case sensitive_. Cette option rend votre déclencheur sensible à la casse. Le déclencheur heLLo avec l'option activée se déclenchera si une personne écrit `heLLo` mais pas si elle dit `hello`.

### Restrictions to roles or channels - Restrictions de rôles et salons

Vous pouvez restreindre ou bloquer l'exécution de CC à des rôles ou salons spécifiques. Pour cela, sélectionner la case à cocher correspondante et sélectionnez les rôles/salons selon vos besoins.

![Cette commande personnalisée peut être exécutée par les personnes qui ont soit le rôle Coll Dog, soit Guy-in-charge ou les deux.](../.gitbook/assets/image\_custom\_commands\_restrictions.png)

{% hint style="warning" %}
Si vous sélectionnez les options \*\*`Require at least one of the`**ou**`Only run in the`\*\*, assurez-vous d'avoir au minimum un rôle/salon de sélectionné, sinon, le bot ne réagira pas à vos commandes.
{% endhint %}

### Restrictions et limitations

Les commandes personnalisées ont quelques limites :

* Vous ne pouvez pas créer plus de 100 commandes personnalisées activées en même temps (250 avec YAGPDB Premium)
* Vous ne pouvez pas exécuter plus de 5 commandes depuis une commande personnalisée en utilisant `execAdmin` ou `exec`
* Les messages privés ne peuvent être envoyés qu'avec une note qui indique le serveur de provenance du message privé
* Les réponses des Commandes personnalisées ne peuvent pas excéder 2000 caractères (c'est une limite de Discord).
* La commande elle-même ne peut pas être plus longue que 10 000 caractères (c'est une somme de tous les caractères et une somme de tous les comptes des [sous-parties des commandes](#user-content-fn-2)[^2]), et la limite des messages lorsqu'une personne rejoint/quitte le serveur est de 5000 caractères.
* Les commandes personnalisées ont des [limites](https://docs.yagpdb.xyz/reference/custom-commands-limits).
* Pas plus de 3 commandes personnalisées peuvent être exécutées depuis un seul message pour les serveurs non premium. La limite est de 5 pour les serveurs premium.

## Advanced Custom Commands - Commandes personnalisées avancées

{% hint style="info" %}
Quelques bases en codage peuvent être requises pour utiliser ces fonctionnalités.
{% endhint %}

### Utiliser des modèles dans les commandes personnalisées

Si vous souhaitez faire plus que _"Faîtes une commandes" -> "Faire répondre quelque chose au bot_"_._ Comme assigner des rôles aux personnes, récupérer des informations sur les personnes qui exécutent des commandes, envoyer des messages dans d'autres salons, et plus encore. Il est recommandé de consulter cette page :

{% content-ref url="../reference/templates/" %}
[templates](../reference/templates/)
{% endcontent-ref %}

### Arguments requis

Depuis la v1.12 il y a un ensemble de fonctions assez simple pour gérer les arguments,  l'ensemble est :

```go
{{$args := parseArgs nombre-arg-requis "Texte affiché lorsque les arguments sont incorrects"
    (carg "int" "nom de l'arg1")
    (carg "string" "nom de l'arg2")
    (plus d'arguments peuvent être ajoutés...)}}
...

{{$args.Get 0}} {{/* <- pour obtenir le premier argument */}}
{{$args.Get 1}} {{/* <- pour obtenir le second argument */}}
```

L'exécution de la commande s'arrêtera au moment où "**parseArgs**" est écrit si jamais des arguments incorrects sont passés.

"**carg**" a la syntaxe suivante:

```
{{carg "type" "nom" options-additionnelles-selon-le-type}}
```

Les types et options disponibles sont :

* **channel -** id/mention de salon, l'argument aura le type _\*templates.CtxChannel_ (consultez [templates](../reference/templates/ "mention")[ ](../reference/templates/#channel)pour plus d'infos). Les fils (Threads) ne sont pas supportés.
* **duration** - converti le nombre donné en minutes ou depuis une chaîne de caractères avec les modificateurs (s, m, h, w etc) vers le type Duration (_Durée_) - ex. 10 = 10m0s et 123s = 2m3s (le type _time.Duration_ est de type _int64_ en nanosecondes - donc 5s sera 5000000000). Il y a deux options additionnelles pour la durée minimum et maximum en nanosecondes.
* **float -** nombres décimaux, vous pouvez spécifier un minimum et un maximum après le nom comme pour le **int**. Il est traité comme le type _float64_.
* **int -** Nombre entier, vous pouvez optionnellement spécifier un minimum et un maximum après le nom. Par exemple\
  `{{carg "int" "entiet" 2 9}}` créera un argument qui devra être un nombre entier compris entre 2 et 9.
* **member** - accepte un ID utilisateur ou une mention. Il renvoie une structure (_object_) de type membre de serveur à utiliser après avec les méthodes du .Member, comme .JoinedAt. (consultez [templates](../reference/templates/ "mention") pour plus d'informations).
* **role** - correspond à un ID ou un nom de rôle et retourne un [objet de type rôle](https://discord.com/developers/docs/topics/permissions#role-object) _\*discordgo.Role_.
* **string -** texte. Si le type **string** est le dernier ou le seul `carg` dans une déclaration`parseArgs`, l'argument prendra tous les autres à partir de celui là.
* **user -** mention d'utilisateur, aura le type utilisateur (_User_) (consultez [templates](../reference/templates/ "mention") pour plus d'informations).
* **userid -** ID d'utilisateur, cet utilisateur peut ne pas exister, les mentions et les id complets sont acceptés, aura le type _int64_.

Pour accéder aux arguments, il faudre utiliser la méthode "**Get**" sur l'objet retourné par **parseArgs**, cette fonction prend en argument l'index de l'argument en commençant à 0.

La méthode "**IsSet**" retournera un booléen **true**/**false** selon si l'argument est défini ou non, si c'est unn argument optionnel.

Exemple d'utilisation des arguments optionnels :

```go
{{$args := parseArgs 1 "Message personnalisé si les arguments sont invalides"
    (carg "int" "nom de l'arg1")
    (carg "string" "nom de l'arg2 (optionnel)")
    (plus d'arguments peuvent être ajoutés...)}}
...

{{$args.Get 0}} {{/* <- pour obtenir le premier argument */}}
{{or ($args.Get 1) "Valeur si le second argument n'est pas défini"}}
{{if $args.IsSet 1}} s'exécute seulement si le second argument est défini {{end}}
```

### Le modèle Message

Vous pouvez récupérer un message avec son ID ou utiliser le [message déclencheur](../reference/templates/#message) et obtenir des informations sur celui-ci. Quelques champs (options) de l'objet message :

Message

| Field                | Type                                                                       | Description                                                                                               |
| -------------------- | -------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| .Message.ID          | Int                                                                        | ID du message                                                                                             |
| .Message.ChannelID   | Int                                                                        | ID du salon dans lequel le message est                                                                    |
| .Message.Author      | [User Object](../reference/templates/#user)                                | Auteur du message (User object)                                                                           |
| .Message.Timestamp   | String                                                                     | Timestampdu message (utilisez `.Message.Timestamp.Parse` pour un objet _Time_, sinon ce sera un _string_) |
| .Message.Attachments | Array of [Attachments](custom-commands.md#attachment)                      | Fichiers joints au message (slice d'objets de type attachment)                                            |
| .Message.Embeds      | Array of [Embeds](../reference/custom-embeds.md#embeds-in-custom-commands) | Embeds sur ce message (slice d'objets de type embed)                                                      |
| .Message.Mentions    | Array of [User Object](../reference/templates/#user)                       | Les utilisateurs mentionnés dand le message                                                               |
| .Message.Reactions   | Array of [Reactions](custom-commands.md#reaction)                          | Reactions sur ce message (seulement disponible avec `getMessage`)                                         |
| .Message.Content     | String                                                                     | Contenu texte du message                                                                                  |

#### Attachment

Il faut commencer par `(index .Message.Attachments 0).` ou une variable de type **attachment**.

| Field     | Type   | Description                                     |
| --------- | ------ | ----------------------------------------------- |
| .ID       | Int    | L'ID du fichier joint                           |
| .URL      | String | URL avec cdn.discordapp.com                     |
| .ProxyURL | String | URL avec media.discordapp.com                   |
| .Filename | String | Nom du fichier                                  |
| .Width    | Int    | Largeur en pixel du fichier, si c'est une image |
| .Height   | Int    | Hauteur en pixel du fichier, si c'est une image |
| .Size     | Int    | Taille du fichier, en octet                     |

#### Reaction

Il faut commencer par `(index .Message.Reactions 0)` ou une variable de type reaction.

| Field  | Type                              | Description                                |
| ------ | --------------------------------- | ------------------------------------------ |
| .Count | Int                               | Nombre de fois que cet émoji a été utilisé |
| .Emoji | [Emoji](custom-commands.md#emoji) | L'émoji utilisé dans la réaction           |

#### Emoji

Il faut commencer par `(index .Message.Reactions 0).Emoji` ou une varible de type emoji.

| Field     | Type    | Description                                                        |
| --------- | ------- | ------------------------------------------------------------------ |
| .ID       | Int     | ID de l'émoji                                                      |
| .Name     | String  | Nom de l'emoji (Si c'est un émoji Unicode, ce sera l'émoji (`😀`)) |
| .Animated | Boolean | Si l'émoji est animé ou non                                        |

| **Method**       | **Description**                                                                                                          |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------ |
| `.APIName`       | Retourne un nom d'API correctement formaté utilisable avec les fonctions de réaction. Exemple de sortie : `emojiname:id` |
| `.MessageFormat` | Retourne un émoji correctement formaté pour l'utilisation dans un message.                                               |

il y a [plus de champs ](https://discordapp.com/developers/docs/resources/channel#reaction-object)qui peuvent être utilisés, mais ils sont soit obsolètes ou alors uniquement utilisés avec les Emotes Globales.\
Exemple de la récupération de la première réaction sur un message récupéré via la fonction `getMessage` :

```go
{{$message := getMessage nil (index .Args 1)}}
{{if $message}}
    {{if $message.Reactions}}
        Nom de la première réaction: {{(index $message.Reactions 0).Emoji.Name}}
    {{else}}
        Aucune réaction sur ce message
    {{end}}
{{else}}
    Message inconnu
{{end}}
```

### Le modèle currentTime

Le modèle currentTime est très complet et peut être utilisé pour afficher l'heure actuelle, pour différents fuseaux horaires, ou dans les embeds dans le champ "timestamp".\
\
Exploré plus en profondeur ici > [https://golang.org/pkg/time/](https://golang.org/pkg/time/)

{% code title="Exemple de timestamp dans un embed" %}
```go
{{ $embed := cembed "timestamp" currentTime }}
```
{% endcode %}

```go
{{/* Le formattage du temps en golang est sous la forme POSIX 0 1 2 3 4 5 6 > Mon 2 Jan 15:04:05 2006 (le calcul du fuseau horaire est omis) */}}
{{/* currentTime.UTC.Format "15:04"  > donne l'heure actuelle dans le fuseau UTC */}}
{{/* ".Add" ajoute du temps en nanosecondes, dans cet exemple, 2 heures ont été ajoutées pour le fuseau UTC+2 */}}
{{ $marker := "void" }}

{{ if gt ( toInt ( currentTime.UTC.Format "15" ) ) 12 }}
{{ $marker = "PM" }}
{{ else }}
{{ $marker = "AM" }}
{{ end }}

{{/* heure actuelle dans le fuseau UTC+2 dans le format 12H */}}
{{ ( joinStr " " ( ( currentTime.Add 7200000000000 ).Format "3:04"  ) $marker ) }}

It's the {{currentTime.Day}}. of {{currentTime.Month}} in the year {{currentTime.Year}}!
{{/*Conseil avancé : vous pouvez ajouter PM dans la chaîne de format "3:04PM"
la variable $marker est là juste pour la comparaison avec la structure if.
Plus ici > https://golang.org/pkg/time/#pkg-constants*/}}
```

### Exemples de commandes personnalisées

Vous pouvez retrouver quelques exemples sur le serveur communautaire et de support de YAGPDB ou dans cette page (avec des explications) :

{% content-ref url="../reference/custom-command-examples.md" %}
[custom-command-examples.md](../reference/custom-command-examples.md)
{% endcontent-ref %}

[^1]: Une expression régulière (Regular Expression, souvent abrégée en regex ou RegEx) décrit un motif, un pattern que nous souhaitons rechercher et localiser dans du texte (y compris des chiffres).

[^2]: Vous pouvez diviser les commandes en plusieurs parties
