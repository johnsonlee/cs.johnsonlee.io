<!-- .slide: class="center" -->

## 3.1. 栈与队列

*为不同任务选择合适的容器*

----

## 真的需要位置号码吗？

数组就像一排编号的盒子 ── 按位置取值非常方便。

但想一想 ── 你 **真的** 每次都需要知道位置吗？

* 叠盘子时，你会说"请给我第 3 个盘子"吗？你只拿 **最上面** 的！ <!-- .element: class="fragment" -->
* 排队打饭时，你会数"第 5 个人出列"吗？你只看 **最前面** 的！ <!-- .element: class="fragment" -->

> 有时候，不关心位置号码反而更简单。让我们看看这意味着什么。

----

## 如果随便抽盘子呢？

食堂有一摞盘子。如果任何人都能从 **中间** 抽呢？

* 上面的盘子可能全倒了 <!-- .element: class="fragment" -->
* 谁也不知道下一个该拿哪个 <!-- .element: class="fragment" -->

所以规则很简单：**只能从最上面拿** 。 <!-- .element: class="fragment" -->

> 这个限制不是麻烦 ── 它是 **保护** 。计算机里的 **栈** 就是这个规则：**L**ast **I**n, **F**irst **O**ut（后进先出）。

----

## 栈的操作

栈有两个操作：

* **Push（压入）** ── 把东西放到最上面
* **Pop（弹出）** ── 从最上面取走东西

![栈的操作](src/zh/images/stack-ops.svg) <!-- .element: style="width: 70%" -->

> 想想”撤销”按钮 ── 它总是先撤销 **最后** 一步操作！

----

## 用代码搭一个栈

我们想用数组来实现栈 ── 但这次不能一开始就放好值，得先准备 **空盒子** ，再一个一个地压入：

```java
// 之前：直接放好值
int[] scores = {90, 85, 78, 92, 88};

// 现在：先准备空盒子
int[] stack = new int[10]; // 10 个空位，等着被压入
```

> `new int[10]` 创建一个有 10 个位置的数组，初始值都是 0。

----

## 用 Java 实现栈

```java
public class StackDemo {
    public static void main(String[] args) {
        int[] stack = new int[10]; // 10 个空盒子
        int top = 0;

        stack[top] = 42; top++;    // 压入 42
        stack[top] = 17; top++;    // 压入 17
        stack[top] = 8;  top++;    // 压入 8

        top--;                      // 弹出
        System.out.println(stack[top]); // 8
        top--;                      // 弹出
        System.out.println(stack[top]); // 17
    }
}
```

> `top` 记录下一个空位的位置。压入时增大，弹出时减小。

----

## 如果允许插队呢？

现在想象食堂排队。如果没有规则，谁都可以挤到最前面 ──

* 先来的同学永远打不到饭 <!-- .element: class="fragment" -->
* 大家都往前挤，乱成一团 <!-- .element: class="fragment" -->

所以规则很简单：**先来的先走** ，新来的排到最后面。 <!-- .element: class="fragment" -->

> 这个规则叫 **FIFO** ── **F**irst **I**n, **F**irst **O**ut（先进先出）。计算机里的 **队列** 就遵守这个规则。

----

## 队列的操作

队列有两个操作：

* **Enqueue（入队）** ── 排到队尾
* **Dequeue（出队）** ── 从队首离开

![队列的操作](src/zh/images/queue-ops.svg) <!-- .element: style="width: 45%" -->

> 想想食堂排队 ── 先排队的同学先打到饭！

----

## 用 Java 实现队列

```java
public class QueueDemo {
    public static void main(String[] args) {
        String[] queue = new String[10]; // 10 个空盒子
        int front = 0;
        int back = 0;

        queue[back] = "Alice";   back++;  // 入队
        queue[back] = "Bob";     back++;  // 入队
        queue[back] = "Charlie"; back++;  // 入队

        System.out.println(queue[front]); // Alice
        front++;                           // 出队
        System.out.println(queue[front]); // Bob
        front++;                           // 出队
    }
}
```

> `front` 和 `back` 分别记录队首和队尾的位置。

----

## 你会怎么选？

遇到下面的情况，你会用哪种容器？

* 浏览器的”后退”按钮 ── 总是回到 **上一个** 页面？ <!-- .element: class=”fragment” -->
* 食堂排队 ── **先来的** 同学先打饭？ <!-- .element: class=”fragment” -->
* 学生成绩单 ── 按学号 **查找** 某个同学的分数？ <!-- .element: class=”fragment” -->

> 栈、队列、数组 ── 没有”最好”的，只有 **最合适** 的！

----

<!-- .slide: class="center" -->

> 栈和队列都是一个接一个地添加元素。但有时数据是分叉的 ── 就像一棵家谱树。接下来认识 **树** ！
