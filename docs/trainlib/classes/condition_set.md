# Condition Sets
Condition Sets come in 2 forms, OR and AND

## Condition Set (OR)
Contains [Condition Sets (AND)](/trainlib/classes/condition_set/#condition-set-and), TrainLib automatically generates these when adding a [Condition](/trainlib/classes/condition) to the set.
### Methods
`set:addCondition(condition)` - Accepts a [Condition Set (AND)](/trainlib/classes/condition_set/#condition-set-and) or a [Condition](/trainlib/classes/condition) and adds it to the set.  
Conditions are automatically wrapped in [Condition Set (AND)](/trainlib/classes/condition_set/#condition-set-and) when being added.  
Returns itself for chaining.

## Condition Set (AND)
Contains [Conditions](/trainlib/classes/condition), and are contained by [Condition Sets (OR)](/trainlib/classes/condition_set/#condition-set-or)
### Methods
`set:addCondition(condition)` - Accepts a [Condition](/trainlib/classes/condition) and adds it to the set.  
Returns itself for chaining.
