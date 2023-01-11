## Supercharge your JSON strings using simple yet powerful dynamic expressions

## Table of Contents

- [The Syntax](#the-syntax)
- [Case Matchers](#case-matchers)

## The Syntax

### Parameter

A parameter may be introduced through the use of `{}`, which mark a parameter
template. A parameter template can contain either a named parameter (through the
use of its name) or a positional one (through the use of its index).

#### Examples

`Your name is {name} and your age is {age}.`

`The three chosen members are {0}, {1} and {2}.`

#### Expression

An expression works a little like a switch statement. A parameter is passed into
an expression and checked against the defined cases. If the parameter matches a
case, its result is returned.

Expressions may be nested, and there is virtually no limit to how many cases an
expression can contain. However, for readability's sake, it is best to keep
expressions small and understandable.

`[{parameter} ~ case1:result1/case2:result2/(...)]`

`[]` introduce an expression

`~` separates the parameter from the cases

`:` separates the result of a case from the case itself

`/` separates cases and their results

#### Examples

`[{age} ~ Lesser(18):You are underage!/Default:You are free to drink.]`

`[{temperature} ~ Lesser(15):Too cold./Lesser(30):Temperate./Default:It's too hot!]`

### Case Matchers

The parser supports several case matchers, which can be used to match the
control variable to an argument.

String-exclusive matchers:

- `StartsWith`
- `EndsWith`
- `Contains`

Indifferent matchers:

- `Equals` *
- `IsIn`
- `IsNotIn`
- `IsInRange`
- `IsNotInRange`

Number-exclusive matchers:

- `IsGreater`
- `IsGreaterOrEqual`
- `IsLesser`
- `IsLesserOrEqual`

Other:

- `Always`

* If no matcher has been defined, the matcher will default to 'Equals'
