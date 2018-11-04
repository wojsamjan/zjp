# Code metrics in Python

Cool [blogpost](https://www.fullstackpython.com/code-metrics.html) about code metric tools for Python

[The Little Book of Python Anti-Patterns](https://docs.quantifiedcode.com/python-anti-patterns/) - exactly what it says on the tin, another good read [here](https://github.com/maxlinksuper/clean-code-python)

##### Main tools used:

Pylint - linter, static code analyzer with extra 'symilar' command - similarities checker

[Radon](https://radon.readthedocs.io/en/latest/index.html) - tool for obtaining raw metrics on line counts, Cyclomatic Complexity, Halstead metrics and maintainability metrics.

## Our patient:


## Command used to keep things DRY:



## Cyclomatic Complexity:
F stands for function (could also be M or C for method or class) and -s option shows value of complexity, complexity is ranked on a scale from A to F


| CC score | Rank | Risk |
|---------|-------|-----------------|
|1 -5 |	  A   | low - simple block       |
|6 - 10  |	  B   |	 	low - well structured and stable block          |
|11 - 20   |	  C   |	 	moderate - slightly complex block   |
| 21 - 30 | D | more than moderate - more complex block |
| 31 - 40 | E | high - complex block, alarming |
|41+ | F |  	very high - error-prone, unstable block |

Construct |	Effect on CC |	Reasoning
---------|--------------|----------------
if |	+1 	|An if statement is a single decision.
elif |	+1 	|The elif statement adds another decision.
else |	+0 	|The else statement does not cause a new decision. The decision is at the if.
for |	+1 |	There is a decision at the start of the loop.
while |	+1 | 	There is a decision at the while statement.
except |	+1 	| Each except branch adds a new conditional path of execution.
finally |	+0 |	The finally block is unconditionally executed.
with 	| +1 |	The with statement roughly corresponds to a try/except block (see PEP 343 for details).
assert |	+1 |	The assert statement internally roughly equals a conditional statement.
Comprehension |	+1 |	A list/set/dict comprehension of generator expression is equivalent to a for loop.
Boolean Operator |	+1 |	Every boolean operator (and, or) adds a decision point.



## Maintainability Index score (defined [here](https://radon.readthedocs.io/en/latest/intro.html#maintainability-index)):

| MI score | Rank | Maintainability |
|---------|-------|-----------------|
|100 - 20 |	  A   | Very high       |
|19 - 10  |	  B   |	Medium          |
|9 - 0    |	  C   |	Extremely low   |



## Raw metrics:
These include:  
+ LOC: the total number of lines of code
+ LLOC: the number of logical lines of code
+ SLOC: the number of source lines of code - not necessarily corresponding to the LLOC
+ comments: the number of Python comment lines (i.e. only single-line comments #)
+ multi: the number of lines representing multi-line strings
+ blank: the number of blank lines (or whitespace-only ones)

[More](https://en.wikipedia.org/wiki/Source_lines_of_code) info about what LLOC/SLOC are.



## Halstead complexity metrics:
[Wiki](https://en.wikipedia.org/wiki/Halstead_complexity_measures) article.
Quick summary:
+ h1 - the number of distinct operators
+ h2 - the number of distinct operands
+ N1 - the total number of operators
+ N2 - the total number of operands
+ vocabulary - h1 + h2
+ length - N1+N2

Check [documentation](https://radon.readthedocs.io/en/latest/intro.html#halstead-metrics) for other definitions.
