Subroutines
===========

In Perl, user-defined functions are called subroutines. They may be located in any Perl code block.

The Perl model for function call and return values is simple: all functions are passed as parameters one single flat list of scalars, and all functions likewise return to their caller one single flat list of scalars.

All parameters passed to a subroutine show up in the special array `@_`. The first parameter can be accessed with `$_[0]`, the second with `$_[1]`, and so on.

`return` statements are used to exit subroutines. They may optionally specify a return value.

Subroutines are declared using the keyword `sub`. Subroutines may be called using an explicit `&` prefix.

```perl
sub hello {
    return 'Hello';
}
$a = &hello();
# $a = 'Hello'
```

```perl
sub max {
    my ($max) = shift(@_);
    foreach $temp (@_) {
        $max = $temp if $max < $temp;
    }
    return $max;
}
$b = max(6, 3, 4, 5, 1, 2, 8);
# $b = 8
```

## LON-CAPA Subroutines

LON-CAPA includes some useful custom Perl subroutines that can be called in any problem. These are not part of the Perl standard library so they work only within LON-CAPA.

### Math Operations

#### Trigonometric: `&sin(<x>), &cos(<x>), &tan(<x>)`

Trigonometric functions where `<x>` is a value in radians.

#### Inverse Trigonometric: `&asin(<x>), &acos(<x>), &atan(<x>), &atan2(<sign>,<x>)`

Inverse trigonometric functions where the return value is in radians.

The input for `&asin` and `&acos` must be between $$-1$$ and $$1$$.

`&atan2` returns a value between $$-\pi$$ and $$\pi$$, the sign of which is determined by `<sign>`.

#### Logarithmic: `&log(<x>), &log10(<x>)`

Natural $$(\ln x)$$ and base-10 $$(\log x)$$ logarithms.

#### Exponential: `&exp(<x>), &pow(<x>,<y>), &sqrt(<x>)`

Exponential $$(e^{x})$$, power $$(x^y)$$, and square root $$(\sqrt{x})$$ functions.

### Number-related

#### Random number (range): `&random(<low>, <high>, <step>)`

Returns a uniformly distributed random number between the `<low>` and `<high>` bounds, in steps of size `<step>`. `<step>` is optional. If omitted, a step of 1 is used.

```perl
$a = &random(-3, 3);
$b = &random(0, 2, 0.5);
# Possible values:
# $a: -3, -2, -1, 0, 1, 2, 3
# $b: 0, 0.5, 1, 1.5, 2
```

#### Round: `&roundto(<num>, <decimal points>)`

Rounds a real number to a given number of decimal points.

```perl
$a = 3.1415926;
$b = &roundto($a, 2); # 3.14
$c = &roundto($a, 5); # 3.14159
```

#### Minimum and maximum: `&min(<@array>|<list>)` `&max(<@array>|<list>)`

Returns the minimum or maximum value in an array or list of scalar variables.

```perl
@ages = (70, 21, 18, 5, 35, 62);
# List, $min = 5
$min = &min(70, 21, 18, 5, 35, 62);
# Array, $max = 70
$max = &max(@ages);
```
