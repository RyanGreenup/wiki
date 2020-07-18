---
title: Introduction to Python
description: The basics of python as adapted from week 2 of Applications of Big Data
published: true
date: 2020-07-18T04:51:35.562Z
tags: public, python
editor: markdown
---

# Basics of Python Programming

| ⚠️ WARNING                                       |
| ----------------------------------------------- |
| Much of the lecture slides deal with *Python 2* |

## Take input

the `input` command will read from STDIN:

```py

def main():
    AGE=input("Please guess your Age:")
    print(type(AGE))
    try:
        AGE=int(AGE)
        print(type(AGE))
    except:    # Observe that python is except unlike julias try/catch
        print("the value is not an integer")
        return
    print("\t\tyou entered:\n\t\t\t " + str(AGE))
end

main()

```

Observe a few things about this code:

- In order to print an integer as a string it is necessary to convert it back to a string by using `str()` 
- values are read in as `str`
- *Python* unlike *Julia* uses `try/except` not `try/catch`.

| Language      | command |
| ------------- | ------- |
| ***R***       | `class` |
| python 🐍      | `type`  |
| julia ***🝆*** | `type`  |


### Types of Numbers

| Set          | `type`  |
| ------------ | ------- |
| $\mathbb{R}$ | `float` |
| $\mathbb{Z}$ | `int`   |

## Variables

## Data Types

- `tuple`
    - `(3, 2, 4)`
        - immutable
- `list`
    - `['apple', 'orange', 33]`
- `Dictionary`
    - ['title': 'wikipedia', 'status': 1, 'time': 999]
        - Essentially a collection of key value pairs

  

### Examples of Language typing

| *Static Typing*                | *Dynamic Typing* |
| ------------------------------ | ---------------- |
|                                | ***R***          |
|                                | *Python*         |
| Java                           | *JavaScript*     |
| ***C*** / ***C***++ / ***C***# | *LISP* [^lisp]   |
| [*Julia*] [^jl]                | [*Julia*] [^jl]  |


[^lisp]: *LISP* is an example of a language that is dynamically typed yet still
compiled rather than interpreted.
[^jl]: Julia can use static typing if variables are declared, otherwise it may
fall back to static typing.

[*Julia*]: https://julialang.org/

## Script walk through

### Modular code

I would personally recommend writing code as nested functions, it makes debugging much simpler.

```python
def main():
    print("I am the main Function")
# end       ## Don't put an end here unlike julia or fish
main()
```
```
I am the main Function
```


### Querying for input

Let's now ask the user for some input:

```python

def main():
    ask_question()
    def ask_question():
        print("What value am I thinking of")
        chosen = input()
        print(chosen)
main()
```
    >>> What value am I thinking of
    33
    33

### Types

We need to explain to python that what we entered (in this case `33` is an
integer so that we can work with it, this can be done with the `str()`
function:)

```python
def main():
    ask_question()
    def ask_question():
        print("What value am I thinking of")
        chosen = int(input())
        print(str(chosen))
main()

```

### If Tests

Perhaps the we should tell the user whether or not the value is higher, or lower, we can do this by using an `if` test.

#### Random Values

First however we need to pick a random value, this can be done by using the `random` library:

```python
def define_value(min, max):
    import random as rand
    VALUE = rand.randint(min, max)
    return VALUE

define_value(1, 9)
```
    1

Observe in that above call:

1. `import`; this is used to import a library under a given name
2. `return`; this is required for python to return a value
   * This is distinct from ***R*** or *Julia🝆* where the last printed value is
     returned, this can be a potential ==gotchya== as there is a convention in
     ***R*** to eschew the `return` statement in functions.
3. ***capitalisation***; the variable `VALUE` is capitalised, this is a convention in many languages to indicate that the value of the variable should be *constant* for the duration of the function.
    

```python
def outer():
    inner()
    print(varin)

def inner():
    nonlocal varin
    varin = 9
    return varin

outer()
# print(varin)
```

So by default variables that have an assignment made to them inside a function,
are strictly local to that function, this can be quite surprising if you've been
using ***R***, `bash`, *Java* (???) or *Julia*, bear in mind, if you want to
access a variable, say `x`, from an above function it will be necessary to use
`nonlocal x`, somewhere inside the lower function.



#### Returning Values

*Python* can return multiple values as a tuple like this:

```Python
def outer():
    x = 9
    y = 7
    z = 8
    return x, y, z

type(outer())
```

This is unlike *Julia* and ***R*** which can only return a single object, for this reason my, if you jump between many languages, a possible recommendation could be to use the following syntax:

```python
def outer():
    x = 9
    y = 7
    z = 8
    tuppleOfVars = (9, 7, 8)
    return listOfVars

type(outer())
# print(varin)
```

It could also be possible to return it as a list, but generally you would want
this output to be read only.

- ⚠️ WARNING
  - In *Julia* tupples can only contain numeric values, in python a tupple is
    essentially an immutable list.


#### Using an `if` test

```python
def main():
    main.MIN=1
    main.MAX=9
    VALUE=define_value(1, 9)
    ask_question(value=VALUE)

def define_value(min, max):
    import random as rand
    return rand.randint(1,9)

def ask_question(value):
    print("What value am I thinking of between " + str(main.MIN) + " and " + str(main.MAX))
    choose = int(input())
    if not (1 < choose and choose < 9):
        print("Choose a value between " + str(main.MIN) + " and " + str(main.MAX))
    elif (choose != value):
        print("That is not the value")
    else :
        print("That is the correct Value good work")

main()
```

