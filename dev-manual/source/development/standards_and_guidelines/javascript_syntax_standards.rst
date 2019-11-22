.. _javascript_syntax_standards:

Javascript Syntax Standards
===========================
Indenting
---------
* All code MUST indent using two (2) space characters,

Semi-colons
-----------
* All statements (except for, function, if, switch, try, while) must be followed by a semi-colon (;).

Camel Casing
------------
* Functions should be lowerCamelCased.
* The first letter of each variable or function should be lowercase, and the first letter of subsequent words should be capitalized.

Functions
---------
* Function names SHOULD begin with the name of the module or theme declaring the function, so as to avoid name collisions.

Function Declarations
---------------------
* The function keyword MUST be followed by one space.
* Every function SHOULD attempt to return a meaningful value.

Function Calls
--------------
* Functions SHOULD be called with no spaces between the function name, the opening parenthesis, and the first parameter.

Constructors
------------
* Constructor functions MUST be given names with an initial uppercase character.
* A function with an initial uppercase name MUST NOT be called without a new operator.

String Concatenation
--------------------
* Expressions SHOULD be separated with one space before and after the + operator to improve readability.
* The concatenating assignment operator (+=) SHOULD be separated with one space on each side as with the assignment operator:

Control Structures
------------------
* Control statements MUST have one space between the control keyword and opening parenthesis, to distinguish them from function calls.
* Control structures MUST always use curly braces, even in situations where they are optional.

Operators
---------
* Comparisons: Strict equality MUST be used in comparisons (=== or !==).

Variables
---------
* All variables must be declared with var before they are used and should be declared only once.
* All variables should be declared at the beginning of a function.
* Each variable assignment SHOULD be declared on a separate line.
* Pre-defined constants SHOULD be all-uppercase and words separated by underscores
