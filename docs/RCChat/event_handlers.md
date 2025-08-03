## Event Decorators
These decorators are methods of the instance of the `chatbox` class.
Example: 
```python
@cb.on_chat_ingame
```
---
### `on_chat_ingame`  
The function must take a `chat_ingame` event as its only parameter.  
**Example:**
```python
@cb.on_chat_ingame
async def handle_ingame(event: chat_ingame):
    print(f"[Ingame] {event.user.displayName}: {event.text}")
```

---

### `on_chat_discord`  
The function must take a `chat_discord` event as its only parameter.  
**Example:**
```python
@cb.on_chat_discord
async def handle_discord(event: chat_discord):
    print(f"[Discord] {event.discordUser.displayName}: {event.text}")
```

---

### `on_command(filter)`  
The function must take a `command` event as its only parameter.


You can optionally filter the command using `@cb.on_command("command_name")`.

**Examples:**

Without a filter (triggers on all commands):
```python
@cb.on_command()
async def handle_any_command(event: command):
    print(f"{event.user.name} ran: {event.command} {event.args}")
```

With a filter:
```python
@cb.on_command("ping")
async def ping_handler(event: command):
    await cb.tell(event.user, "Pong!")
```

---

### `on_join`  
The function must take a `join` event as its only parameter.  
**Example:**
```python
@cb.on_join
async def welcome(event: join):
    print(f"{event.user.displayName} joined the server!")
```

---

### `on_leave`  
The function must take a `leave` event as its only parameter.  
**Example:**
```python
@cb.on_leave
async def farewell(event: leave):
    print(f"{event.user.displayName} left the server.")
```

---

### `on_death`  
The function must take a `death` event as its only parameter.  
**Example:**
```python
@cb.on_death
async def deathlog(event: death):
    print(f"Death: {event.text}")
```

---

### `on_world_change`  
The function must take a `world_change` event as its only parameter.  
**Example:**
```python
@cb.on_world_change
async def world_switch(event: world_change):
    print(f"{event.user.displayName} moved from {event.origin} to {event.destination}")
```

---

### `on_event`  
The function must take a generic `Event` object — this will be an instance of one of the known event types (`chat_ingame`, `join`, etc.).  
Use `isinstance()` to check the type if needed.  
**Example:**
```python
@cb.on_event
async def debug_all(event: Event):
    print(f"Received event: {type(event).__name__}")
```

