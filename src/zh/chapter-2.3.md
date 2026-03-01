<!-- .slide: class="center" -->

## 2.3. 做决定和重复

*教计算机选择和坚持*

----

## 日常生活中的选择

每天，你都在做决定：

* 如果天晴 → 戴墨镜 <!-- .element: class="fragment" -->
* 如果下雨 → 带雨伞 <!-- .element: class="fragment" -->
* 如果天冷 → 穿外套 <!-- .element: class="fragment" -->

> 你先检查一个 **条件**，然后根据结果 **行动**。

----

## Java 中的 `if`

Java 也用同样的方式做决定：

```java
int temperature = 35;

if (temperature > 30) {
    System.out.println("It's hot! Stay hydrated.");
}
```

* **条件** 放在 `( )` 里
* **动作** 放在 `{ }` 里

> `{ }` 里的代码只有在条件为 `true` 时才会运行。

----

## `if / else` ── 两个选择

如果有两个选项呢？

```java
int temperature = 15;

if (temperature > 30) {
    System.out.println("It's hot!");
} else {
    System.out.println("It's not too hot.");
}
```

* `if` ── 条件为 `true` 时执行 <!-- .element: class="fragment" -->
* `else` ── 条件为 `false` 时执行 <!-- .element: class="fragment" -->

> 就像岔路口 ── 要么走这边，要么走那边，不能两边都走。

----

## `else if` ── 多个选择

如果有两个以上的选项呢？

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

> Java 从 **上到下** 检查每个条件，执行 **第一个** 匹配的。

----

## 组合条件

有时候一个条件不够用：

* `&&` 表示 **并且** ── 两个都为真才行 <!-- .element: class="fragment" -->
* `||` 表示 **或者** ── 至少一个为真就行 <!-- .element: class="fragment" -->

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

### 现在计算机可以做决定了。

### 但如果要重复做一件事呢？

----

## 重复的问题

想象你要打印"Hello!"5 次：

```java
System.out.println("Hello!");
System.out.println("Hello!");
System.out.println("Hello!");
System.out.println("Hello!");
System.out.println("Hello!");
```

这样可以……但如果是 100 次呢？1000 次呢？

> 一定有更好的办法！

----

## `for` 循环 ── 一台计数机器

```java
for (int i = 0; i < 5; i++) {
    System.out.println("Hello!");
}
```

这会精确地打印"Hello!"5 次。

让我们拆解一下：

| 部分 | 含义 |
|:-----|:-----|
| `int i = 0` | 从 0 开始计数 |
| `i < 5` | 当 `i` 小于 5 时继续 |
| `i++` | 每轮结束后，`i` 加 1 |

> 循环数的是：0、1、2、3、4 ── 一共 5 轮！

----

## 看看计数器

```java
for (int i = 0; i < 5; i++) {
    System.out.println("Round " + i);
}
```

输出：

```text
Round 0
Round 1
Round 2
Round 3
Round 4
```

> 注意：我们从 **0** 开始，不是从 1。这是大多数编程语言的惯例！

----

## `while` 循环 ── 重复直到结束

`while` 循环会在条件为 `true` 时一直执行：

```java
int count = 1;

while (count <= 5) {
    System.out.println("Count: " + count);
    count++;
}
```

输出：

```text
Count: 1
Count: 2
Count: 3
Count: 4
Count: 5
```

> `for` 适合你知道 **执行多少次** 的情况。`while` 适合你不确定的时候。

----

## 循环 + 条件 = 强大

让我们数一数 1 到 10 之间有多少个偶数：

```java
int evenCount = 0;

for (int i = 1; i <= 10; i++) {
    if (i % 2 == 0) {
        evenCount++;
    }
}

System.out.println("Even numbers: " + evenCount);
```

输出：`Even numbers: 5`

> 循环和条件 **配合** 在一起，就能解决真正的问题！

----

<!-- .slide: class="center" -->

> 计算机永远不会累，永远不会烦。
>
> 它可以重复十亿次，却不会抱怨一声。
>
> 这就是循环的力量。
