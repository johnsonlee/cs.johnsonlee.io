<!-- .slide: class="center" -->

## 3.3. What is an Algorithm?

*Same problem, smarter solutions*

----

## More Than One Way

In Chapter 2, we learned to give a computer step-by-step instructions.

But what happens when there's **more than one way** to solve the same problem?

* Which way is faster? <!-- .element: class="fragment" -->
* Which way is smarter? <!-- .element: class="fragment" -->
* Does it even matter? <!-- .element: class="fragment" -->

> Let's find out with a simple challenge!

----

## A Simple Challenge

Imagine you have a class list with 20 names and need to find "Emma":

```text
Alex, Ben, Chris, Dana, Emma, Fay, Grace, ...
```

How would you find her?

> There's more than one strategy — and some are **much faster** than others.

----

## Strategy 1: Check Every Name

Start from the beginning, check each name one by one:

1. Alex? No. <!-- .element: class="fragment" -->
2. Ben? No. <!-- .element: class="fragment" -->
3. Chris? No. <!-- .element: class="fragment" -->
4. Dana? No. <!-- .element: class="fragment" -->
5. Emma? **Yes!** <!-- .element: class="fragment" -->

> This works! But what if Emma were the last name on a list of 1,000?

----

## Strategy 2: Jump to the Middle

If the list is **sorted alphabetically**, try a smarter approach:

1. Look at the middle name — "Kate" <!-- .element: class="fragment" -->
2. Emma comes *before* Kate — ignore the second half <!-- .element: class="fragment" -->
3. Look at the middle of the rest — "Chris" <!-- .element: class="fragment" -->
4. Emma comes *after* Chris — ignore names before Chris <!-- .element: class="fragment" -->
5. Look at the middle again — **Emma! Found her!** <!-- .element: class="fragment" -->

> We only checked 3 names instead of 5!

----

## Same Problem, Different Speeds

| Strategy | How it works | Checks needed (20 names) |
|:---------|:-------------|:------------------------:|
| Check every name | One by one | Up to 20 |
| Jump to the middle | Cut the list in half | About 5 |

What about 1,000,000 names?

* One by one: up to **1,000,000** checks <!-- .element: class="fragment" -->
* Jump to the middle: only about **20** checks! <!-- .element: class="fragment" -->

----

## What is an Algorithm?

These step-by-step strategies have a name — they're called **algorithms**.

An **algorithm** is a step-by-step plan to solve a problem.

* The same problem can have **many** algorithms <!-- .element: class="fragment" -->
* Some algorithms are **much faster** than others <!-- .element: class="fragment" -->
* Choosing the right one matters — a lot! <!-- .element: class="fragment" -->

> An algorithm isn't just about following steps — it's about finding the **smartest** steps.

----

## The Heart of Computer Science

Computer science isn't just about **solving** problems.

It's about solving them **well**.

* Methods taught us to **organize** steps <!-- .element: class="fragment" -->
* Algorithms teach us to **choose** the best steps <!-- .element: class="fragment" -->

> This is what makes computer science exciting — finding **smarter** solutions!

----

<!-- .slide: class="center" -->

> Now let's learn our first real algorithms — starting with **searching**.
