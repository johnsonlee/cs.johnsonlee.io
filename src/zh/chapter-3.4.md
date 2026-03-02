<!-- .slide: class="center" -->

## 3.4. 搜索

*大海捞针*

----

## 猜数字游戏

我们来玩一个游戏：

* 我在 1 到 100 之间选一个秘密数字 <!-- .element: class="fragment" -->
* 你猜一个数字 <!-- .element: class="fragment" -->
* 我告诉你 **“大了”** 还是 **“小了”** <!-- .element: class="fragment" -->

> 你需要猜几次才能找到秘密数字？

----

## 策略一：一个一个猜

你可以这样猜：1, 2, 3, 4, 5, ...

* 如果秘密数字是 1 ── **猜 1 次** <!-- .element: class="fragment" -->
* 如果秘密数字是 50 ── **猜 50 次** <!-- .element: class="fragment" -->
* 如果秘密数字是 100 ── **猜 100 次** <!-- .element: class="fragment" -->

> 这叫做 **线性搜索** ── 一个一个地检查每个可能的答案。

----

## 线性搜索的 Java 代码

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

> 逐个遍历每个元素，如果匹配目标，就找到了！

----

## 策略二：每次猜中间

换一种方法 ── 每次都猜剩余范围的 **中间值** ：

* 范围 1–100 ── 猜 **50** ── “大了！” <!-- .element: class="fragment" -->
* 范围 1–49 ── 猜 **25** ── “小了！” <!-- .element: class="fragment" -->
* 范围 26–49 ── 猜 **37** ── “小了！” <!-- .element: class="fragment" -->
* 范围 38–49 ── 猜 **43** ── “大了！” <!-- .element: class="fragment" -->
* 范围 38–42 ── 猜 **40** ── “对了！” <!-- .element: class="fragment" -->

> 1 到 100 之间的数字，只需 **5 次** 就猜到了！

----

## 为什么这么快？

每次猜测都会把范围 **砍掉一半** ：

```text
100 → 50 → 25 → 12 → 6 → 3 → 1
```

最多猜 7 次，就能找到 1 到 100 之间的任何数字。

> 这个策略叫做 **二分搜索** ── “二分”就是把范围分成 **两半** 。

----

## 二分搜索：一步步演示

在一个有序数组中搜索 **23** ：

```text
[2, 5, 8, 12, 16, 23, 38, 56, 72, 91]
```

| 步骤 | 搜索范围 | 中间值 | 结果 |
|:----:|:---------|:------:|:-----|
| 1 | 索引 0–9 | 16 | 太小 ── 搜索右半部分 |
| 2 | 索引 5–9 | 56 | 太大 ── 搜索左半部分 |
| 3 | 索引 5–6 | 23 | **找到了！** |

> 10 个元素只需要 3 步就搜完了！

----

## 二分搜索的 Java 代码

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
                break; // 停止搜索
            } else if (numbers[mid] < target) {
                low = mid + 1;
            } else {
                high = mid - 1;
            }
        }
    }
}
```

输出：`Found at index 5`

----

## 代码解析

* `low` 和 `high` 标记当前的搜索范围 <!-- .element: class="fragment" -->
* `mid = (low + high) / 2` 找到中间索引 <!-- .element: class="fragment" -->
* 如果 `numbers[mid]` 太小 ── 把 `low` 往上移 <!-- .element: class="fragment" -->
* 如果 `numbers[mid]` 太大 ── 把 `high` 往下移 <!-- .element: class="fragment" -->
* `break` 的意思是“停止循环” ── 我们已经找到目标了！ <!-- .element: class="fragment" -->

> 每一步都把范围砍掉一半 ── 所以速度极快！

----

## 线性搜索 vs 二分搜索

| 数据量 | 线性搜索 | 二分搜索 |
|-------:|:--------:|:--------:|
| 10 | 最多 10 次 | 最多 4 次 |
| 100 | 最多 100 次 | 最多 7 次 |
| 1,000 | 最多 1,000 次 | 最多 10 次 |
| 1,000,000 | 最多 1,000,000 次 | 最多 20 次 |

> 二分搜索快得惊人 ── 但有一个前提条件……

----

## 有一个前提条件

二分搜索只能在 **有序数据** 上使用！

* 如果数组没有排序，跳到中间也没有意义 <!-- .element: class="fragment" -->
* 线性搜索可以在 **任何** 数组上使用 ── 无论是否有序 <!-- .element: class="fragment" -->

> 那我们怎么给数据排序呢？这就是下一个话题！

----

<!-- .slide: class="center" -->

> 在学习排序之前，先来认识一个强大的技巧 ── **递归** ！
