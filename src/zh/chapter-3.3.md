<!-- .slide: class="center" -->

## 3.3. 什么是算法？

*同一个问题，更聪明的解法*

----

## 不止一种方法

在第 2 章中，我们学会了给计算机写一步步的指令。

但如果同一个问题有 **不止一种** 解法呢？

* 哪种更快？ <!-- .element: class="fragment" -->
* 哪种更聪明？ <!-- .element: class="fragment" -->
* 这有关系吗？ <!-- .element: class="fragment" -->

> 让我们用一个简单的挑战来一探究竟！

----

## 一个简单的挑战

假设你有一份 20 个人的名单，需要找到“Emma”：

```text
Alex, Ben, Chris, Dana, Emma, Fay, Grace, ...
```

你会怎么找她？

> 方法不止一种 ── 有些方法比其他的 **快得多** ！

----

## 策略一：逐个检查

从头开始，一个一个地看：

1. Alex？不是。 <!-- .element: class="fragment" -->
2. Ben？不是。 <!-- .element: class="fragment" -->
3. Chris？不是。 <!-- .element: class="fragment" -->
4. Dana？不是。 <!-- .element: class="fragment" -->
5. Emma？**找到了！** <!-- .element: class="fragment" -->

> 这行得通！但如果 Emma 是 1,000 个名字中的最后一个呢？

----

## 策略二：跳到中间

如果名单是按 **字母顺序** 排列的，可以试试更聪明的方法：

1. 看中间的名字 ── “Kate” <!-- .element: class="fragment" -->
2. Emma 在 Kate 前面 ── 忽略后半部分 <!-- .element: class="fragment" -->
3. 看剩余部分的中间 ── “Chris” <!-- .element: class="fragment" -->
4. Emma 在 Chris 后面 ── 忽略 Chris 之前的名字 <!-- .element: class="fragment" -->
5. 再看中间 ── **Emma！找到了！** <!-- .element: class="fragment" -->

> 我们只看了 3 个名字，而不是 5 个！

----

## 同一个问题，不同的速度

| 策略 | 怎么做 | 检查次数（20 个名字） |
|:-----|:-------|:--------------------:|
| 逐个检查 | 一个一个看 | 最多 20 次 |
| 跳到中间 | 每次砍掉一半 | 大约 5 次 |

如果是 1,000,000 个名字呢？

* 逐个检查：最多 **1,000,000** 次 <!-- .element: class="fragment" -->
* 跳到中间：只需要大约 **20** 次！ <!-- .element: class="fragment" -->

----

## 什么是算法？

这些解题策略有一个专门的名字 ── 叫做 **算法** 。

**算法** 就是一个解决问题的分步计划。

* 同一个问题可以有 **很多种** 算法 <!-- .element: class="fragment" -->
* 有些算法比其他的 **快得多** <!-- .element: class="fragment" -->
* 选择正确的算法非常重要！ <!-- .element: class="fragment" -->

> 算法不仅仅是按步骤做事 ── 而是找到 **最聪明** 的步骤。

----

## 计算机科学的核心

计算机科学不仅仅是 **解决** 问题。

更重要的是 **高效地** 解决问题。

* **方法** 教我们如何 **组织** 步骤 <!-- .element: class="fragment" -->
* **算法** 教我们如何 **选择** 最优的步骤 <!-- .element: class="fragment" -->

> 这就是计算机科学令人兴奋的地方 ── 找到更 **聪明** 的解决方案！

----

<!-- .slide: class="center" -->

> 现在让我们来学习真正的算法 ── 从 **搜索** 开始。
