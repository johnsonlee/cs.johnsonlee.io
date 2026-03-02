<!-- .slide: class="center" -->

## 3.4. Searching

*Finding a needle in a haystack*

----

## The Number Guessing Game

Let's play a game:

* I pick a secret number between 1 and 100 <!-- .element: class="fragment" -->
* You guess a number <!-- .element: class="fragment" -->
* I tell you "**higher**" or "**lower**" <!-- .element: class="fragment" -->

> How many guesses do you need to find the secret number?

----

## Strategy 1: Guess One by One

You could try: 1, 2, 3, 4, 5, ...

* If the secret number is 1 — **1 guess** <!-- .element: class="fragment" -->
* If the secret number is 50 — **50 guesses** <!-- .element: class="fragment" -->
* If the secret number is 100 — **100 guesses** <!-- .element: class="fragment" -->

> This is called **Linear Search** — check every possibility, one by one.

----

## Linear Search in Java

```java
public class LinearSearch {
    public static void main(String[] args) {
        int[] numbers = {38, 12, 91, 5, 23, 72, 8, 56, 2, 16};
        int target = 23;

        for (int i = 0; i < numbers.length; i++) {
            if (numbers[i] == target) {
                System.out.println("Found at index " + i);
            }
        }
    }
}
```

> Walk through each element. If it matches the target, we found it!

----

## Strategy 2: Always Guess the Middle

Instead, always guess the **middle** of the remaining range:

* Range 1–100 — guess **50** — "Higher!" <!-- .element: class="fragment" -->
* Range 51–100 — guess **75** — "Lower!" <!-- .element: class="fragment" -->
* Range 51–74 — guess **62** — "Lower!" <!-- .element: class="fragment" -->
* Range 51–61 — guess **56** — "Higher!" <!-- .element: class="fragment" -->
* Range 57–61 — guess **59** — "Correct!" <!-- .element: class="fragment" -->

> Only **5 guesses** for a number between 1 and 100!

----

## Why Is This So Fast?

Each guess **cuts the range in half**:

```text
100 → 50 → 25 → 12 → 6 → 3 → 1
```

After at most 7 guesses, you can find any number from 1 to 100.

> This strategy is called **Binary Search** — "binary" means splitting into **two** halves.

----

## Binary Search: Step by Step

Searching for **23** in a sorted array:

```text
[2, 5, 8, 12, 16, 23, 38, 56, 72, 91]
```

| Step | Search range | Middle value | Result |
|:----:|:-------------|:------------:|:-------|
| 1 | Index 0–9 | 16 | Too low — search right half |
| 2 | Index 5–9 | 56 | Too high — search left half |
| 3 | Index 5–6 | 23 | **Found it!** |

> Only 3 steps to search through 10 items!

----

## Binary Search in Java

```java
public class BinarySearch {
    public static void main(String[] args) {
        int[] numbers = {2, 5, 8, 12, 16, 23, 38, 56, 72, 91};
        int target = 23;
        int low = 0;
        int high = numbers.length - 1;

        while (low <= high) {
            int mid = (low + high) / 2;
            if (numbers[mid] == target) {
                System.out.println("Found at index " + mid);
                break; // stop searching
            } else if (numbers[mid] < target) {
                low = mid + 1;
            } else {
                high = mid - 1;
            }
        }
    }
}
```

Output: `Found at index 5`

----

## How the Code Works

* `low` and `high` mark the search range <!-- .element: class="fragment" -->
* `mid = (low + high) / 2` finds the middle index <!-- .element: class="fragment" -->
* If `numbers[mid]` is too small — move `low` up <!-- .element: class="fragment" -->
* If `numbers[mid]` is too big — move `high` down <!-- .element: class="fragment" -->
* `break` means "stop the loop" — we found our target! <!-- .element: class="fragment" -->

> Each step cuts the range in half — that's why it's so fast!

----

## Linear Search vs Binary Search

| Items | Linear Search | Binary Search |
|------:|:-------------:|:-------------:|
| 10 | up to 10 | up to 4 |
| 100 | up to 100 | up to 7 |
| 1,000 | up to 1,000 | up to 10 |
| 1,000,000 | up to 1,000,000 | up to 20 |

> Binary search is incredibly fast — but there's a catch...

----

## The Catch

Binary search only works on **sorted** data!

* If the array isn't sorted, jumping to the middle tells us nothing <!-- .element: class="fragment" -->
* Linear search works on **any** array — sorted or not <!-- .element: class="fragment" -->

> So how do we sort data? That's our next topic!

----

<!-- .slide: class="center" -->

> Before we learn to sort, let's discover a powerful technique — **recursion**!
