<!-- .slide: class="center" -->

## 3.5. 递归

*自己调用自己的方法*

----

## 俄罗斯套娃

想象一组俄罗斯套娃：

* 打开大娃娃 ── 里面有一个 **更小的** 娃娃 <!-- .element: class="fragment" -->
* 再打开 ── 里面还有一个 **更更小的** 娃娃 <!-- .element: class="fragment" -->
* 继续打开……直到碰到 **最小的** 那个，打不开了 <!-- .element: class="fragment" -->
* 然后把它们一个套一个地装回去 <!-- .element: class="fragment" -->

> 这就是递归的工作方式 ── 把大问题拆成越来越小的版本，直到碰到最小的那个！

----

## 什么是递归？

**递归** 就是一个方法 **调用自己** ，去解决同一个问题的更小版本。

每个递归方法都需要两个部分：

* **基本情况（终止条件）** ── 什么时候 **停下来** （最小的那个娃娃） <!-- .element: class="fragment" -->
* **递归情况** ── 用 **更小的** 问题调用自己（打开下一个娃娃） <!-- .element: class="fragment" -->

> 如果没有终止条件，方法就会一直调用自己 ── 就像一个无限循环！

----

## 倒计时：思路

让我们从 5 倒数到 1：

* 从 5 倒数：先打印 5，然后从 4 倒数 <!-- .element: class="fragment" -->
* 从 4 倒数：先打印 4，然后从 3 倒数 <!-- .element: class="fragment" -->
* 从 3 倒数：先打印 3，然后从 2 倒数 <!-- .element: class="fragment" -->
* …… <!-- .element: class="fragment" -->
* 从 0 倒数：**停！** （基本情况） <!-- .element: class="fragment" -->

> 每一步都是同一个问题，只是数字变小了！

----

## 倒计时的 Java 代码

```java
public class Countdown {
    public static void countdown(int n) {
        if (n == 0) {
            System.out.println("Go!");
            return; // 基本情况：到这里就停
        }
        System.out.println(n);
        countdown(n - 1); // 递归情况：问题变小了
    }

    public static void main(String[] args) {
        countdown(5);
    }
}
```

输出：`5  4  3  2  1  Go!`

----

## 追踪调用过程

当我们调用 `countdown(5)` 时，会发生什么？

```text
countdown(5)  → 打印 5，然后调用……
  countdown(4)  → 打印 4，然后调用……
    countdown(3)  → 打印 3，然后调用……
      countdown(2)  → 打印 2，然后调用……
        countdown(1)  → 打印 1，然后调用……
          countdown(0)  → 打印 "Go!" 然后停下来！
```

> 每次调用都要等下一次结束 ── 就像一个接一个地打开套娃。

----

## 阶乘：一个经典的例子

**阶乘** 就是把一个数和它下面的所有数相乘：

* $5! = 5 \times 4 \times 3 \times 2 \times 1 = 120$

我们可以用递归来表达：

* $5! = 5 \times 4!$ <!-- .element: class="fragment" -->
* $4! = 4 \times 3!$ <!-- .element: class="fragment" -->
* $3! = 3 \times 2!$ <!-- .element: class="fragment" -->
* $2! = 2 \times 1!$ <!-- .element: class="fragment" -->
* $1! = 1$（基本情况！） <!-- .element: class="fragment" -->

> 每个阶乘都用一个 **更小的** 阶乘来定义 ── 这就是递归！

----

## 阶乘的 Java 代码

```java
public class Factorial {
    public static int factorial(int n) {
        if (n == 1) {
            return 1; // 基本情况
        }
        return n * factorial(n - 1); // 递归情况
    }

    public static void main(String[] args) {
        int result = factorial(5);
        System.out.println("5! = " + result);
    }
}
```

输出：`5! = 120`

----

## 追踪阶乘的调用过程

```text
factorial(5)
  = 5 * factorial(4)
  = 5 * 4 * factorial(3)
  = 5 * 4 * 3 * factorial(2)
  = 5 * 4 * 3 * 2 * factorial(1)
  = 5 * 4 * 3 * 2 * 1
  = 120
```

> 方法不断调用自己，直到碰到基本情况，然后把所有结果乘回来 ── 就像把套娃一个个装回去！

----

## 为什么递归很重要？

有些问题天生就是 **递归的** ── 它们包含自身的更小副本：

* **树** 有分支，每个分支本身也是一棵树 <!-- .element: class="fragment" -->
* **文件夹** 里面有文件，还有其他文件夹 <!-- .element: class="fragment" -->
* **二分搜索** 把数据分成两半 ── 每一半都是同一个问题，只是更小了 <!-- .element: class="fragment" -->

> 预告：**归并排序** 和 **快速排序** 都用递归来"分而治之"！

----

## 递归 vs 循环

每个递归都 **可以** 写成循环 ── 反过来也一样。下面是阶乘的两种写法：

| 递归 | 循环 |
|:-----|:-----|
| `factorial(5)` 调用 `factorial(4)` 调用 `factorial(3)`…… | `result = 1; for i = 1 to 5: result = result * i` |
| 把问题拆成 **更小的** 子问题 | 一步一步地 **累积** 结果 |
| 有时候更容易 **理解** | 有时候 **运行效率** 更高 |

> 有些问题（比如树和文件夹）用递归想起来容易得多。哪种方式让代码更清楚，就用哪种！

----

<!-- .slide: class="center" -->

> 学会了递归，我们就可以挑战 **排序** 了 ── 接下来见识几种真正聪明的算法！
