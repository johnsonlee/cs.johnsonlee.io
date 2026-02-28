<!-- .slide: class="center" -->

## 1.3. How Computer Represents Colors?

*From light to pixels*

----

## Colors we Have

![Crayons](assets/crayons-12-colors.png)
<!-- .element: style="margin:0 auto" -->

----

## Are These Enough?

Can I use these colors to draw this?

![Dream World](assets/dream-world.png)
<!-- .element: style="width: 50%; margin:0 auto" -->

----

## We Want More Colors
* More colors → better pictures
* But buying colors forever is hard

> So what can we do?

----

<!-- .slide: class="center" -->
## Do we Really Need New Crayons?
How do artists solve this problem?

----

## Creating New Colors with Primary Colors

![Mixing Colors](assets/mixing-colors.png)
<!-- .element: style="height: 90%; margin:0 auto" -->

----
<video controls>
  <source src="assets/making-21-colors-with-only-3-primary-colors-3x.mp4" type="video/mp4">
</video>
<!-- .element: style="margin:0 auto;" -->

----

## What About Computers?

We can create many colors from a few colors.

Computer show many colors.

But computers don't use paint.

> so, how do computers create new colors?

----

## Computer also Starts with Few Colors

![RGB Color Model](assets/rgb-mixing.png)
<!-- .element: style="margin:0 auto;" -->

----

## Color as Number

Computer represents colors as numbers.

Most of the time, they use `(R, G, B)` three dimensions to represent a color:

$$
Color = (Red, Green, Blue)
$$

![RGB Color Cube](assets/RGB-color-cube.svg)
<!-- .element: style="margin:0 auto" -->

----

## From Color to Bits

Each RGB value is stored as a number → then as binary (0 and 1).

Typical case:
* 8 bits for Red
* 8 bits for Green
* 8 bits for Blue

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

## Color Depth

Color depth is the number of bits used to represent the color of one pixel.

* 24-bit color → depth is **24** (True Color)
* 16-bit color → depth is **16**
* 8-bit color → depth is **8**

![Color Depth](assets/touchmark.png)

<!-- .element: style="width:75%; margin: 0 auto" -->
