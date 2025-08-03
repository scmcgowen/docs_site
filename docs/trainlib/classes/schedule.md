# Schedule
The Schedule object allows you to create train schedule. After creating it, pass it to `setSchedule` on the Create Train Station  
Obtained from `trainlib.schedule()`

## Methods
`schedule:addEntry(entry)` - Takes an [Entry](/trainlib/classes/entry) and appends it to the end of the current schedule.  
Returns the Schedule for chaining.  

`schedule:setEntry(pos,entry)` - Sets the entry at postion `pos` to the entry provided.  
Returns the Schedule for chaining.  

`schedule:getEntry(pos)` - Gets the entry at position pos.  
Returns: [Entry](/trainlib/classes/entry)
