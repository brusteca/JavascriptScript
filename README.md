# JavascriptScript

## A string oriented language for the 22nd century

***

Everything is a string, space (any unicode whitespace) is a separator.
Comparisons are always with strings. 
10 < 5 because 1 < 5.
Objects are strings, and functions too.

Everything is global.

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
>> C
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



