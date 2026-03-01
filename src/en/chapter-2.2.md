<!-- .slide: class="center" -->

## 2.2. Variables and Operations

*Teaching computers to remember and calculate*

----

## A Forgetful Computer

In the last section, we told the computer to print "Hello, World!".

It did it — then forgot everything.

> What if we want it to **remember** something?

----

## Variables = Labeled Boxes

A **variable** is like a labeled box.

```text
  +-------+
  |  10   |    ← the value inside
  +-------+
    age        ← the label (name)
```

* You give the box a **name** (label)
* You put a **value** inside

> In Java, you also need to say what **type** of thing goes in the box.

----

## Types — What Goes in the Box?

Java needs to know the type **before** you store anything:

| Type | What it stores | Example |
|:-----|:---------------|:--------|
| `int` | Whole numbers | `10`, `-3`, `0` |
| `double` | Decimal numbers | `3.14`, `-0.5` |
| `String` | Text | `"Hello"`, `"Alice"` |
| `boolean` | True or false | `true`, `false` |

> Think of the type as the **shape** of the box — only matching things fit in.

----

## Declaring and Assigning

To create a variable, we **declare** it:

```java
int age;           // create a box labeled "age" for whole numbers
age = 10;          // put the value 10 inside
```

Or do both at once:

```java
int age = 10;      // create the box and put 10 in it
```

----

## More Examples

```java
double height = 1.45;
String name = "Alice";
boolean isHappy = true;
```

Each variable has three things:

* A **type** — what kind of value (`int`, `double`, `String`, `boolean`) <!-- .element: class="fragment" -->
* A **name** — how we refer to it (`height`, `name`, `isHappy`) <!-- .element: class="fragment" -->
* A **value** — what's stored inside (`1.45`, `"Alice"`, `true`) <!-- .element: class="fragment" -->

----

## Arithmetic — The Calculator

Java can do math, just like a calculator:

| Operator | Meaning | Example | Result |
|:--------:|:--------|:--------|:-------|
| `+` | Add | `3 + 5` | `8` |
| `-` | Subtract | `10 - 4` | `6` |
| `*` | Multiply | `6 * 7` | `42` |
| `/` | Divide | `15 / 3` | `5` |
| `%` | Remainder | `10 % 3` | `1` |

----

## Using Arithmetic

```java
int a = 10;
int b = 3;

int sum = a + b;       // 13
int diff = a - b;      // 7
int product = a * b;   // 30
int quotient = a / b;  // 3 (integer division!)
int remainder = a % b; // 1
```

> Notice: `10 / 3` gives `3`, not `3.33`! Integer division drops the decimal part.

----

## Comparison — True or False?

We can also **compare** values:

| Operator | Meaning | Example | Result |
|:--------:|:--------|:--------|:-------|
| `>` | Greater than | `5 > 3` | `true` |
| `<` | Less than | `5 < 3` | `false` |
| `>=` | Greater or equal | `5 >= 5` | `true` |
| `<=` | Less or equal | `3 <= 5` | `true` |
| `==` | Equal to | `5 == 5` | `true` |
| `!=` | Not equal to | `5 != 3` | `true` |

> The result of a comparison is always a `boolean` — `true` or `false`.

----

## Watch Out: `=` vs `==`

They look similar, but mean very different things!

* `=` means **assign** — put a value into a box <!-- .element: class="fragment" -->
* `==` means **compare** — are they the same? <!-- .element: class="fragment" -->

```java
int x = 5;      // assign: put 5 into x
x == 5           // compare: is x equal to 5? → true
```
<!-- .element: class="fragment" -->

> This is a classic beginner mistake — don't mix them up!

----

## String Concatenation

The `+` operator also works with text — it **joins** strings together:

```java
String first = "Hello";
String second = "World";
String greeting = first + ", " + second + "!";
// greeting is "Hello, World!"
```

You can even mix strings and numbers:

```java
String message = "I am " + 10 + " years old.";
// message is "I am 10 years old."
```

----

## Putting It All Together

```java
public class MyCalculator {
    public static void main(String[] args) {
        int apples = 12;
        int friends = 4;
        int each = apples / friends;
        int leftover = apples % friends;
        System.out.println("Each friend gets " + each + " apples.");
        System.out.println("Leftover: " + leftover);
    }
}
```

Output:

```text
Each friend gets 3 apples.
Leftover: 0
```

> It can **remember** and **calculate** — next, let's teach it to make **decisions**!
