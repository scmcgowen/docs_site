# Data Types
## Objects
---

### `IngameUser`


| Field         | Type              | Description                                |
|---------------|-------------------|--------------------------------------------|
| `name`        | `str`             | Username (typically lowercase)             |
| `uuid`        | `str`             | Unique player identifier                   |
| `displayName` | `str`             | Player’s display name                      |
| `group`       | `str`             | User's permission group                    |
| `pronouns`    | `Optional[str]`   | Optional user pronouns                     |
| `world`       | `Optional[str]`   | Current world name                         |
| `afk`         | `bool`            | Whether the player is AFK                  |
| `alt`         | `bool`            | Whether the account is an alt              |
| `bot`         | `bool`            | Whether the account is a bot               |
| `supporter`   | `int`             | Supporter level                            |
| `linkedUser`  | `Optional[DiscordUser]` | Associated Discord user if linked     |

---

### `DiscordRole`

| Field   | Type     | Description               |
|---------|----------|---------------------------|
| `id`    | `str`    | Role ID                   |
| `name`  | `str`    | Role name                 |
| `colour`| `int`    | Color code of the role    |

---

### `DiscordUser`

| Field         | Type                | Description                              |
|---------------|---------------------|------------------------------------------|
| `id`          | `str`               | Discord user ID                          |
| `name`        | `str`               | Username                                 |
| `displayName` | `str`               | Server display name                      |
| `discriminator` | `Optional[str]`   | Legacy Discord tag                       |
| `avatar`      | `str`               | Avatar hash                              |
| `roles`       | `list[DiscordRole]` | List of user roles                       |
| `linkedUser`  | `Optional[IngameUser]` | Associated in-game user if linked     |

---
## Events
---

### `chat_ingame`

| Field         | Type           | Description                                           |
|---------------|----------------|-------------------------------------------------------|
| `text`        | `str`          | Message content                                       |
| `rawText`     | `str`          | Raw unprocessed text                                  |
| `renderedText`| `dict`         | Minecraft JSON Text Format                            |
| `user`        | `IngameUser`   | Player who sent the message                           |
| `time`        | `str`          | The time (as ISO-8601) this message was sent         |

---

### `chat_discord`

| Field         | Type            | Description                                           |
|---------------|-----------------|-------------------------------------------------------|
| `text`        | `str`           | Message content                                       |
| `rawText`     | `str`           | Raw unprocessed text                                  |
| `renderedText`| `dict`          | Minecraft JSON Text Format                            |
| `discordId`   | `str`           | Discord user ID                                       |
| `discordUser` | `DiscordUser`   | Full Discord user info                                |
| `edited`      | `bool`          | Whether the message was edited                        |
| `time`        | `str`           | The time (as ISO-8601) this message was sent         |

---

### `command`

| Field        | Type            | Description                                           |
|--------------|-----------------|-------------------------------------------------------|
| `user`       | `IngameUser`    | Player who ran the command                            |
| `command`    | `str`           | The command name                                      |
| `args`       | `list[str]`     | Arguments passed with the command                     |
| `ownerOnly`  | `bool`          | Whether this is owner-only                            |
| `time`       | `str`           | The time (as ISO-8601) this command was issued       |

---

### `join`

| Field  | Type         | Description                                               |
|--------|--------------|-----------------------------------------------------------|
| `user` | `IngameUser` | The player who joined                                     |
| `time` | `str`        | The time (as ISO-8601) this player joined the server     |

---

### `leave`

| Field  | Type         | Description                                               |
|--------|--------------|-----------------------------------------------------------|
| `user` | `IngameUser` | The player who left                                       |
| `time` | `str`        | The time (as ISO-8601) this player left the server       |

---

### `death`

| Field         | Type                  | Description                                               |
|---------------|-----------------------|-----------------------------------------------------------|
| `text`        | `str`                 | Death message                                             |
| `rawText`     | `str`                 | Unformatted message                                       |
| `renderedText`| `dict`                | Minecraft JSON Text Format                                |
| `user`        | `IngameUser`          | Player who died                                           |
| `source`      | `Optional[IngameUser]`| Player who caused the death (if any)                      |
| `time`        | `str`                 | The time (as ISO-8601) this player died according to the server |

---

### `world_change`

| Field        | Type         | Description                                                  |
|--------------|--------------|--------------------------------------------------------------|
| `user`       | `IngameUser` | Player who changed worlds                                    |
| `origin`     | `str`        | Name of the original world                                   |
| `destination`| `str`        | Name of the destination world                                |

---
