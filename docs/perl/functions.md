Functions
=========

Perl has many built-in functions for manipulating various variables.

## String Operations/Functions

Strings are commonly used scalar variables in Perl. They are important because many forms of data are stored as strings.

#### Concatenation: `<string1>.<string2>` $$\Rightarrow$$ `<string>`

Concatenation is the act of appending one string to the end of another. The string concatenation operator in Perl is `.` (dot).

```perl
$a = 4;
$b = 4;
$c = 1;
$equation = $a."*x^2 + ".$b."*x + ".$c;
# $equation = "4*x^2 + 4*x + 1"
```

Alternatively, you can use variables name directly within quotation marks to concatenate them.

```perl
$firstName = "Johnny";
$lastName = "Appleseed";
$name = "$firstName $lastName";
```

#### Repetition: `<string>x<integer>` $$\Rightarrow$$ `<string>`

Repetition is the act of repeating a string multiple times. The string repetition operator in Perl is `x`: it repeats the `<string>` on its left side as many times as the `<integer>` on its right side.

```perl
$clock = "tick tock "x3;
# $clock = "tick tock tick tock tick tock "
```

#### Substring: `substr(<string>)` $$\Rightarrow$$ `<string>`

*in progress*

#### Split: `split(<string>, <delimiter>)` $$\Rightarrow$$ `<array>`

*in progress*

## Number functions

#### Random number: `rand(<number>)`

`rand(<number>)` returns a random real number between $$0$$ and `<number>`.

*Note: LON-CAPA provides a more powerful random number subroutine called `&rand`s. Read about it in the [Subroutine section](/docs/perl/subroutines.md).*

```perl
$a = rand(0, 5);
```

## Array functions

#### Index: `index(@array, <scalar>)` $$\Rightarrow$$ `<index>`

`index` searches an array for a scalar variable. If the scalar variable exists in the array, its index in the array is returned. Otherwise, `-1` is returned.

```perl
@possibleAns = ("1/2", "0.5", ".5");
$ans = "0.5";
# Check if @possibleAns contains $ans
if (index(@possibleAns, $ans) != -1) {
    $output = "Correct answer."
} else {
    $output = "Incorrect answer."
}
```

#### Push: `push(@array, (<scalar>|@array))` $$\Rightarrow$$ `<size>`

`push` adds a scalar variable or an array of scalar variables to the end of an array. It returns the size of the array after the variable(s) have been added.

```perl
@a = ();
@b = ('chicago', 'new york city');
push(@a, 1); # returns 1
push(@a, 2); # returns 2
push(@a, ('a', 'b', 'c')); # returns 5
push(@a, @b); # returns 7
# @a = (1, 2, 'a', 'b', 'c', 'chicago', 'new york city')
```

#### Pop: `pop(@array)` $$\Rightarrow$$ `<scalar>`

`pop` removes the element last added to an array and returns it.

```perl
@c = ('a', 'man', 'a', 'plan', 'a', 'canal', 'panama');
pop(@c); # returns 'panama'
$string = pop(@c); # $string = 'canal'
```
