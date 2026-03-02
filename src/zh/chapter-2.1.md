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

就像人类有中文、英文、法文一样，编程也有很多语言：

* **Python** ── 最流行，写起来最简洁 <!-- .element: class="fragment" -->
* **C / C++** ── 速度最快，很多游戏用它写的 <!-- .element: class="fragment" -->
* **Java** ── 全世界数千万程序员在用 <!-- .element: class="fragment" -->

> 这么多选择！我们应该先学哪个？

----

## 为什么不选 Python？

Python 最流行 ── 但它有些地方对初学者不太友好：

* **看不见的陷阱** ── 多一个空格或少一个空格，程序就出错了，但你很难看出哪里不对 <!-- .element: class="fragment" -->
* **盒子不贴标签** ── 你不用说盒子里放的是什么类型的东西，但这样容易搞混 <!-- .element: class="fragment" -->

> 流行不一定最适合学习。 <!-- .element: class="fragment" -->

----

## 为什么不选 C / C++？

C 和 C++ 速度快、功能强 ── 但它们对新手不太友好：

* **得自己打扫房间** ── 程序用完的东西必须自己清理，忘了就会出大问题 <!-- .element: class="fragment" -->
* **准备工作太多** ── 还没写第一行代码，就要装一大堆工具 <!-- .element: class="fragment" -->

> 太强大也是一种负担 ── 作为第一门语言太复杂了。 <!-- .element: class="fragment" -->

----

## 为什么选 Java？

Java 恰好是学习的最佳平衡点：

* **盒子有标签** ── 每个盒子都清楚标明装的是什么，不会搞混 <!-- .element: class="fragment" -->
* **自动打扫** ── Java 会自己清理用完的东西，让你专心写程序 <!-- .element: class="fragment" -->
* **准备简单** ── 装好就能开始写代码 <!-- .element: class="fragment" -->
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
