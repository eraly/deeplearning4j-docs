---
title: DataVec Conditions
short_title: Conditions
description: Rules for triggering operations and transformations.
category: DataVec
weight: 3
---

## Available conditions

### BooleanCondition
<span style="float:right;"> [[source]](https://github.com/deeplearning4j/deeplearning4j/tree/master/datavec/datavec-api/src/main/java/org/datavec/api/transform/condition/BooleanCondition.java) </span>

BooleanCondition: used for creating compound conditions,
such as AND(ConditionA, ConditionB, ...)<br>
As a BooleanCondition is a condition,
these can be chained together,
like NOT(OR(AND(...),AND(...)))


<button class="btn btn-primary" type="button" data-toggle="collapse" data-target="#BooleanCondition" aria-expanded="false" aria-controls="BooleanCondition">Show methods</button>
<div class="collapse" id="BooleanCondition"><div class="card card-body">

#### outputColumnName 
```java
public String outputColumnName() 
```


The output column name
after the operation has been applied

- return the output column name

#### columnName 
```java
public String columnName() 
```


The output column names
This will often be the same as the input

- return the output column names

#### condition 
```java
public boolean condition(Object input) 
```


Condition on arbitrary input

- param input the input to return
the condition for
- return true if the condition is met
false otherwise

#### conditionSequence 
```java
public boolean conditionSequence(Object sequence) 
```


Condition on arbitrary input

- param sequence the sequence to
do a condition on
- return true if the condition for the sequence is met false otherwise

#### transform 
```java
public Schema transform(Schema inputSchema) 
```


Get the output schema for this transformation, given an input schema

- param inputSchema

#### AND 
```java
public static Condition AND(Condition... conditions) 
```


And of all the given conditions
- param conditions the conditions to and
- return a joint and of all these conditions

#### OR 
```java
public static Condition OR(Condition... conditions) 
```


Or of all the given conditions
- param conditions the conditions to or
- return a joint and of all these conditions

#### NOT 
```java
public static Condition NOT(Condition condition) 
```


Not of  the given condition
- param condition the conditions to and
- return a joint and of all these condition

#### XOR 
```java
public static Condition XOR(Condition first, Condition second) 
```


And of all the given conditions
- param first the first condition
- param second  the second condition for xor
- return the xor of these 2 conditions


</div></div>


### SequenceConditionMode
<span style="float:right;"> [[source]](https://github.com/deeplearning4j/deeplearning4j/tree/master/datavec/datavec-api/src/main/java/org/datavec/api/transform/condition/SequenceConditionMode.java) </span>

For certain single-column conditions: how should we apply these to sequences?<br>
<b>And</b>: Condition applies to sequence only if it applies to ALL time steps<br>
<b>Or</b>: Condition applies to sequence if it applies to ANY time steps<br>
<b>NoSequencMode</b>: Condition cannot be applied to sequences at all (error condition)




### BooleanColumnCondition
<span style="float:right;"> [[source]](https://github.com/deeplearning4j/deeplearning4j/tree/master/datavec/datavec-api/src/main/java/org/datavec/api/transform/condition/column/BooleanColumnCondition.java) </span>

Created by agibsonccc on 11/26/16.

<button class="btn btn-primary" type="button" data-toggle="collapse" data-target="#BooleanColumnCondition" aria-expanded="false" aria-controls="BooleanColumnCondition">Show methods</button>
<div class="collapse" id="BooleanColumnCondition"><div class="card card-body">

#### columnCondition 
```java
public boolean columnCondition(Writable writable) 
```


Returns whether the given element
meets the condition set by this operation

- param writable the element to test
- return true if the condition is met
false otherwise

#### condition 
```java
public boolean condition(Object input) 
```


Condition on arbitrary input

- param input the input to return
the condition for
- return true if the condition is met
false otherwise


</div></div>


### CategoricalColumnCondition
<span style="float:right;"> [[source]](https://github.com/deeplearning4j/deeplearning4j/tree/master/datavec/datavec-api/src/main/java/org/datavec/api/transform/condition/column/CategoricalColumnCondition.java) </span>



<button class="btn btn-primary" type="button" data-toggle="collapse" data-target="#CategoricalColumnCondition" aria-expanded="false" aria-controls="CategoricalColumnCondition">Show methods</button>
<div class="collapse" id="CategoricalColumnCondition"><div class="card card-body">

#### columnCondition 
```java
public boolean columnCondition(Writable writable) 
```


Constructor for conditions equal or not equal.
Uses default sequence condition mode, {- link BaseColumnCondition#DEFAULT_SEQUENCE_CONDITION_MODE}

- param columnName Column to check for the condition
- param op         Operation (== or != only)
- param value      Value to use in the condition

#### condition 
```java
public boolean condition(Object input) 
```


Condition on arbitrary input

- param input the input to return
the condition for
- return true if the condition is met
false otherwise


</div></div>


### DoubleColumnCondition
<span style="float:right;"> [[source]](https://github.com/deeplearning4j/deeplearning4j/tree/master/datavec/datavec-api/src/main/java/org/datavec/api/transform/condition/column/DoubleColumnCondition.java) </span>



<button class="btn btn-primary" type="button" data-toggle="collapse" data-target="#DoubleColumnCondition" aria-expanded="false" aria-controls="DoubleColumnCondition">Show methods</button>
<div class="collapse" id="DoubleColumnCondition"><div class="card card-body">

#### columnCondition 
```java
public boolean columnCondition(Writable writable) 
```


Constructor for operations such as less than, equal to, greater than, etc.
Uses default sequence condition mode, {- link BaseColumnCondition#DEFAULT_SEQUENCE_CONDITION_MODE}

- param columnName Column to check for the condition
- param op         Operation (<, >=, !=, etc)
- param value      Value to use in the condition

#### condition 
```java
public boolean condition(Object input) 
```


Condition on arbitrary input

- param input the input to return
the condition for
- return true if the condition is met
false otherwise


</div></div>


### InfiniteColumnCondition
<span style="float:right;"> [[source]](https://github.com/deeplearning4j/deeplearning4j/tree/master/datavec/datavec-api/src/main/java/org/datavec/api/transform/condition/column/InfiniteColumnCondition.java) </span>

A column condition that simply checks whether a floating point value is infinite


<button class="btn btn-primary" type="button" data-toggle="collapse" data-target="#InfiniteColumnCondition" aria-expanded="false" aria-controls="InfiniteColumnCondition">Show methods</button>
<div class="collapse" id="InfiniteColumnCondition"><div class="card card-body">

#### columnCondition 
```java
public boolean columnCondition(Writable writable) 
```


- param columnName Column check for the condition


</div></div>


### IntegerColumnCondition
<span style="float:right;"> [[source]](https://github.com/deeplearning4j/deeplearning4j/tree/master/datavec/datavec-api/src/main/java/org/datavec/api/transform/condition/column/IntegerColumnCondition.java) </span>



<button class="btn btn-primary" type="button" data-toggle="collapse" data-target="#IntegerColumnCondition" aria-expanded="false" aria-controls="IntegerColumnCondition">Show methods</button>
<div class="collapse" id="IntegerColumnCondition"><div class="card card-body">

#### columnCondition 
```java
public boolean columnCondition(Writable writable) 
```


Constructor for operations such as less than, equal to, greater than, etc.
Uses default sequence condition mode, {- link BaseColumnCondition#DEFAULT_SEQUENCE_CONDITION_MODE}

- param columnName Column to check for the condition
- param op         Operation (<, >=, !=, etc)
- param value      Value to use in the condition

#### condition 
```java
public boolean condition(Object input) 
```


Condition on arbitrary input

- param input the input to return
the condition for
- return true if the condition is met
false otherwise


</div></div>


### InvalidValueColumnCondition
<span style="float:right;"> [[source]](https://github.com/deeplearning4j/deeplearning4j/tree/master/datavec/datavec-api/src/main/java/org/datavec/api/transform/condition/column/InvalidValueColumnCondition.java) </span>

A Condition that applies to a single column.
Whenever the specified value is invalid according to the schema, the condition applies.

For example, if a Writable contains String values in an Integer column (and these cannot be parsed to an integer), then
the condition would return true, as these values are invalid according to the schema.


<button class="btn btn-primary" type="button" data-toggle="collapse" data-target="#InvalidValueColumnCondition" aria-expanded="false" aria-controls="InvalidValueColumnCondition">Show methods</button>
<div class="collapse" id="InvalidValueColumnCondition"><div class="card card-body">

#### condition 
```java
public boolean condition(Object input) 
```


Condition on arbitrary input

- param input the input to return
the condition for
- return true if the condition is met
false otherwise


</div></div>


### LongColumnCondition
<span style="float:right;"> [[source]](https://github.com/deeplearning4j/deeplearning4j/tree/master/datavec/datavec-api/src/main/java/org/datavec/api/transform/condition/column/LongColumnCondition.java) </span>



<button class="btn btn-primary" type="button" data-toggle="collapse" data-target="#LongColumnCondition" aria-expanded="false" aria-controls="LongColumnCondition">Show methods</button>
<div class="collapse" id="LongColumnCondition"><div class="card card-body">

#### columnCondition 
```java
public boolean columnCondition(Writable writable) 
```


Constructor for operations such as less than, equal to, greater than, etc.
Uses default sequence condition mode, {- link BaseColumnCondition#DEFAULT_SEQUENCE_CONDITION_MODE}

- param columnName Column to check for the condition
- param op         Operation (<, >=, !=, etc)
- param value      Value to use in the condition

#### condition 
```java
public boolean condition(Object input) 
```


Condition on arbitrary input

- param input the input to return
the condition for
- return true if the condition is met
false otherwise


</div></div>


### NaNColumnCondition
<span style="float:right;"> [[source]](https://github.com/deeplearning4j/deeplearning4j/tree/master/datavec/datavec-api/src/main/java/org/datavec/api/transform/condition/column/NaNColumnCondition.java) </span>

A column condition that simply checks whether a floating point value is NaN


<button class="btn btn-primary" type="button" data-toggle="collapse" data-target="#NaNColumnCondition" aria-expanded="false" aria-controls="NaNColumnCondition">Show methods</button>
<div class="collapse" id="NaNColumnCondition"><div class="card card-body">

#### columnCondition 
```java
public boolean columnCondition(Writable writable) 
```


- param columnName Name of the column to check the condition for


</div></div>


### NullWritableColumnCondition
<span style="float:right;"> [[source]](https://github.com/deeplearning4j/deeplearning4j/tree/master/datavec/datavec-api/src/main/java/org/datavec/api/transform/condition/column/NullWritableColumnCondition.java) </span>

Condition that applies to the values in any column. Specifically, condition is true
if the Writable value is a NullWritable, and false for any other value


<button class="btn btn-primary" type="button" data-toggle="collapse" data-target="#NullWritableColumnCondition" aria-expanded="false" aria-controls="NullWritableColumnCondition">Show methods</button>
<div class="collapse" id="NullWritableColumnCondition"><div class="card card-body">

#### condition 
```java
public boolean condition(Object input) 
```


Condition on arbitrary input

- param input the input to return
the condition for
- return true if the condition is met
false otherwise


</div></div>


### StringColumnCondition
<span style="float:right;"> [[source]](https://github.com/deeplearning4j/deeplearning4j/tree/master/datavec/datavec-api/src/main/java/org/datavec/api/transform/condition/column/StringColumnCondition.java) </span>



<button class="btn btn-primary" type="button" data-toggle="collapse" data-target="#StringColumnCondition" aria-expanded="false" aria-controls="StringColumnCondition">Show methods</button>
<div class="collapse" id="StringColumnCondition"><div class="card card-body">

#### columnCondition 
```java
public boolean columnCondition(Writable writable) 
```


Constructor for conditions equal or not equal
Uses default sequence condition mode, {- link BaseColumnCondition#DEFAULT_SEQUENCE_CONDITION_MODE}

- param columnName Column to check for the condition
- param op         Operation (== or != only)
- param value      Value to use in the condition

#### condition 
```java
public boolean condition(Object input) 
```


Condition on arbitrary input

- param input the input to return
the condition for
- return true if the condition is met
false otherwise


</div></div>


### TimeColumnCondition
<span style="float:right;"> [[source]](https://github.com/deeplearning4j/deeplearning4j/tree/master/datavec/datavec-api/src/main/java/org/datavec/api/transform/condition/column/TimeColumnCondition.java) </span>

Condition that applies to the values


<button class="btn btn-primary" type="button" data-toggle="collapse" data-target="#TimeColumnCondition" aria-expanded="false" aria-controls="TimeColumnCondition">Show methods</button>
<div class="collapse" id="TimeColumnCondition"><div class="card card-body">

#### columnCondition 
```java
public boolean columnCondition(Writable writable) 
```


Constructor for operations such as less than, equal to, greater than, etc.
Uses default sequence condition mode, {- link BaseColumnCondition#DEFAULT_SEQUENCE_CONDITION_MODE}

- param columnName Column to check for the condition
- param op         Operation (<, >=, !=, etc)
- param value      Time value (in epoch millisecond format) to use in the condition

#### condition 
```java
public boolean condition(Object input) 
```


Condition on arbitrary input

- param input the input to return
the condition for
- return true if the condition is met
false otherwise


</div></div>


### TrivialColumnCondition
<span style="float:right;"> [[source]](https://github.com/deeplearning4j/deeplearning4j/tree/master/datavec/datavec-api/src/main/java/org/datavec/api/transform/condition/column/TrivialColumnCondition.java) </span>

Created by huitseeker on 5/17/17.



### SequenceLengthCondition
<span style="float:right;"> [[source]](https://github.com/deeplearning4j/deeplearning4j/tree/master/datavec/datavec-api/src/main/java/org/datavec/api/transform/condition/sequence/SequenceLengthCondition.java) </span>

A condition on sequence lengths




### StringRegexColumnCondition
<span style="float:right;"> [[source]](https://github.com/deeplearning4j/deeplearning4j/tree/master/datavec/datavec-api/src/main/java/org/datavec/api/transform/condition/string/StringRegexColumnCondition.java) </span>

Condition that applies to the values in a String column, using a provided regex.
Condition return true if the String matches the regex, or false otherwise<br>

<b>Note:</b> Uses Writable.toString(), hence can potentially be applied to non-String columns


<button class="btn btn-primary" type="button" data-toggle="collapse" data-target="#StringRegexColumnCondition" aria-expanded="false" aria-controls="StringRegexColumnCondition">Show methods</button>
<div class="collapse" id="StringRegexColumnCondition"><div class="card card-body">

#### condition 
```java
public boolean condition(Object input) 
```


Condition on arbitrary input

- param input the input to return
the condition for
- return true if the condition is met
false otherwise


</div></div>