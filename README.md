##### Main tools used:

Pylint - linter, static code analyzer with extra 'symilar' command - similarities checker
[Radon](https://pypi.org/project/radon/) - Radon is a Python tool that computes various metrics from the source code.

## Code:
```python
def wtf(word):
    try:
        if (length(word) == 1 and length(word) != 0) or (length(word) > 1 and length(word) != 0) or (length(word) == 0 and length(word) != -1):
            if(length(word) != -1):
                if(length(word) not in [0]):
                    print("OK")
    except:
        if(word):
            print("Coś nie tak ze słowem")
        else:
            print("Nie ma słowa")
```

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

```
$ radon cc -s wtf.py
wtf.py
    F 1:0 wtf - C (11)
```

## Maintainability Index score (defined [here](https://radon.readthedocs.io/en/latest/intro.html#maintainability-index)):

| MI score | Rank | Maintainability |
|---------|-------|-----------------|
|100 - 20 |	  A   | Very high       |
|19 - 10  |	  B   |	Medium          |
|9 - 0    |	  C   |	Extremely low   |

```
$ radon mi -s wtf.py 
wtf.py - A (59.70)
```