There's a few things to note here:

- `and`
    - so i find this terribly annoying and confusing, instead of using `&` or
  `&&` like every other language, *Python* uses `and`, (likewise for `||`/`or`)
- `print("string" + "string")` 
    - in *Python* strings are joined with `+`
        - in ***R*** this is done with `paste()`
        - in *Julia* this is done by comma seperating everything.
- `else :`
    - observe the ⍽ between `else` and `:`, this is also necessary.
- ***function attributes***
    - in *Python* the variables are local to functions,
    they can't be accessed from outside, this can be very disorientating if
    you've been working inside ***R*** or `bash` where this is not the case.
        - There's the `global` keyword, but don't, it's bad for your health.
    - There's also the `nonlocal` keyword which is used when modifying a variable
    defined in an above function.
    - the `nonlocal` keyword is not necessary for reading a variable defined in
      an above function, making a new variable in the absence of `nonlocal` will
      however create a variable with the same name that is local to that function.
  keywords) 
    - Instead you should have functions `return` the values you want to work with.
    - If you really want to access the variables in functions below another,
    *Python* also has function attribues, which was uses the notation
    `function.var`, this was done with `MIN` and `MAX`, these could also have
    been passed in as variables to the function.




### Loops

There are generally two types of loops you'd be concerned with:

- `for`
    - These are used when the number of iterations is known in advance
    > *for each item in my shopping list*,<br>
    >            *go purchase each item*
- `while`
    - These are used when we don't know how many iterations are required:
    > while $x < 9$, do<br>
    >                        $x = \sqrt{x}/\pi$
    
In this case we may want our function to run `while` the unser hasn't guessed the value:


```Python
def main():
    main.MIN=1
    main.MAX=9
    VALUE=define_value(1, 9)
    user_value = ask_question(value=VALUE)

    while user_value != VALUE :
        user_value = ask_question(value=VALUE)

def define_value(min, max):
    import random as rand
    return rand.randint(1,9)

def ask_question(value):
    print("What value am I thinking of between " + str(main.MIN) + " and " + str(main.MAX))
    choose = int(input())
    if not (1 < choose and choose < 9):
        print("Choose a value between " + str(main.MIN) + " and " + str(main.MAX))
    elif (choose != value):
        print("That is not the value")
    else :
        print("That is the correct Value good work")

    return choose
main()
```

#### Flow Control 


| function          | definition                  |
| ----------------- | --------------------------- |
| `break`           | get out of the loop         |
| `continue`        | get to the top of a loop    |
| `return`          | get out of a function       |
| [*exit commands*] | get out of a script [^8392] |

> [*exit commands*] are less graceful that `return`, so try and use `return` if you can.

These can be used to modify the behaviour of our script, for example we may want
to try and emulate a `do while` loop:

  <!-- Sometimes you need a dot, <br> ruins the spacing Important --><details  open markdown="1"><summary><p>

SHOW/HIDE CODE; CLICK ME!
</p></summary><p>

```python
def main():
    main.MIN=1
    main.MAX=9
    VALUE=define_value(1, 9)

    while TRUE :
        user_value = ask_question(value=VALUE)
        if user_value != VALUE:
            break

def define_value(min, max):
    import random as rand
    return rand.randint(1,9)

def ask_question(value):
    print("What value am I thinking of between " + str(main.MIN) + " and " + str(main.MAX))
    choose = int(input())
    if not (1 < choose and choose < 9):
        print("Choose a value between " + str(main.MIN) + " and " + str(main.MAX))
    elif (choose != value):
        print("That is not the value")
    else :
        print("That is the correct Value good work")

    return choose
main()
```

</p>
<!--Newline Important-->
</details>
<!--Newline Important-->

#### Recursion

That solution however was a bit hacky, an alternative solution could be acheived with recursion:

  <!-- Sometimes you need a dot, <br> ruins the spacing Important --><details  closed markdown="1"><summary><p>

SHOW/HIDE CODE; CLICK ME
</p></summary><p>

```python
def main():
    main.MIN=1
    main.MAX=9
    main.VALUE=define_value(1, 9)
    user_value = ask_question(value=main.VALUE)

def define_value(min, max):
    import random as rand
    return rand.randint(1,9)

def ask_question(value):
    print("What value am I thinking of between " + str(main.MIN) + " and " + str(main.MAX))
    choose = int(input())
    if not (1 < choose and choose < 9):
        print("Choose a value between " + str(main.MIN) + " and " + str(main.MAX))
        user_value = ask_question(value=main.VALUE)
    elif (choose != value):
        print("That is not the value")
        user_value = ask_question(value=main.VALUE)
    else :
        print("That is the correct Value good work")

    return choose
main()
```

</p>
<!--Newline Important-->
</details>
<!--Newline Important-->

- This required maiking `VALUE` an attribute of MAIN
- in this case the recursion had to occur inside `ask_question()`


[*exit commands*]: https://www.geeksforgeeks.org/python-exit-commands-quit-exit-sys-exit-and-os-_exit/
[^8392]: This is significantly le
