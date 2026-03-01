<!-- .slide: class="center" -->

## 2.2. 变量与运算

*教计算机记忆和计算*

----

## 健忘的计算机

上一节，我们让计算机打印了"Hello, World!"。

它做到了 ── 但随后就全忘了。

> 如果我们想让它 **记住** 一些东西呢？

----

## 变量 = 贴了标签的盒子

**变量** 就像一个贴了标签的盒子。

```text
  +-------+
  |  10   |    ← 盒子里的值
  +-------+
    age        ← 标签（名字）
```

* 你给盒子一个 **名字**（标签）
* 你把一个 **值** 放进去

> 在 Java 中，你还需要说明盒子里放什么 **类型** 的东西。

----

## 类型 ── 盒子里放什么？

Java 需要在存放东西 **之前** 知道类型：

| 类型 | 存放什么 | 示例 |
|:-----|:---------|:-----|
| `int` | 整数 | `10`、`-3`、`0` |
| `double` | 小数 | `3.14`、`-0.5` |
| `String` | 文本 | `"Hello"`、`"Alice"` |
| `boolean` | 真或假 | `true`、`false` |

> 把类型想象成盒子的 **形状** ── 只有匹配的东西才能放进去。

----

## 声明和赋值

要创建一个变量，我们先 **声明** 它：

```java
int age;           // 创建一个标签为"age"的盒子，用来装整数
age = 10;          // 把值 10 放进去
```

或者一步到位：

```java
int age = 10;      // 创建盒子并把 10 放进去
```

----

## 更多示例

```java
double height = 1.45;
String name = "Alice";
boolean isHappy = true;
```

每个变量有三样东西：

* 一个 **类型** ── 什么种类的值（`int`、`double`、`String`、`boolean`） <!-- .element: class="fragment" -->
* 一个 **名字** ── 我们怎么称呼它（`height`、`name`、`isHappy`） <!-- .element: class="fragment" -->
* 一个 **值** ── 里面存了什么（`1.45`、`"Alice"`、`true`） <!-- .element: class="fragment" -->

----

## 算术运算 ── 计算器

Java 可以做数学运算，就像计算器一样：

| 运算符 | 含义 | 示例 | 结果 |
|:------:|:-----|:-----|:-----|
| `+` | 加 | `3 + 5` | `8` |
| `-` | 减 | `10 - 4` | `6` |
| `*` | 乘 | `6 * 7` | `42` |
| `/` | 除 | `15 / 3` | `5` |
| `%` | 取余 | `10 % 3` | `1` |

----

## 使用算术运算

```java
int a = 10;
int b = 3;

int sum = a + b;       // 13
int diff = a - b;      // 7
int product = a * b;   // 30
int quotient = a / b;  // 3（整数除法！）
int remainder = a % b; // 1
```

> 注意：`10 / 3` 的结果是 `3`，不是 `3.33`！整数除法会丢掉小数部分。

----

## 比较运算 ── 真还是假？

我们还可以 **比较** 两个值：

| 运算符 | 含义 | 示例 | 结果 |
|:------:|:-----|:-----|:-----|
| `>` | 大于 | `5 > 3` | `true` |
| `<` | 小于 | `5 < 3` | `false` |
| `>=` | 大于等于 | `5 >= 5` | `true` |
| `<=` | 小于等于 | `3 <= 5` | `true` |
| `==` | 等于 | `5 == 5` | `true` |
| `!=` | 不等于 | `5 != 3` | `true` |

> 比较的结果永远是一个 `boolean` ── `true` 或 `false`。

----

## 注意：`=` 和 `==`

它们长得很像，但意思完全不同！

* `=` 的意思是 **赋值** ── 把值放进盒子 <!-- .element: class="fragment" -->
* `==` 的意思是 **比较** ── 它们相等吗？ <!-- .element: class="fragment" -->

```java
int x = 5;      // 赋值：把 5 放进 x
x == 5           // 比较：x 等于 5 吗？ → true
```
<!-- .element: class="fragment" -->

> 这是初学者最容易犯的错误 ── 别搞混了！

----

## 字符串拼接

`+` 运算符也可以用于文本 ── 它会把字符串 **连接** 在一起：

```java
String first = "Hello";
String second = "World";
String greeting = first + ", " + second + "!";
// greeting 的值是 "Hello, World!"
```

你甚至可以混合字符串和数字：

```java
String message = "I am " + 10 + " years old.";
// message 的值是 "I am 10 years old."
```

----

## 把所有知识用起来

```java
public class MyCalculator {
    public static void main(String[] args) {
        int apples = 12;
        int friends = 4;
        int each = apples / friends;
        int leftover = apples % friends;
        System.out.println("Each friend gets " + each + " apples.");
        System.out.println("Leftover: " + leftover);
    }
}
```

输出：

```text
Each friend gets 3 apples.
Leftover: 0
```

> 现在计算机可以 **记忆** 和 **计算** 了 ── 接下来教它做 **决定**！
