<!-- .slide: class="center" -->

## 3.5. Recursion

*A function that calls itself*

----

## Russian Dolls

Imagine a set of Russian nesting dolls:

* You open the big doll — there's a **smaller doll** inside <!-- .element: class="fragment" -->
* You open that one — there's an **even smaller** doll inside <!-- .element: class="fragment" -->
* Keep opening... until you reach the **tiniest doll** that doesn't open <!-- .element: class="fragment" -->
* Then you put them all back together, one inside the other <!-- .element: class="fragment" -->

> That's exactly how recursion works — solve a big problem by solving smaller and smaller versions, until you hit the smallest one!

----

## What is Recursion?

**Recursion** is when a method calls **itself** to solve a smaller version of the same problem.

Every recursive method needs two parts:

* **Base case** — when to **stop** (the tiniest doll) <!-- .element: class="fragment" -->
* **Recursive case** — call yourself with a **smaller** problem (open the next doll) <!-- .element: class="fragment" -->

> Without a base case, the method would call itself forever — like an infinite loop!

----

## Countdown: The Idea

Let's count down from 5 to 1:

* To count down from 5: print 5, then count down from 4 <!-- .element: class="fragment" -->
* To count down from 4: print 4, then count down from 3 <!-- .element: class="fragment" -->
* To count down from 3: print 3, then count down from 2 <!-- .element: class="fragment" -->
* ... <!-- .element: class="fragment" -->
* To count down from 0: **stop!** (base case) <!-- .element: class="fragment" -->

> Each step is the same problem, just with a smaller number!

----

## Countdown in Java

```java
public class Countdown {
    public static void countdown(int n) {
        if (n == 0) {
            System.out.println("Go!");
            return; // base case: stop here
        }
        System.out.println(n);
        countdown(n - 1); // recursive case: smaller problem
    }

    public static void main(String[] args) {
        countdown(5);
    }
}
```

Output: `5  4  3  2  1  Go!`

----

## Trace the Calls

When we call `countdown(5)`, here's what happens:

```text
countdown(5)  → prints 5, then calls...
  countdown(4)  → prints 4, then calls...
    countdown(3)  → prints 3, then calls...
      countdown(2)  → prints 2, then calls...
        countdown(1)  → prints 1, then calls...
          countdown(0)  → prints "Go!" and stops!
```

> Each call waits for the next one to finish — like opening dolls one by one.

----

## Factorial: A Classic Example

**Factorial** means multiplying a number by every number below it:

* $5! = 5 \times 4 \times 3 \times 2 \times 1 = 120$

We can write this recursively:

* $5! = 5 \times 4!$ <!-- .element: class="fragment" -->
* $4! = 4 \times 3!$ <!-- .element: class="fragment" -->
* $3! = 3 \times 2!$ <!-- .element: class="fragment" -->
* $2! = 2 \times 1!$ <!-- .element: class="fragment" -->
* $1! = 1$ (base case!) <!-- .element: class="fragment" -->

> Each factorial is defined in terms of a **smaller** factorial — that's recursion!

----

## Factorial in Java

```java
public class Factorial {
    public static int factorial(int n) {
        if (n == 1) {
            return 1; // base case
        }
        return n * factorial(n - 1); // recursive case
    }

    public static void main(String[] args) {
        int result = factorial(5);
        System.out.println("5! = " + result);
    }
}
```

Output: `5! = 120`

----

## Trace the Factorial Calls

```text
factorial(5)
  = 5 * factorial(4)
  = 5 * 4 * factorial(3)
  = 5 * 4 * 3 * factorial(2)
  = 5 * 4 * 3 * 2 * factorial(1)
  = 5 * 4 * 3 * 2 * 1
  = 120
```

> The method keeps calling itself until it reaches the base case, then multiplies everything back together — like putting the dolls back inside each other!

----

## Why Recursion Matters

Some problems are **naturally recursive** — they contain smaller copies of themselves:

* A **tree** has branches, and each branch is also a tree <!-- .element: class="fragment" -->
* A **folder** contains files and other folders <!-- .element: class="fragment" -->
* **Binary search** splits data in half — each half is the same problem, just smaller <!-- .element: class="fragment" -->

> Preview: **merge sort** and **quick sort** both use recursion to split and conquer!

----

## Recursion vs Loops

Every recursion **can** be written as a loop — and vice versa. Here's factorial both ways:

| Recursion | Loop |
|:----------|:-----|
| `factorial(5)` calls `factorial(4)` calls `factorial(3)`... | `result = 1; for i = 1 to 5: result = result * i` |
| Breaks the problem into **smaller pieces** | Builds the answer **step by step** |
| Can be easier to **think about** | Can be easier to **run efficiently** |

> Some problems (like trees and folders) are much easier to think about with recursion. Use whichever makes the code clearer!

----

<!-- .slide: class="center" -->

> Now that we understand recursion, we're ready to tackle **sorting** — and some really clever algorithms!
