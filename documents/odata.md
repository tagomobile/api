Supported OData Query Options
===============================


`$top` The maximum number of items returned in the result set for each page.

`$skip` The number of rows to skip in the result set before beginning to return results.

`$filter`

Comparisons
Eq – Equal to 
Gt – Greater than 
Lt – Less than 
Ne – Not equal to 

Concatinations
And
Or

Field Names - Types: all OData supported types.

`$orderby`

Specifies the sort order of the result set. 
NOTE: Requires DataServiceVersion 2.0 or higher. To determine DataServiceVersion see Determine DataServiceVersion later in this topic.

`$select`

Specifies the fields returned in the result set.

`$skiptoken`

An opaque value that must be passed back to the server in order to continue getting results for the query. For more information see Skip Token System Query Option ($skiptoken) at OData.org.

`$count`

Returns the count of a collection of entities. 
NOTE: Requires DataServiceVersion 2.0 or higher. To determine DataServiceVersion see Determine DataServiceVersion in this topic.

`$inlinecount`

$inlinecount is only supported for flexible query services. It is not supported for fixed query services. 
NOTE: Requires DataServiceVersion 2.0 or higher. To determine DataServiceVersion see Determine DataServiceVersion later in this topic.

`$metadata`

Retrieves a list of fields, their data types, mode, and other related information in a dataset.

`ID operators`

E.g. "/Companies('Microsoft')"

`Comparison operators`

eq – Equal to 
ne – Not equal to 
lt – Less than 
le – Less than or equal to 
gt – Greater than 
ge – Greater than or equal to

`Logical operators`

and – True only if both operands are true
or – True if either or both operands are true
not – opposite of operand

`Arithimetic operators`

add – Addition operator
sub – Subtraction operator
mult – Multiplication operator
div – Division operator
mod – Modulo (remainder after integer division) operator

`Grouping operators`

( and )

`DateTime Functions`

year 
month 
day 
hour 
minute 
second

`Math functions`

round 
ceiling 
floor