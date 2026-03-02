<!-- .slide: class="center" -->

## 2.1. What is a Programming Language?

*From human language to computer language*

----

## How Do We Communicate?

Every day, we talk to other people.

We use **language** — Chinese, English, Spanish...

> Language lets us share ideas, ask questions, and give instructions.

----

## Can We Talk to a Computer?

Actually — we can talk to **AI**!

We can ask AI to:

* "Draw me a cat!" → it draws one! <!-- .element: class="fragment" -->
* "Write a story!" → it writes one! <!-- .element: class="fragment" -->
* "Help me with math!" → it helps! <!-- .element: class="fragment" -->

> But here's a secret... <!-- .element: class="fragment" -->

----

## AI is Also a Program

AI seems to understand human language.

But AI itself is a **program** — written by programmers using programming languages.

* Programmers wrote millions of lines of code <!-- .element: class="fragment" -->
* They trained AI with huge amounts of data <!-- .element: class="fragment" -->
* All of that was built with programming languages <!-- .element: class="fragment" -->

> Without programming languages, there would be no AI.

----

## Computer vs AI

| | Computer | AI |
|:---|:---------|:---|
| What | The machine itself | A program running on the machine |
| Understands | Only 0s and 1s | Human language (because programmers taught it) |
| Built by | Engineers | Programmers, using programming languages |

> To truly understand how things work, we need to learn the language that builds everything — a **programming language**.

----

## Why Not Just Use Human Language?

Human language is **ambiguous**.

* "I saw a man on the hill with a telescope" — who has the telescope? <!-- .element: class="fragment" -->
* "It's cold" — should I close the window? Turn on the heater? <!-- .element: class="fragment" -->

> Humans can guess from context. Computers cannot. <!-- .element: class="fragment" -->

----

## What Computers Need

Computers need instructions that are:

* **Exact** — no ambiguity <!-- .element: class="fragment" -->
* **Step-by-step** — one thing at a time <!-- .element: class="fragment" -->
* **Following strict rules** — like grammar, but stricter <!-- .element: class="fragment" -->

> This is what a **programming language** provides.

----

<!-- .slide: class="center" -->

> A programming language is a way to write precise instructions that a computer can follow — no guessing needed.

----

## Many Programming Languages

Just like people speak many human languages, there are many programming languages too:

* **Python** — the most popular, very concise to write <!-- .element: class="fragment" -->
* **C / C++** — the fastest, used to build many video games <!-- .element: class="fragment" -->
* **Java** — used by tens of millions of programmers worldwide <!-- .element: class="fragment" -->

> So many choices! Which one should we learn first?

----

## Why Not Python?

Python is the most popular — but it has tricky parts for beginners:

* **Invisible traps** — one extra space or one missing space breaks your program, and it's hard to see what went wrong <!-- .element: class="fragment" -->
* **No labels on boxes** — you don't have to say what type of thing goes in a box, but that makes it easy to mix things up <!-- .element: class="fragment" -->

> Popular doesn't always mean best for learning. <!-- .element: class="fragment" -->

----

## Why Not C / C++?

C and C++ are fast and powerful — but they're tough for beginners:

* **You clean up your own mess** — when your program is done using something, you must clean it up yourself; forget once and the program crashes <!-- .element: class="fragment" -->
* **Too much setup** — you need to install many tools before you can even write your first line of code <!-- .element: class="fragment" -->

> Too much power can be a burden — too complex for a first language. <!-- .element: class="fragment" -->

----

## Why Java?

Java hits the sweet spot for learning:

* **Labels on every box** — every box is clearly labeled with what goes inside, so nothing gets mixed up <!-- .element: class="fragment" -->
* **Auto-cleanup** — Java tidies up for you, so you focus on your program <!-- .element: class="fragment" -->
* **Easy setup** — install it and start coding right away <!-- .element: class="fragment" -->
* **Top 4 worldwide** — used by tens of millions of programmers <!-- .element: class="fragment" -->

> Java teaches us to think precisely — exactly what we need!

----

## Your First Java Program

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

This is the simplest Java program.

> It prints the words `Hello, World!` on the screen.

----

## What Does All That Code Mean?

Think of it like a **house**:

```text
public class HelloWorld {          ← The house (gives the program a name)

    public static void main(...) { ← The front door (where it starts)

        ...                        ← What happens inside

    }
}
```

* `class` = the **house** — every program needs one <!-- .element: class="fragment" -->
* `main` = the **front door** — the computer always enters here first <!-- .element: class="fragment" -->
* `System.out.println(...)` = an **action** — it prints text to the screen <!-- .element: class="fragment" -->

> For now, just remember: code lives inside `main`, which lives inside a `class`.

----

<!-- .slide: class="center" -->

> We now have a way to talk to computers — let's learn the vocabulary!
