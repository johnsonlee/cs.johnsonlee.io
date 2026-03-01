<!-- .slide: class="center" -->

## 2.4. Methods and Arrays

*Reusable tricks and rows of boxes*

----

## A Daily Routine

Imagine teaching a robot to make a sandwich:

1. Get two slices of bread <!-- .element: class="fragment" -->
2. Spread peanut butter <!-- .element: class="fragment" -->
3. Add jelly <!-- .element: class="fragment" -->
4. Put the slices together <!-- .element: class="fragment" -->

> If the robot makes a sandwich every day, do we repeat these 4 steps every time?

----

## Methods — Name the Routine

Instead, we give the routine a **name**: `makeSandwich`.

Now we just say: `makeSandwich()` — and the robot knows what to do!

```java
public static void makeSandwich() {
    System.out.println("1. Get bread");
    System.out.println("2. Spread peanut butter");
    System.out.println("3. Add jelly");
    System.out.println("4. Put slices together");
}
```

> A **method** is a named, reusable block of instructions.

----

## Calling a Method

Defining a method is like writing a recipe.

**Calling** a method is like following the recipe:

```java
public static void main(String[] args) {
    makeSandwich();    // make one sandwich
    makeSandwich();    // make another!
}
```

> Define once, use as many times as you want.

----

## Parameters — Customize the Routine

What if we want to greet different people?

```java
public static void greet(String name) {
    System.out.println("Hello, " + name + "!");
}

public static void main(String[] args) {
    greet("Alice");    // Hello, Alice!
    greet("Bob");      // Hello, Bob!
}
```

* `name` is a **parameter** — a variable that gets its value when the method is called

> Parameters make methods flexible — same recipe, different ingredients!

----

## Return Values — Getting Answers Back

Sometimes we want a method to **give back** a result:

```java
public static int add(int a, int b) {
    return a + b;
}

public static void main(String[] args) {
    int result = add(3, 5);
    System.out.println(result);    // 8
}
```

* `int` before the method name means it gives back an `int` <!-- .element: class="fragment" -->
* `void` means "gives back nothing" <!-- .element: class="fragment" -->
* `return` sends the answer back to the caller <!-- .element: class="fragment" -->

----

<!-- .slide: class="center" -->

### Methods let us organize and reuse code.

### But what about organizing **data**?

----

## The Problem with Many Values

What if a teacher has 5 students and wants to store their scores?

```java
int score0 = 90;
int score1 = 85;
int score2 = 78;
int score3 = 92;
int score4 = 88;
```

That works for 5... but what about 30? 300?

> We need a way to store **many values** of the same type together.

----

## Arrays — A Row of Boxes

An **array** is a row of numbered boxes:

```text
 index:   0     1     2     3     4
        +-----+-----+-----+-----+-----+
        | 90  | 85  | 78  | 92  | 88  |
        +-----+-----+-----+-----+-----+
```

In Java:

```java
int[] scores = {90, 85, 78, 92, 88};
```

> Each box has an **index** (position number), starting from **0**.

----

## Accessing Array Elements

Use the index in `[ ]` to read or change a specific box:

```java
int[] scores = {90, 85, 78, 92, 88};

System.out.println(scores[0]);    // 90 (first element)
System.out.println(scores[2]);    // 78 (third element)
System.out.println(scores[4]);    // 88 (fifth element)

scores[1] = 95;                   // change the second element
System.out.println(scores[1]);    // 95
```

> Remember: the index starts from **0**, so the 1st element is `scores[0]`!

----

## Looping Through an Array

The real power of arrays comes with **loops**:

```java
int[] scores = {90, 85, 78, 92, 88};

for (int i = 0; i < scores.length; i++) {
    System.out.println("Student " + i + ": " + scores[i]);
}
```

Output:

```text
Student 0: 90
Student 1: 85
Student 2: 78
Student 3: 92
Student 4: 88
```

> `scores.length` gives us the number of elements — no need to remember it ourselves!

----

## Chapter 2 Summary

We've come a long way:

* **Chapter 1** — What computers understand: bits, numbers, text <!-- .element: class="fragment" -->
* **Chapter 2** — How we talk to computers: variables, conditions, loops, methods, arrays <!-- .element: class="fragment" -->
* **Chapter 3** (next) — How to organize data and solve problems efficiently <!-- .element: class="fragment" -->

> Now you have all the tools to write real programs.
>
> Next, we'll learn to use them **wisely** — that's what algorithms are all about!
