<!-- .slide: class="center" -->

## 3.1. Stacks and Queues

*The right container for the right job*

----

## Do You Always Need a Position Number?

Arrays are like a row of numbered boxes — great for accessing any item by index.

But think about it — do you **always** need to know the position?

* When stacking plates, do you say "give me plate #3"? You just take the **top** one! <!-- .element: class="fragment" -->
* When lining up for lunch, do you say "person at position 5, come out"? You just look at **who's first**! <!-- .element: class="fragment" -->

> Sometimes, not worrying about position numbers makes things simpler. Let's see what this means.

----

## What If You Could Pull Any Plate?

A cafeteria has a stack of plates. What if anyone could pull one from the **middle**?

* The plates above might all come crashing down <!-- .element: class="fragment" -->
* Nobody knows which plate to grab next <!-- .element: class="fragment" -->

So the rule is simple: **only take from the top**. <!-- .element: class="fragment" -->

> This constraint isn't a hassle — it's **protection**. A **stack** in computing follows this rule: **L**ast **I**n, **F**irst **O**ut (LIFO).

----

## Stack Operations

A stack has two operations:

* **Push** — put an item on top
* **Pop** — take the item off the top

![Stack Operations](src/en/images/stack-ops.svg) <!-- .element: style="width: 70%" -->

> Think of the Undo button — it always undoes the **last** action first!

----

## Building a Stack with Code

We want to use an array as a stack — but this time we can't fill in all the values upfront. We need **empty boxes** to push into one by one:

```java
// Before: values already inside
int[] scores = {90, 85, 78, 92, 88};

// Now: empty boxes, ready for pushing
int[] stack = new int[10]; // 10 slots, waiting to be pushed into
```

> `new int[10]` creates an array with 10 slots, all starting at 0.

----

## Stack in Java

```java
public class StackDemo {
    public static void main(String[] args) {
        int[] stack = new int[10]; // 10 empty boxes
        int top = 0;

        stack[top] = 42; top++;    // push 42
        stack[top] = 17; top++;    // push 17
        stack[top] = 8;  top++;    // push 8

        top--;                      // pop
        System.out.println(stack[top]); // 8
        top--;                      // pop
        System.out.println(stack[top]); // 17
    }
}
```

> `top` tracks the next empty slot. Push increases it; pop decreases it.

----

## What If Anyone Could Cut in Line?

Imagine the lunch line with no rules — anyone can push to the front.

* The students who came first never get served <!-- .element: class="fragment" -->
* Everyone shoves forward — total chaos <!-- .element: class="fragment" -->

So the rule is simple: **first come, first served** — newcomers go to the back. <!-- .element: class="fragment" -->

> This rule is called **FIFO** — **F**irst **I**n, **F**irst **O**ut. A **queue** in computing follows this rule.

----

## Queue Operations

A queue has two operations:

* **Enqueue** — join the back of the line
* **Dequeue** — leave from the front

![Queue Operations](src/en/images/queue-ops.svg) <!-- .element: style="width: 45%" -->

> Think of the lunch line — the first student in line gets served first!

----

## Queue in Java

```java
public class QueueDemo {
    public static void main(String[] args) {
        String[] queue = new String[10]; // 10 empty boxes
        int front = 0;
        int back = 0;

        queue[back] = "Alice";   back++;  // enqueue
        queue[back] = "Bob";     back++;  // enqueue
        queue[back] = "Charlie"; back++;  // enqueue

        System.out.println(queue[front]); // Alice
        front++;                           // dequeue
        System.out.println(queue[front]); // Bob
        front++;                           // dequeue
    }
}
```

> `front` and `back` track the two ends of the line.

----

## Which Would You Pick?

For each situation, which container would you use?

* The browser's Back button — always goes to the **last** page you visited? <!-- .element: class="fragment" -->
* The lunch line — the **first** student in line gets served first? <!-- .element: class="fragment" -->
* A grade book — look up a student's score by **student ID**? <!-- .element: class="fragment" -->

> Stack, queue, array — there's no "best" one, only the **right fit**!

----

<!-- .slide: class="center" -->

> Stacks and queues add items one at a time. But sometimes data has a branching structure — like a family tree. Let's explore **trees**!
