Functions
=========

Perl has many built-in functions for manipulating various variables.

## String Operations/Functions

Strings are commonly used scalar variables in Perl. They are important because many forms of data are stored as strings.

#### Length: `length(<string>)` $$\Rightarrow$$ `<length>`

`length()` returns the length of a string.

```perl
$a = length('lon-capa');
# $a = 8
```

#### Case conversions: `uc(<string>)` and `lc(<string>)`

`uc()` converts a string to all uppercase and `lc()` converts a string to all lowercase.

```perl
$str = 'Hello World';
$upper = uc($str); # 'HELLO WORLD'
$lower = lc($str); # 'hello world'
```

#### Concatenation: `<string1>.<string2>` $$\Rightarrow$$ `<string>`

Concatenation is the act of appending one string to the end of another. The string concatenation operator in Perl is `.` (dot).

```perl
$a = 4;
$b = 4;
$c = 1;
$equation = $a.'*x^2 + '.$b.'*x + '.$c;
# $equation = '4*x^2 + 4*x + 1'
```

Alternatively, you can use variables name directly within quotation marks to concatenate them.

```perl
$firstName = 'Johnny';
$lastName = 'Appleseed';
$name = '$firstName $lastName';
```

#### Repetition: `<string>x<integer>` $$\Rightarrow$$ `<string>`

Repetition is the act of repeating a string multiple times. The string repetition operator in Perl is `x`: it repeats the `<string>` on its left side as many times as the `<integer>` on its right side.

```perl
$clock = 'tick tock 'x3;
# $clock = 'tick tock tick tock tick tock '
```

#### Substring: `substr(<string>, <offset>, <length>)` $$\Rightarrow$$ `<string>`

`substr()` extracts a substring from a string. It takes a string as input, along with a 0-based location called `offset` and the `length` of the substring.

```perl
$a = 'I came, I saw, I conquered';
$b = substr($a, 2, 4); # start at index 2, copy 4 characters
# $b = 'came'
```

If the `length` parameter is omitted, `substr()` will return all characters starting from `offset` until the end of the string.

```perl
$a = 'I came, I saw, I conquered';
$c = substr($a, 8); # start at index 7, copy all until end
# $c = 'I saw, I conquered'
```

If the `offset` is negative, `substr()` will start counting from the end of the string instead of the beginning.

```perl
$a = 'I came, I saw, I conquered';
$d = substr($a, -9); # start at 9 characters from the right, copy all until end
$e = substr($a, -9, 7); # start at 9 characters from the right, copy 7
# $d = 'conquered'
# $e = 'conquer'
```

#### Split: `split(<delimiter>, <string>)` $$\Rightarrow$$ `<array>`

`split()` splits a string into an array of strings based on a delimiter. This function is especially useful for parsing mathematical expressions that contain some delimiter, such as commas.

```perl
$submission = '-1,0,2';
@roots = split(',', $submission);
# @roots = (-1, 0, 2)
# Array elements can now be accessed with $roots[0], etc
```

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
@possibleAns = ('1/2', '0.5', '.5');
$ans = '0.5';
# Check if @possibleAns contains $ans
if (index(@possibleAns, $ans) != -1) {
    $output = 'Correct answer.'
} else {
    $output = 'Incorrect answer.'
}
```

#### Push and Unshift: `push|unshift(@array, (<scalar>|@array))` $$\Rightarrow$$ `<size>`

`push` adds a scalar variable or an array of scalar variables to the end of an array. `unshift` is similar to `push` but instead prepends the variable(s) to the front of an array.

Both functions return the size of the array after the variable(s) have been added.

```perl
@a = ();
@b = ('chicago', 'new york city');
push(@a, 1); # returns 1
push(@a, 2); # returns 2
unshift(@a, ('a', 'b', 'c')); # returns 5
push(@a, @b); # returns 7
# @a = ('a', 'b', 'c', 1, 2, 'chicago', 'new york city')
```

#### Pop and Shift: `pop|shift(@array)` $$\Rightarrow$$ `<scalar>`

`pop` removes the element at the end of an array and returns it. `shift` removes the element at the front of an array and returns it.

```perl
@c = ('a', 'man', 'a', 'plan', 'a', 'canal', 'panama');
pop(@c); # returns 'panama'
$str1 = pop(@c); # $str1 = 'canal'
shift(@c); # returns 'a'
$str2 = shift(@c); #str2 = 'man'
```
