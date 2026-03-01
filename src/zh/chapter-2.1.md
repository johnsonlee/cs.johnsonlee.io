<!-- .slide: class="center" -->

## 2.1. 什么是编程语言？

*从人类语言到计算机语言*

----

## 我们如何交流？

每天，我们都在和别人说话。

我们使用 **语言** ── 中文、英语、西班牙语……

> 语言让我们可以分享想法、提出问题、发出指令。

----

## 我们能跟计算机说话吗？

其实 ── 我们可以跟 **AI** 说话！

我们可以让 AI：

* "给我画一只猫！" → 它真的画了！ <!-- .element: class="fragment" -->
* "写一个故事！" → 它真的写了！ <!-- .element: class="fragment" -->
* "帮我做数学题！" → 它真的帮了！ <!-- .element: class="fragment" -->

> 但这里有个秘密…… <!-- .element: class="fragment" -->

----

## AI 也是一个程序

AI 好像能听懂人类的语言。

但 AI 本身是一个 **程序** ── 由程序员用编程语言写出来的。

* 程序员编写了数百万行代码 <!-- .element: class="fragment" -->
* 他们用海量数据训练了 AI <!-- .element: class="fragment" -->
* 这一切都是用编程语言构建的 <!-- .element: class="fragment" -->

> 没有编程语言，就不会有 AI。

----

## 计算机 vs AI

| | 计算机 | AI |
|:---|:-------|:---|
| 是什么 | 机器本身 | 运行在机器上的程序 |
| 能理解什么 | 只懂 0 和 1 | 人类语言（因为程序员教会了它） |
| 谁造的 | 工程师 | 程序员，用编程语言 |

> 要真正理解这一切是怎么运作的，我们需要学习那门"造万物"的语言 ── **编程语言**。

----

## 为什么不能直接用人类语言？

人类的语言是 **模糊的**。

* "我在山上用望远镜看到了一个人" ── 谁拿着望远镜？ <!-- .element: class="fragment" -->
* "好冷啊" ── 是要关窗？开暖气？还是拿件外套？ <!-- .element: class="fragment" -->

> 人类可以根据上下文猜测。计算机不行。 <!-- .element: class="fragment" -->

----

## 计算机需要什么

计算机需要的指令必须是：

* **精确的** ── 没有歧义 <!-- .element: class="fragment" -->
* **一步一步的** ── 一次只做一件事 <!-- .element: class="fragment" -->
* **遵循严格规则的** ── 像语法，但更严格 <!-- .element: class="fragment" -->

> 这就是 **编程语言** 提供的东西。

----

<!-- .slide: class="center" -->

> 编程语言是一种编写精确指令的方式，计算机可以照着执行 ── 不需要猜测。

----

## 有很多编程语言

[TIOBE 指数](https://www.tiobe.com/tiobe-index/) 排列了最流行的编程语言：

| 排名 | 语言 | 份额 |
|:----:|:-----|:----:|
| 1 | Python | 21.81% |
| 2 | C | 11.05% |
| 3 | C++ | 8.55% |
| 4 | Java | 8.12% |

> 这么多选择！我们应该先学哪个？

----

## 为什么不选 Python？

Python 人气排名第一 ── 但它有些特性对初学者并不友好：

* **看不见的规则** ── 缩进（空格）会改变代码的含义；多一个或少一个空格，程序就出错了 <!-- .element: class="fragment" -->
* **没有类型标签** ── 你不需要声明变量的类型，这让初学者很难理解盒子里到底装了什么 <!-- .element: class="fragment" -->

> 流行不一定意味着最适合学习。 <!-- .element: class="fragment" -->

----

## 为什么不选 C / C++？

C 和 C++ 速度快、功能强 ── 但它们可能让人望而却步：

* **手动管理内存** ── 你必须自己分配和释放内存；一个小错误就会让程序崩溃 <!-- .element: class="fragment" -->
* **工具链复杂** ── 编译器、链接器、头文件……还没写第一行代码，就要搞定一大堆东西 <!-- .element: class="fragment" -->

> 强大是有代价的 ── 作为第一门语言，太复杂了。 <!-- .element: class="fragment" -->

----

## 为什么选 Java？

Java 恰好是学习的最佳平衡点：

* **显式类型** ── 每个变量都有清晰的类型标签，你始终知道盒子里装的是什么 <!-- .element: class="fragment" -->
* **不用手动管理内存** ── Java 会自动清理，让你专注于逻辑 <!-- .element: class="fragment" -->
* **工具链简单** ── 只需 `javac` 和 `java` 两个命令，就能编写和运行代码 <!-- .element: class="fragment" -->
* **全球前 4** ── 全世界有数千万程序员在使用 <!-- .element: class="fragment" -->

> Java 教会我们精确思考 ── 这正是我们所需要的！

----

## 你的第一个 Java 程序

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

这是最简单的 Java 程序。

> 它会在屏幕上打印出 `Hello, World!` 这几个字。

----

## 这些代码是什么意思？

把它想象成一栋 **房子**：

```text
public class HelloWorld {          ← 房子（给程序起个名字）

    public static void main(...) { ← 大门（程序从这里开始）

        ...                        ← 屋子里发生的事

    }
}
```

* `class` = **房子** ── 每个程序都需要一个 <!-- .element: class="fragment" -->
* `main` = **大门** ── 计算机总是从这里进入 <!-- .element: class="fragment" -->
* `System.out.println(...)` = 一个 **动作** ── 在屏幕上打印文字 <!-- .element: class="fragment" -->

> 现在只需记住：代码放在 `main` 里，`main` 放在 `class` 里。

----

<!-- .slide: class="center" -->

> 我们现在有了和计算机对话的方式 ── 接下来学习它的"词汇"吧！
