Loops
=====

Many programs require repeated execution of code, sometimes for a variable number of times. Rather than writing the same code multiple times, it is better to use a loop.

## `for` loop

A `for` loop follows the following syntax:

```perl
for (<initialization>; <termination>; <increment>) {
    # statements to loop
}
```

The `<initialization>` expression initializes the loop and is executed once when the loop begins. After each iteration of the loop, the `<increment>` expression is executed and then the `<termination>` condition is checked. When the `<termination>` condition is `false`, the loop terminates.

If the `<termination>` condition evaluates to `false` when the loop begins, the contents of a `for` loop will not be run.

```perl
$factorial = 1;
# The loop below runs 4 times
for ($i = 5; $i > 1; $i--) {
    $factorial *= $i;
}
# $factorial holds 5 * 4 * 3 * 2 = 5! = 120
```

`for` loops are suited for iterating through arrays:

```perl
@roots = (-1, 3, 2);
$product = 1;

for ($i = 0; $i < $scalar roots; $i++) {
    $product *= $roots[$i];
}
# $product holds -1 * 3 * 2 = -6
```

The three expressions of the `for` loop are optional. Thus, an infinite loop can be created with `for(;;)`.

## `while` loop

A `while` loop follows the following syntax:

```perl
while (<condition>) {
    # statements to loop
}
```

The condition is checked every time the loop begins. If the condition is `false`, the loop terminates. Otherwise, the loop is executed once and the condition is checked again.

Like a `for` loop, if the condition evaluates to `false` when the loop begins, the contents of a `while` loop will not be run.

## `do while` loop

A `do while` loop is very similar to a `while` loop. It follows the following syntax:

```perl
do {
    # statements to loop
} while (<condition>);
```

Unlike `while` loops, the condition is checked after the loop is run. Thus, a `do while` loop always executes at least once. One should use a `do while` loop for writing code that runs at least once.

Below is an example of a `do while` loop that is frequently used in math problems:

```perl
# Generate a random integer between -5 and 5, excluding 0
do { $a = &rand(-5, 5, 1) } while ($a == 0);
```

## `break` and `continue`

The `break` statement causes a loop to terminate.

```perl
for ($i = 0; $i < 10; $i++) {
    if ($i == 5) {
        break; # exit loop
    }
}
# $i has value 5 after loop
```

The `continue` statement causes a loop to skip the current iteration and begin a new iteration.

```perl
$a = 0;
for ($i = 1; $i < 7; $i++) {
    # If $i is odd, continue
    if ($i % 2 == 1) {
        continue;
    }
    # Else add $i to $a
    $a += $i;
}
# $a = 2 + 4 + 6 = 12
```
