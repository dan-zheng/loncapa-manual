Conditions
==================

Like many other languages, Perl offers control statements which control the flow of execution in a program using conditions. Conditions are statements that, when evaluated, yield `true` or `false`.

(Technically, Perl does not contain boolean variables `true` and `false`. Instead, conditions yield *truthy* and *falsey* values. *Falsey* values include `0` and the empty string `''`. *Truthy* values include non-zero numbers and non-empty strings.)

### Conditional Operators

Conditions involve conditional operators:

| Operator | Meaning | Example |
|----------|---------|---------|
| `<`, `<=` | less than, less than or equal to | `1 < 2`, `true` |
| `>`, `>=` | greater than, greater than or equal to | `4 > 5`, `false` |
| `==` | number equality | `3 == 3.00`, `true` |
| `!=` | number inequality | `3.14 != 3.14159`, `true` |
| `eq` | string equality | `"Hello" eq "Aloha"`, `false` |
| `ne` | string inequality | `"green eggs" ne "ham"`, `true` |

Notice that there are different operators for comparing numbers and comparing strings. They are subtly different: `"3" == "3.00"` returns `true` because the two are numerically equivalent but `"3" eq "3.00"` returns `false` because they are not equal as strings.

### `if`, `elsif`, `else`

`if` statements are used to execute code based on whether a condition is true. The syntax is `if (<condition>) { # code to execute }`. They can be used in conjunction with an `else` statement to execute code if the same condition is false.

```perl
$a = 5;
if ($a < 5) {
    $b = "$a is less than 5."
} else {
    $b = "$a is greater than or equal to 5."
}
```

To negate a condition, one can use the boolean operator `!`:

```perl
$string = "Hello world";
if (!($string eq "Hello World")) {
    # If $string is not equal to "Hello World"
}
# equivalent to: if ($string ne "Hello World")
```

`elsif` statements are used with `if` statements to check multiple conditions. Conditions are always checked sequentially, starting with the first `if` statement and proceeding downwards.

```perl
if ($a < 0) {
    $b = "$a is negative."
} elsif ($a < 20) {
    $b = "$a is greater than or equal to 0 and less than 20."
} else {
    $b = "$a is greater than or equal to 20."
}
```

To check if multiple conditions are true in a single `if` statement, one can join conditions using the boolean operators `&&` and `||`.

`<cond 1> && <cond 2>` returns true only if both conditions 1 and 2 are true. `<cond 1> || <cond 2>` returns true if condition 1 is true, condition 2 is true, or both are true.

It is possible to group conditions together using parentheses to change the order in which the conditions are evaluated. Note that the grouping of conditions is significant as boolean operators are not necessarily associative.

```perl
if ((<cond1> && <cond2>) || <cond3>) { # true if either 1 and 2 are true or 3 is true }
if (<cond1> && (<cond2> || <cond3>) { # true if 1 and either 2 or 3 is true }
```

### `switch`

`switch` statements can be used when comparing a variable with many different values. It is possible to do such comparisons using many `elsif` statements:

```perl
if ($color eq "red") {
    # case red
} elsif ($color eq "green") {
    # case green
} elsif ($color eq "blue") {
    # case blue
} else {
    # case other
}
```

However, `switch` statements offer a cleaner, more semantically clear alternative:

```perl
switch ($color) {
    case ("red") {
        # case red
    }
    case ("green") {
        # case green
    }
    case ("blue") {
        # case blue
    }
    else {
        # case other
    }
}
```

Some `cases` for `switch` statements have different meanings:

```perl
switch ($variable) {
    case (42) {
        # $variable == 42
    }
    case ("foobar") {
        # $variable eq "foobar"
    }
    case (@array) {
        # @array contains $variable
    }
    case (%hash) {
        # %hash contains $variable entry
    }
    else {
        # no case applies
    }
}
```
