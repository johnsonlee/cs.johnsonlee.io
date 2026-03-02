<!-- .slide: class="center" -->

## 3.6. Sorting

*Putting things in order*

----

## Why Sort?

Sorted data is **powerful**:

* Binary search only works on sorted data <!-- .element: class="fragment" -->
* Sorted lists are easier to read and understand <!-- .element: class="fragment" -->
* Dictionaries, contacts, leaderboards — all sorted! <!-- .element: class="fragment" -->

> Sorting is one of the most important tasks in computer science.

----

## Sorting Cards in Your Hand

Imagine you're holding 5 cards: **5, 3, 8, 1, 2**

How would you sort them?

One simple way: **compare two neighbors** and swap them if they're in the wrong order. Repeat until everything is sorted!

> This is called **Bubble Sort** — the biggest numbers slowly "bubble up" to the end.

----

## Why "Bubble" Sort?

![Bubble Sort](src/en/images/bubble-sort.svg) <!-- .element: style="width: 35%" -->

Just like big air bubbles rise to the surface in water, **big numbers rise to the end** of the array!

----

## Bubble Sort: One Pass

Compare each pair of neighbors from bottom to top — swap if the lower one is bigger:

```text
┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐
│  2  │ │  2  │ │  2  │ │  2  │ │  8  │ ← 8 bubbled
│  1  │ │  1  │ │  1  │ │  8  │ │  2  │   to the top!
│  8  │ │  8  │ │  8  │ │  1  │ │  1  │
│  3  │ │  5  │ │  5  │ │  5  │ │  5  │
│  5  │ │  3  │ │  3  │ │  3  │ │  3  │
└─────┘ └─────┘ └─────┘ └─────┘ └─────┘
 5 & 3   3 & 5   5 & 8   8 & 1   8 & 2
 swap!    OK      OK     swap!   swap!
```

> After one pass, the **biggest** number floats to the top — it's in its final position!

----

## Bubble Sort: Pass by Pass

Repeat until every number floats to its place:

```text
  Start   Pass 1   Pass 2   Pass 3   Done!
┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐
│  2  │ │  8  │ │  8  │ │  8  │ │  8  │
│  1  │ │  2  │ │  5  │ │  5  │ │  5  │
│  8  │ │  1  │ │  2  │ │  3  │ │  3  │
│  3  │ │  5  │ │  1  │ │  2  │ │  2  │
│  5  │ │  3  │ │  3  │ │  1  │ │  1  │
└─────┘ └─────┘ └─────┘ └─────┘ └─────┘
           ↑ 8     ↑ 5     ↑ 3
```

> After each pass, one more number is locked in place at the top — the next pass can skip it!

----

## Fewer Comparisons Each Pass

After each pass, one more number is sorted at the top — skip it next time:

| Pass | Sorted at top | Comparisons |
|-----:|:-------------:|:-----------:|
| Pass 1 | 0 | 4 |
| Pass 2 | 1 | 3 |
| Pass 3 | 2 | 2 |
| Pass 4 | 3 | 1 |

> Pattern: for N numbers, pass `i` needs `N - 1 - i` comparisons.

----

## Bubble Sort in Java

```java
public class BubbleSort {
    public static void main(String[] args) {
        int[] numbers = {5, 3, 8, 1, 2};

        for (int i = 0; i < numbers.length - 1; i++) {
            for (int j = 0; j < numbers.length - 1 - i; j++) {
                if (numbers[j] > numbers[j + 1]) {
                    int temp = numbers[j];
                    numbers[j] = numbers[j + 1];
                    numbers[j + 1] = temp;
                }
            }
        }
        for (int k = 0; k < numbers.length; k++) {
            System.out.println(numbers[k]);
        }
    }
}
```

Output: `1  2  3  5  8`

----

## How the Code Works

* **Outer loop** (`i`): counts completed passes <!-- .element: class="fragment" -->
* **Inner loop** (`j`): only walks through unsorted numbers — `- i` skips the ones already sorted at the top! <!-- .element: class="fragment" -->
* **The swap**: uses a helper variable `temp` to exchange two values <!-- .element: class="fragment" -->

```java
int temp = numbers[j];          // save the left value
numbers[j] = numbers[j + 1];   // move right value left
numbers[j + 1] = temp;         // put saved value on right
```
<!-- .element: class="fragment" -->

> Without `temp`, we'd lose one of the values during the swap!

----

## How Many Comparisons?

| Items | Comparisons (approx.) |
|------:|:---------------------:|
| 5 | 10 |
| 10 | 45 |
| 100 | ~5,000 |
| 1,000 | ~500,000 |

Double the items — **four times** the work!

> For large data, bubble sort is too slow. Can we do better? <!-- .element: class="fragment" -->

----

## Merge Sort: Split and Merge

Sorting 1 number needs no work — so keep splitting, then merge back!

![Merge Sort](src/en/images/merge-sort.svg) <!-- .element: style="width: 55%" -->

> **Split** until tiny, **merge** back in order — that's **Merge Sort**!

----

## Quick Sort: Pick a Pivot

Pick one number as the **pivot** — smaller goes left, bigger goes right:

![Quick Sort](src/en/images/quick-sort.svg) <!-- .element: style="width: 55%" -->

> For 1,000 numbers: bubble sort ≈ 500,000 comparisons, quick sort ≈ only 10,000!

----

## The Key Lesson

The **right algorithm** makes a huge difference:

* Binary search vs linear search — millions of times faster <!-- .element: class="fragment" -->
* Quick sort vs bubble sort — thousands of times faster <!-- .element: class="fragment" -->

> As data grows bigger, choosing the right algorithm becomes more and more important.

----

## Chapter 3 Summary

Let's look back at how far we've come:

* **Chapter 1** — What computers understand: bits, numbers, text <!-- .element: class="fragment" -->
* **Chapter 2** — How we talk to computers: variables, loops, methods, arrays <!-- .element: class="fragment" -->
* **Chapter 3** — How to organize data and solve problems wisely <!-- .element: class="fragment" -->

> You now know how to write programs **and** make them efficient.

----

<!-- .slide: class="center" -->

> Next, we'll learn how to build **real software** as a team — that's what software engineering is all about!
