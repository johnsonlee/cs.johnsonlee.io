<!-- .slide: class="center" -->

## 2.3. Making Decisions and Repeating

*Teaching computers to choose and persist*

----

## Choices in Daily Life

Every day, you make decisions:

* If it's sunny → wear sunglasses <!-- .element: class="fragment" -->
* If it's raining → take an umbrella <!-- .element: class="fragment" -->
* If it's cold → put on a jacket <!-- .element: class="fragment" -->

> You check a **condition**, then **act** based on the result.

----

## `if` in Java

Java makes decisions the same way:

```java
int temperature = 35;

if (temperature > 30) {
    System.out.println("It's hot! Stay hydrated.");
}
```

* The **condition** goes inside `( )`
* The **action** goes inside `{ }`

> The code inside `{ }` only runs when the condition is `true`.

----

## `if / else` — Two Choices

What if there are two options?

```java
int temperature = 15;

if (temperature > 30) {
    System.out.println("It's hot!");
} else {
    System.out.println("It's not too hot.");
}
```

* `if` — runs when the condition is `true` <!-- .element: class="fragment" -->
* `else` — runs when the condition is `false` <!-- .element: class="fragment" -->

> Like a fork in the road — you go one way or the other, never both.

----

## `else if` — Multiple Choices

What if there are more than two options?

```java
int score = 85;

if (score >= 90) {
    System.out.println("Excellent!");
} else if (score >= 70) {
    System.out.println("Good job!");
} else if (score >= 60) {
    System.out.println("You passed.");
} else {
    System.out.println("Keep trying!");
}
```

> Java checks each condition **top to bottom** and runs the **first** match.

----

## Combining Conditions

Sometimes one condition is not enough:

* `&&` means **and** — both must be true <!-- .element: class="fragment" -->
* `||` means **or** — at least one must be true <!-- .element: class="fragment" -->

```java
int age = 10;
boolean hasTicket = true;

if (age >= 6 && hasTicket) {
    System.out.println("You can enter!");
}
```
<!-- .element: class="fragment" -->


----

<!-- .slide: class="center" -->

### Now the computer can make decisions.

### But what about doing something over and over?

----

## The Problem with Repetition

Imagine you want to print "Hello!" 5 times:

```java
System.out.println("Hello!");
System.out.println("Hello!");
System.out.println("Hello!");
System.out.println("Hello!");
System.out.println("Hello!");
```

That works... but what about 100 times? 1000 times?

> There must be a better way!

----

## `for` Loop — A Counting Machine

```java
for (int i = 0; i < 5; i++) {
    System.out.println("Hello!");
}
```

This prints "Hello!" exactly 5 times.

Let's break it down:

| Part | Meaning |
|:-----|:--------|
| `int i = 0` | Start counting from 0 |
| `i < 5` | Keep going while `i` is less than 5 |
| `i++` | After each round, add 1 to `i` |

> The loop counts: 0, 1, 2, 3, 4 — that's 5 rounds!

----

## Seeing the Counter

```java
for (int i = 0; i < 5; i++) {
    System.out.println("Round " + i);
}
```

Output:

```text
Round 0
Round 1
Round 2
Round 3
Round 4
```

> Notice: we start from **0**, not 1. This is a convention in most programming languages!

----

## `while` Loop — Repeat Until Done

A `while` loop keeps going as long as a condition is `true`:

```java
int count = 1;

while (count <= 5) {
    System.out.println("Count: " + count);
    count++;
}
```

Output:

```text
Count: 1
Count: 2
Count: 3
Count: 4
Count: 5
```

> `for` is best when you know **how many times**. `while` is best when you don't.

----

## Loops + Conditions = Power

Let's count how many even numbers are between 1 and 10:

```java
int evenCount = 0;

for (int i = 1; i <= 10; i++) {
    if (i % 2 == 0) {
        evenCount++;
    }
}

System.out.println("Even numbers: " + evenCount);
```

Output: `Even numbers: 5`

> Loops and conditions work **together** to solve real problems!

----

<!-- .slide: class="center" -->

> The computer never gets tired, never gets bored.
>
> It will repeat a billion times without a single complaint.
>
> That's the power of loops.
