# Working With String

## Learning Goals

* Recognize how to declare a `String` with double-quotes
* Recognize how to declare a `String` with single-quotes
* State the difference between single- and double-quoted `String`s
* Define _interpolation_
* Explain how different quote characters allow flexibility
* Demonstrate escaping double-quotes in a `String`
* Join `String`s using `+`
* Identify why `TypeError` happens when + `String` with `Integer`

## Introduction

Thus far in programming as conversation, we've really used numbers a lot. We
use numbers because they reach across language, culture, time itself.

But as we start writing more advanced programs, we want to say fun things like
`"Byron the poodle barks 10 times"`. These, occasionally silly, programs help us
get the grasp of programming. As a result, we need to learn a bit more about
the `String` type.

It's just like when we learned to talk: We learned to ask questions, make
statements, and communicate usefully, but at some point we were expected to
give our responses in full, proper sentences. So, let's learn how to format
Python's responses into meaningful `String`s.

## Recognize How to Declare a `String` with Double-quotes

We declare `String`s most often by putting them in double-quotes:

```Python
greeting = "Hello, folks"
```

## Recognize How to Declare a `String` with Single-quotes

We can also declare `String`s by putting them in single-quotes:

```Python
greeting = 'Hello, folks'
```

## State the difference between single- and double-quoted `String`s

The difference between single- and double-quoted `String`s is best seen when
using a special power of the `String`, _interpolating_ data.

### Define _Interpolation_

When you use the _interpolation operator_ you take data from the programming
language, convert it to a `String`, and then place it inside the `String`. In
Python, we can interpolate data in a few ways, but in this leson, we'll look at
"f-strings." An f-string, short for formatted string, allows us to "plug in"
the value of an expression after converting the result of the expression to a
`String`. F-strings always start with an `f`, followed by text wrapped in single
or double quotes.

```python
formatted_string = f'hello world!'
```

Inside the quotations of an f-string, if we include a set of curly braces (`{}`),
we can add expressions to be evaluated:

```Python
bark_count = 3
dq = f"Byron barks {bark_count} times" #=> "Byron barks 3 times"
sq = f'Byron barks {bark_count} times' #=> "Byron barks 3 times"
```

Although `bark_count` is assigned to an Integer, when placed inside curly braces
in an f-string, the Integer is converted to a String.

## Explain How Different Quote Characters Allow Flexibility

What if you needed to store some dialog:

> "Wait," said Jo, "Do not go without me!"

Given the number of `"` used for direct speech, it might be a wise choice to use
a single-quote here.

```Python
little_woman_esque = '"Wait," said Jo, "Do not go without me!"'
```

Because the opening boundary of the `String` was `'`, Python will "close" the
`String` at the next `'` &mdash; at the very end. Inside of the `'...'`, the
`"` loses its meaning of "here's a `String`" and, instead, is just a plain
letter.

## Demonstrate Escaping Single-Quotes and Double-Quotes in a `String`

On the rare occassion, we might need to write a `String` that has both single-quotes _and_ double-quotes.

```text
"Sometimes we use 'single-quotes' within a set of 'double-quotes'"
```

We can't wrap the above sentence in either single-quotes or double-quotes. When
Python encounters a single- or double-quote, it ignores all characters until it
reaches a matching single- or double-quote. If we were to use double-quotes:

```python
""Sometimes we use 'single-quotes' within a set of 'double-quotes'""
```

Python would interpret the pairs of double-quotes at the beginning and end as
_empty_ `Strings` (`""`). Python won't know what to do with `Sometimes`, producing
a syntax error. To prevent this, we can use _triple_-quotes to wrap a `String`:

```Python
'''"Sometimes we use 'single-quotes' within a set of 'double-quotes'"'''
```

Just as with single- and double-quotes, Python will look for opening and closing
triple-quotes and consider everything in between to be part of the `String`.

## Join `String`s using `+`

Now here's an interesting use of the `+` operator when placed between
`String`s, it joins them and returns a ***new*** `String`.

```Python
first_name = "Byronius"
clan_name = "Karbitus"
common_name = "Maris"

# With +
first_name + " " + clan_name + " " + common_name #=> "Byronius Karbitus Maris"

# Or, with interpolation, like you already know
f"{first_name} {clan_name} {common_name}" #=> "Byronius Karbitus Maris"
```

## Identify Why TypeError Happens When + String with Integer

Be careful, `+` only joins `Strings` with both sides are `String`

```Python
fact = "Byron is "
tail = " years old"
age = 5

fact + age + tail #=> TypeError: must be str, not int
```

Python is not sure whether you want to add like an `Integer` (stored in `tail`)
or add like `String`s! If you need to do this, you should use the `str()` method
on data.

```Python
fact = "Byron is "
tail = " years old"
age = 5

fact + str(age) + tail #=> "Byron is 5 years old"
```

The `str()` method can convert any other data type into a `String` by placing
the value inside the parentheses after `str`. Once a non-`String` is converted
to a `String`, it can be joined with `+` to another `String`. You might still be
unclear on what a "method" is. That's OK, we'll cover it in detail later.  You
might remember the `.class` method we introduced when we were talking about
type, earlier. For now, think of them as "commands" you can ask values to do in
Object-Oriented languages, like Python.

## Conclusion

With mastery of `String` we can use the expressions we've learned thus far to
make interesting programs using only expressions. We're going to provide an
example in the next lesson.
