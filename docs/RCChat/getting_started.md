# Getting Started
To use RCChat, you will need a license key. This is obtained ingame using  
`/chatbox license register`  
---
The general structure of a program using RCChat is as follows:
```python
import rcchat
import asyncio
async def main()
    cb = rcchat.chatbox.create("<your-license-key>")# Create chatbox instance
    
    @cb.on_command("example"): # Register Event Handlers
    async def example_command(event: command):
        await cb.tell(event.user, "Example Command!")
        
    await asyncio.Event().wait() # Wait forever so that the chatbox commands will actually execute.

asyncio.run(main()) # Run the main function.
```
---

A list of Event handlers can be found at [Event Handlers](/RCChat/event_handlers)  
The data types that get provided can be found in [Data Types](/RCChat/data_types)
