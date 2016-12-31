Variables
=========

There are three types of variables in Perl: scalars, arrays, and hashes.

### Scalars

Scalar variables are a basic variable type in Perl. They represent simple values, such as integers, floats, characters, and strings. Scalar variables are preceded by the `$` symbol.

```perl
# Integer
$a = 1;
# Float
$b = 1.5;
# String
$c = 'Hello';
```

#### Strings

In Perl, either single quotation marks (`''`) or double quotation marks (`""`) may be used to represent strings.

Some special characters must be delimited in strings.


### Arrays

Arrays contain an ordered list of scalar variables. They are preceded by the `@` symbol.

```perl
@fruits = ("apple", "orange", "kiwi");
@fibonacci = (1, 1, 2, 3, 5, 8, 13);
@empty = (); # empty array
```

To access a single element of an array, prefix the name of the array with `$` and then append the zero-indexed location of the element in square brackets.

```perl
@sports = ("basketball", "soccer", "badminton", "rugby");
$a = $sport[2]; # $a holds "badminton"
```

To access the size of an array, one can use `scalar(@array)`.

```perl
@daysOfWeek = ("M", "T", "W", "R", "F", "S", "U");
$length1 = scalar(@daysOfWeek); # $length1 holds 7

@empty = ();
$length2 = scalar(@empty); # $length2 holds 0
```

### Hashes

Hashes in Perl are a hash-table data structure. In Python they are called "dictionaries" and in Java they are called "maps".

A hash represents an unordered set of key-value pairs. The keys and values can be any scalar variable. Hashes are preceded by the `%` symbol.

They are multiple ways of creating hashes:

```perl
# 1. Use a comma-separated list
%population = ('China', 1367, 'India', 1251, 'United States', 321);
# 2. Use a list with arrows, more semantically clear
%population = ('China' => 1367, 'India' => 1251, 'United States' => 321);
# 3. Declare each key-value pair individually
$population{'China'} = 1367;
$population{'India'} = 1251;
$population{'United States'} = 321;
```

To access a single element from a hash, prefix the name of the hash with `$` and then append the element key within curly brackets.

```perl
%ages = ('Steve Jobs' => 56);
$a = $age{'Steve Jobs'}; # $a holds 56
```
