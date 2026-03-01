<!-- .slide: class="center" -->

## 2.4. 方法与数组

*可复用的技巧和一排盒子*

----

## 每天的例行工作

想象你要教一个机器人做三明治：

1. 拿两片面包 <!-- .element: class="fragment" -->
2. 涂花生酱 <!-- .element: class="fragment" -->
3. 加果酱 <!-- .element: class="fragment" -->
4. 把两片合起来 <!-- .element: class="fragment" -->

> 如果机器人每天都做三明治，我们需要每次都重复这 4 步吗？

----

## 方法 ── 给例行工作起个名字

我们可以给这套流程起一个 **名字**：`makeSandwich`。

现在只需说：`makeSandwich()` ── 机器人就知道该做什么了！

```java
public static void makeSandwich() {
    System.out.println("1. Get bread");
    System.out.println("2. Spread peanut butter");
    System.out.println("3. Add jelly");
    System.out.println("4. Put slices together");
}
```

> **方法** 就是一个有名字的、可以重复使用的指令块。

----

## 调用方法

定义方法就像写菜谱。

**调用** 方法就像照着菜谱做菜：

```java
public static void main(String[] args) {
    makeSandwich();    // 做一个三明治
    makeSandwich();    // 再做一个！
}
```

> 定义一次，想用多少次就用多少次。

----

## 参数 ── 定制你的流程

如果我们想和不同的人打招呼呢？

```java
public static void greet(String name) {
    System.out.println("Hello, " + name + "!");
}

public static void main(String[] args) {
    greet("Alice");    // Hello, Alice!
    greet("Bob");      // Hello, Bob!
}
```

* `name` 是一个 **参数** ── 调用方法时才给它赋值的变量

> 参数让方法变得灵活 ── 同一个菜谱，不同的食材！

----

## 返回值 ── 拿回答案

有时候我们希望方法能 **返回** 一个结果：

```java
public static int add(int a, int b) {
    return a + b;
}

public static void main(String[] args) {
    int result = add(3, 5);
    System.out.println(result);    // 8
}
```

* 方法名前面的 `int` 表示它会返回一个 `int` <!-- .element: class="fragment" -->
* `void` 表示"不返回任何东西" <!-- .element: class="fragment" -->
* `return` 把答案送回给调用者 <!-- .element: class="fragment" -->

----

<!-- .slide: class="center" -->

### 方法让我们可以组织和复用代码。

### 但如果要组织 **数据** 呢？

----

## 多个值的问题

如果一位老师有 5 个学生，想记录他们的分数：

```java
int score0 = 90;
int score1 = 85;
int score2 = 78;
int score3 = 92;
int score4 = 88;
```

5 个学生还行……但 30 个呢？300 个呢？

> 我们需要一种方式来把 **同类型的多个值** 存在一起。

----

## 数组 ── 一排编号的盒子

**数组** 是一排编好号的盒子：

```text
 index:   0     1     2     3     4
        +-----+-----+-----+-----+-----+
        | 90  | 85  | 78  | 92  | 88  |
        +-----+-----+-----+-----+-----+
```

在 Java 中：

```java
int[] scores = {90, 85, 78, 92, 88};
```

> 每个盒子有一个 **索引**（编号），从 **0** 开始。

----

## 访问数组元素

用 `[ ]` 中的索引来读取或修改某个盒子：

```java
int[] scores = {90, 85, 78, 92, 88};

System.out.println(scores[0]);    // 90（第一个元素）
System.out.println(scores[2]);    // 78（第三个元素）
System.out.println(scores[4]);    // 88（第五个元素）

scores[1] = 95;                   // 修改第二个元素
System.out.println(scores[1]);    // 95
```

> 记住：索引从 **0** 开始，所以第 1 个元素是 `scores[0]`！

----

## 用循环遍历数组

数组真正的威力在于和 **循环** 配合使用：

```java
int[] scores = {90, 85, 78, 92, 88};

for (int i = 0; i < scores.length; i++) {
    System.out.println("Student " + i + ": " + scores[i]);
}
```

输出：

```text
Student 0: 90
Student 1: 85
Student 2: 78
Student 3: 92
Student 4: 88
```

> `scores.length` 告诉我们元素的个数 ── 不用自己记了！

----

## 第 2 章总结

我们已经走了很远：

* **第 1 章** ── 计算机能理解什么：比特、数字、文字 <!-- .element: class="fragment" -->
* **第 2 章** ── 我们怎么和计算机交流：变量、条件、循环、方法、数组 <!-- .element: class="fragment" -->
* **第 3 章**（下一章）── 如何组织数据、高效解决问题 <!-- .element: class="fragment" -->

> 你现在已经拥有了编写真正程序的所有工具。
>
> 接下来，我们将学习 **聪明地** 使用它们 ── 这就是算法的意义所在！
