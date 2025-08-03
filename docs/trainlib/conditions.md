# Conditions
The `trainlib.conditions` table is a list of premade functions that make [Conditions](/trainlib/classes/condition)
# Methods
`trainlib.conditions.delay(value: number,time_unit: number)` - Makes the train wait for a certain amount of time.  
Valid values for time_unit are:  

| time_unit | Unit    |
|-----------|---------|
| 0         | ticks   |
| 1         | seconds |
| 2         | minutes |

`trainlib.conditions.time_of_day(hour: number,minute: number,rotation: number)` - Makes the train wait for a certain time of day.  
Valid Values for Rotation are:

| Rotation | Time Interval    |
|----------|------------------|
| 0        | Every Day        |
| 1        | Every 12 Hours   |
| 2        | Every 6 Hours    |
| 3        | Every 4 Hours    |
| 4        | Every 3 Hours    |
| 5        | Every 2 Hours    |
| 6        | Every Hour       |
| 7        | Every 45 Minutes |
| 8        | Every 30 Minutes |
| 9        | Every 15 Minutes |

`trainlib.conditions.fluid_threshold(bucket: trainlib.item,threshold: number,operator: number)` - Makes the train wait until the fluid cargo is at a given level
Bucket should be a [trainlib.item] of the bucket for the Fluid.
Threshold should be a positive integer in number of buckets of fluid.
Valid values for Operator are:

| Operator | Meaning      |
|----------|--------------|
| 0        | Greater Than |
| 1        | Less Than    |
| 2        | Equal To     |

