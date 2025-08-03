# Functions

---
### `cb.say(message:str,name:str=None,mode:str="markdown")`  
Sends a message to public chat.
!!! note
    This function requires the `say` capability which must be manually granted by server staff. Most licenses do not have this capability.
**Example:**
```python
await cb.say("We're no strangers to love")
```

---
### `cb.tell(self,user:str|IngameUser,message:str,name:str=None,mode:str="markdown")`  
Sends a private message to a user.

**Example:**
```python
await cb.tell("HerrKatzeGaming", "You know the rules, and so do I")
```

---
### Formatting Modes
Any of these formatting modes can be chosen, These functions will default to `markdown` if unset

| Format&nbsp;Type&nbsp;&nbsp;| Description                                                                           |
|-----------------|:----------------------------------------------------------------------------------------------|
| `markdown`      | Discord-like markdown formatting. Supports URLs, but not colours.                             |
| `format`        | Minecraft-like formatting strings (e.g. `&e` for yellow). Supports colours, but not URLs.     |
| `minimessage`   | HTML-like formatting strings (e.g. `<yellow></yellow>` for yellow). Supports colours and hover events. |
