<!-- .slide: class="center" -->

## 3.2. Trees

*Data that branches out*

----

## Does All Data Fit in a Line?

Arrays, stacks, and queues store data in a **line** — one item after another.

But try putting your family tree in a line — does that work?

* Your dad and your uncle are **side by side**, not one after the other <!-- .element: class="fragment" -->
* Grandpa has **two** branches below him, not one <!-- .element: class="fragment" -->

> Some data naturally **branches out** — a line can't hold it. What do we do?

----

## Think of a Family Tree

You've probably seen a family tree before:

```text
      Grandma & Grandpa
         /          \
      Mom            Uncle
     /   \              \
   You   Sister       Cousin
```

* **Grandma & Grandpa** are at the top <!-- .element: class="fragment" -->
* Below them are their **children** <!-- .element: class="fragment" -->
* Below those are their **grandchildren** <!-- .element: class="fragment" -->

> Data can have the same shape — one thing connecting to several things below it.

----

## Tree Terminology

```text
        A         ← root
       / \
      B   C       ← branches
     / \   \
    D   E   F     ← leaves
```

* **Root** — the top node (A). Every tree has exactly one. <!-- .element: class="fragment" -->
* **Edge** — a connection between two nodes (the `/` and `\` lines). <!-- .element: class="fragment" -->
* **Leaf** — a node with no children (D, E, F). <!-- .element: class="fragment" -->
* **Node** — any item in the tree (A, B, C, D, E, F are all nodes). <!-- .element: class="fragment" -->

> A tree grows **downward** in computer science — the root is at the **top**!

----

## Can You Spot the Trees?

Think about it — which of these have a tree-like structure?

* Folders on your computer — folders inside folders, and files at the end <!-- .element: class="fragment" -->
* A school — principal, grade leaders, teachers, students <!-- .element: class="fragment" -->
* A tournament bracket — winners of each round advance to the next <!-- .element: class="fragment" -->

> Whenever data **branches out**, you can use a tree. Can you think of more examples?

----

## Binary Tree

A **binary tree** is a tree where each node has **at most 2 children** — a left child and a right child.

```text
        10
       /  \
      6    15
     / \     \
    3   8    20
```

* Node 10 has two children: 6 and 15 <!-- .element: class="fragment" -->
* Node 15 has only a right child: 20 <!-- .element: class="fragment" -->
* Nodes 3, 8, and 20 are leaves — they have no children <!-- .element: class="fragment" -->

> "Binary" means **two** — so each node can branch into at most two paths.

----

## Can You Spot the Pattern?

Look closely at the numbers in this binary tree:

```text
        10
       /  \
      6    15
     / \     \
    3   8    20
```

* 6 is smaller than 10 — it goes **left** <!-- .element: class="fragment" -->
* 15 is bigger than 10 — it goes **right** <!-- .element: class="fragment" -->
* Every node follows this rule: smaller on the left, bigger on the right! <!-- .element: class="fragment" -->

> This "smaller-left, bigger-right" tree is very useful — it helps us find any number quickly.

----

## Finding a Number in a Tree

Let's find the number **8**, starting from the top:

```text
        10         8 < 10 → go left
       /
      6            8 > 6  → go right
       \
        8          Found it!
```

Only **3 steps** — no need to check every number from start to end! <!-- .element: class="fragment" -->

> Each step eliminates **half** the numbers. Doesn't it remind you of the guessing game?

----

## Reading All Numbers in Order

If we read this tree following the rule "left first, then self, then right":

```text
        10
       /  \
      6    15
     / \     \
    3   8    20

Read out: 3 → 6 → 8 → 10 → 15 → 20
```

> Notice? The numbers come out **sorted from smallest to biggest**! The "smaller-left, bigger-right" rule makes sorting happen naturally.

----

## Think About It

* A binary tree with 2 levels (root + one layer of children) can hold 3 nodes. How about 3 levels? <!-- .element: class="fragment" -->
* To find the number 20 in the tree above, which way would you go at each step? <!-- .element: class="fragment" -->
* If the tree had 1,000 numbers, what's the most steps you'd need? <!-- .element: class="fragment" -->

> Trees let data **branch out** — something a line can never do.

----

<!-- .slide: class="center" -->

> Now we know several ways to organize data — arrays, stacks, queues, and trees. Next, let's learn to solve problems **wisely** — that's what **algorithms** are about!
