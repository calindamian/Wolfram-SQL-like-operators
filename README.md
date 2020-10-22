# Wolfram-SQL-like-operators-
Wolfram SQL like operators 

## Objective

New  to Wolfram language I'm very  impressed by its expressive power .
However coming from a database background I found sometimes counterintuitive to manipulate data using Datasets.
In my journey of learning Wolfram language  I'm trying to  implement SQL like operators in order to explore data structures 
with the simplicity of SQL Language .

A small query example using stocks data imported from FinancialData package:
sampledataSQL is a 2 dimensional list with 3 columns { symbol, time , close}

```
 whereSQL[sampledataSQL , (! MissingQ[close]) ]  //
 groupBySQL[# , {time} ]&//
 summarySQL [# ,  Association["maxclose" :> (close//Max) ,
						"minclose" :> (close//Min) ,
						"count" :> (table//Length) ]
		]&//
   orderBySQL[#, {maxclose}]&//
   showTableSQL
```

## Demo
https://www.wolframcloud.com/obj/damcalrom/Published/SQL_Operators.nb
