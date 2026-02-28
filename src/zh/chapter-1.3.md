<!-- .slide: class="center" -->

## 1.3. 计算机如何表示颜色？

*从光到像素*

----

## 我们有的颜色

![Crayons](assets/crayons-12-colors.png)
<!-- .element: style="margin:0 auto" -->

----

## 这些够用吗？

我能用这些颜色画出这幅画吗？

![Dream World](assets/dream-world.png)
<!-- .element: style="width: 50%; margin:0 auto" -->

----

## 我们想要更多颜色
* 更多的颜色 → 更好的图片
* 但是不可能无限购买颜色

> 那我们该怎么办？

----

<!-- .slide: class="center" -->
## 我们真的需要新蜡笔吗？
画家们是怎么解决这个问题的？

----

## 用三原色创造新颜色

![Mixing Colors](assets/mixing-colors.png)
<!-- .element: style="height: 90%; margin:0 auto" -->

----
<video controls>
  <source src="assets/making-21-colors-with-only-3-primary-colors-3x.mp4" type="video/mp4">
</video>
<!-- .element: style="margin:0 auto;" -->

----

## 那计算机呢？

我们可以用少量颜色创造很多颜色。

计算机也能显示很多颜色。

但计算机不用颜料。

> 那么，计算机是怎么创造新颜色的？

----

## 计算机也从少量颜色开始

![RGB Color Model](assets/rgb-mixing.png)
<!-- .element: style="margin:0 auto;" -->

----

## 颜色即数字

计算机用数字来表示颜色。

大多数时候，它们用 `(R, G, B)` 三个维度来表示一种颜色：

$$
Color = (Red, Green, Blue)
$$

![RGB Color Cube](assets/RGB-color-cube.svg)
<!-- .element: style="margin:0 auto" -->

----

## 从颜色到比特

每个 RGB 值作为数字存储 → 然后转为二进制（0 和 1）。

典型情况：
* 8 位用于红色
* 8 位用于绿色
* 8 位用于蓝色

```text
                          Red     Green     Blue

                        ▢▢▢▢▢▢▢▢ ▢▢▢▢▢▢▢▢ ▢▢▢▢▢▢▢▢

⚫️ RGB(0, 0, 0)       → 00000000 00000000 00000000 → 0x000000

🔴 RGB(255, 0, 0)     → 11111111 00000000 00000000 → 0xFF0000

🔵 RGB(0, 0, 255)     → 00000000 00000000 11111111 → 0x0000FF

🟢 RGB(0, 255, 0)     → 00000000 11111111 00000000 → 0x00FF00

⚪️ RGB(255, 255, 255) → 11111111 11111111 11111111 → 0xFFFFFF

🟡 RGB(255, 255, 0)   → 11111111 11111111 00000000 → 0xFFFF00
```
<!-- .element: style="text-align:center" -->

----

## 色深

色深是表示一个像素颜色所用的比特数。

* 24 位色 → 色深为 **24**（真彩色）
* 16 位色 → 色深为 **16**
* 8 位色 → 色深为 **8**

![Color Depth](assets/touchmark.png)

<!-- .element: style="width:75%; margin: 0 auto" -->
