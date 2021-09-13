# JavascriptScript

## A string oriented language for the 22nd century


Everything is a string, space (any unicode whitespace) is a separator.
Comparisons are always with strings.
10 < 5 because 1 < 5.
Objects are strings, and functions too.

Everything is global and case insensitive.

## Operators

Because every value is a string, there's no diference betweent names and values.
Therefore, assignment ```=``` can be done on anything. Every name starts by default
with the value of its own name. Also, whenever you access a name the value that is its
own name is returned

```
A
>> A
A = 1
A
>> A
```

To access the value a name has assigned you can use the ```*``` operator:

```
A = 1
B = A
B*
>> A
B**
>> 1
```

In order to access the final value of the name -> value chain you can use the ``` ' ```
operator. Any unicode single quote will work. Be careful with circular definitions
though.

```
A = 1
A
>> A
A'
>> 1
1'
>> 1

B = A
B
>> B
B'
>> 1
1 = 2
1'
>> 2
B'
>> 2
```

The ``` == ``` operator assigns to the last item of the chain, and is syntactic
sugar for ``` '= ```

```
A = 1
B = A
B == C
B
>> A
1
>> C
```

The ``` === ``` operator compares names. It can output either ``` true ``` or
``` fals ```. Obviously these are name as well.

```
A === A
>> true
B = A
A === B
>> fals
```

The ``` ==== ``` operator compares immediate values. It's syntactic sugar for
``` x* === y* ```.

```
A ==== A
>> true
B = A
A ==== B
>> true
```

The ``` ===== ``` operator compares final values. It's syntactic sugar for
``` x' === y' ```.

```
A ===== A
>> true
B = A
C = B
A ===== C
>> true
```

The ``` + ``` operator concatenates.

```
1 + 2
>> 12
```

The ``` ++ ``` operator concatenates immediate values.

```
1 = A
2 = B
1 ++ 2
>> AB
```

The ``` +++ ``` operator concatenates final values.

```
1 = A
2 = B
X = 2
1 ++ X
>> A2
1 +++ X
>> AB
```

The ternary operator ``` ? : ``` does contitionals:

```
A === A ? its true! : its fals!
>> its true!
```


In JavascriptScript we don't believe in math, instead, computations are done by splitting or appending strings. You won't need anything else, trust me.


## Objects

Objects are also strings. An object is a string that contains spaces (it can contain
zero spaces, and therefore every string is also an object). They're represented like
``` name1 name2 name3 ...```

To access the members of an object you use the ``` . ``` operator:

```
A = 1 2
A.1
>> A.1
A.1'
>> A.1
A.1 = B
A.1'
>> B
```

The members of an object are all new names. ``` . ``` is a  reserved character and
when using it inside a string, it implicitly concatenates a space and the new name to
the value the name referenced before. For example:

```
A = 1
A*
>> 1
A.B = X
A*
>> 1 B
A.B*
>> X

A.C = Y
A*
>> 1 B C
```

The only thing the ``` . ``` operator does is parsing spaces, since what's actually
happening is that you are using a lot of new names of the form ``` obj.member ```


## Functions

Functions are defined with ```var1 var2 ... varN >= {instructions} ```. Thanks to
the magic of _everything is a string_, functions are anonymous by default, which
fosters a functional style. The parameters of a function are inside the ```this```
object.

In order to call a function, you just have to put it there

```
A = 1
B = 2
A B >= {return this.A* ++ this.B*}
>> 12
```

If you want to name a function, it's simple. Since everything is a string:

```
func = A B >= {return this.A* ++ this.B*}
```

And then to use it

```
func.A = 1
func.B = 2
func’
>> 12
```

It's clear then that a function is an object whose attributes are its parameters
and the ``` > ``` has the instructions of the function. The attributes of a function
are accessed inside its code with the name ``` this ```. The curly braces indicate
that a string can be read as instructions.

## Reserved words

_Reserved_ is more of a suggestion. It means that that name is in use when the program
starts. Obviously the programmer has the freedom to redefine everything.

### namespace

namespace is an object that contains all the strings of the program that have been
used (i.e. names that have had a value assigned that isn't itself). It includes
itself, of course.

```
namespace
>> namespace
namespace*
>> namespace print .... (all the other reserved words)
A = 1
namespace
>> namespace print .... (reserved words) ... A
namespace.A*
>> 1
namespace.namespace.A*
>> 1
```


## Other proposed names

phpscript

stringscript

bashscript

JavaScriptscript (note the capitalization)

JavaScript♭

MethScript

Garbash

JavaScript--
