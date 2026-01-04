<!-- .slide: class="center" -->
## How Computer Represents Information?

---

## Common Types of Information

* 🔢 Number
* 🔤 Text
* 🎨 Color
* 🖼 Image / Video
* 🔊 Sound / Audio
* 💻 Program Instructions / Binary Data / etc.
* ...

---

<!-- .slide: class="center" -->
## How Computer Represents Numbers?

---

## How do Human Count?

Before computers,

Humans were already counting.

` `

` `

` `

> How did we start counting in the first place?

---

## Counting with Fingers!

Human have 10 fingers:

![10 fingers](https://www.emoji.family/api/emojis/1f450/noto/png/256)
<!-- .element: style="text-align:center" -->

` `

> So, counting in group of 10 feels natural to us.

---

## Decimal

We use *decimal* symbols (digits):

` `

> 0 1 2 3 4 5 6 7 8 9

` `

After 9, we run out of symbols, then:
* Go back to 0 <!-- .element: class="fragment" data-fragment-index="1" -->
* Carry 1 to the next position <!-- .element: class="fragment" data-fragment-index="2" -->

<br/>
<br/>

**This rule is not about math, it's about representation.** <!-- .element: class="fragment" data-fragment-index="3" -->

---

## What does "Decimal" Mean?

Decimal means:

* **10** symbols
* Each position is worth a power of **10**

` `

The values comes from the **position**.

` `

> `345 = 300 + 40 + 5`  
> `    = 3 × 10² + 4 × 10¹ + 5 × 10⁰`

---

<!-- .slide: class="center" -->
## Is Decimal the ONLY Way to Count?

---

<!-- .slide: class="center" -->
> Decimal is a human choice.

---

## Computer's Choice

If **Decimal** comes from human hands,

What kind of "hands" do computers have?

` `

` `

> Computers also have a choice.  
> But their choice is limited by -- **hardware**.

---

## Hardware Limits the Choice

At the lowest level, a computer can only reliably tell:
* ON / OFF
* High / Low
* 1 / 0

` `

` `

> This makes **binary** a natural choice.

---

## Binary

Computers use binary digits:

> 0 1

` `

Just like **decimal**:
* There are only 2 symbols
* Each position has a weight (a power of 2)

` `

The value also comes from the **position**:

`1010 = 1 × 2³ + 0 × 2² + 1 × 2¹ + 0 × 2⁰`

---

## Hexadecimal

Just like **decimal** and **binary**:
* Hexadecimal has 16 symbols: 0 1 2 3 4 5 6 7 8 9 A B C D E F
* Each position has a weight (a power of 16)

` `

The value also comes from the **position**:

`12A = 1 × 16² + 2 × 16¹ + 10 × 16⁰`

` `

So, binary and hexadecimal follow the same idea as decimal.

---

<!-- .slide: class="center" -->
### This shared idea has a name -- Positional Numeral System

---

## Different Representations

We write numbers using symbols:
* 42
* 101010
* 2A

` `

They look different, but can represent the same value.

` `

> What makes them different?

---

## What's NOT the Difference?

The difference is NOT:
* The value
* The idea of counting

---

## Number of Symbols Matters

Each representation uses a different set of symbols:
* Decimal uses 10 symbols

  → `0 1 2 3 4 5 6 7 8 9`

* Binary uses 2 symbols

  → `0 1`

* Hexadecimal uses 16 symbols

  → `0 1 2 3 4 5 6 7 8 9 A B C D E F`

This is called:

> The **Base (Radix)** of a Number System

---

## Base Notation

Any number expressed in base 𝑏 can be represented as follows:

$$
(d_n d_{n-1} \dots d_1 d_0)_b
$$

| Base | Digits                          | Notation   |
|:----:|:-------------------------------:|:----------:|
| 2    | 0 1                             | (1010)₂    |
| 10   | 0 1 2 3 4 5 6 7 8 9             | (42)₁₀     |
| 16   | 0 1 2 3 4 5 6 7 8 9 A B C D E F | (2A)₁₆     |

---

<!-- .slide: class="center" -->
## How Computer Stores Numbers?

---

## Numbers in Binary

We know that numbers are represented in binary digits.

Inside a computer, binary digits are represented as **bits**.

` `

`Digits :   1    0    1    0`

`           ↓    ↓    ↓    ↓`

`Bits   :   1    0    1    0`

` `

> Where do these bits live?

---

## Bits Live in Memory

Bits are stored in **memory** in groups. A group of 8 bits is called a **byte**.

Memory is a long sequence of bytes:

```
+--------+--------+--------+--------+--------+--------+--------+
| byte 0 | byte 1 | byte 2 | byte 3 | byte 4 |  ....  | byte N |
+--------+--------+--------+--------+--------+--------+--------+
↓↓↓↓↓↓↓↓
10100101
```
<!-- .element: style="text-align:center" -->

Memory has order, bits are stored next to each other.

In real program, we store many numbers in memory.

> So, we need a way to know **where one number ends and the next one begins**.

---

## A Natural Idea

Numbers can be:
* small: `123`
* large: `23456789`

` `

Why no use:
* fewer bits for small numbers
* more bits for large numbers?

` `

> This sounds efficient, right?

---

## A Problem with Variable Length

If numbers use different numbers of bits,

How do we find the next numbers?

` `

` `

> To find the 10th number, do we have to count from the beginning?

---

<!-- .slide: class="center" -->
### What if each number uses the same number of bits?

---

## Fixed-size Numbers

With fixed-size numbers, the position of each number is predictable.

` `

Fixed size solves:
> Where is the next number?

` `

But we still need to choose:
> How many bits per number?

---

## Bit-width

The number of bits used for one number is called its **bit-width**.

` `

Common choices:

```text
  bit-width | bits                                                            
------------+-----------------------------------------------------------------
    8-bit   | ▢▢▢▢▢▢▢▢                                                        
   16-bit   | ▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢                                                
   32-bit   | ▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢                                
   64-bit   | ▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢
```
<!-- .element: style="text-align:center" -->

` `

> Why not always use 64-bits?

---

## Bit-width is a Trade-off

More bits means:
* larger range
* more memory

` `

Fewer bits means:
* smaller range
* less memory

---

## A Quick Thought

If we store 1,000,000 numbers:
* 8-bit → 1MB
* 32-bit → 4MB
* 64-bit → 8MB

` `

` `

> Same count of numbers, different memory cost.  
> ` `  
> This matters in real programs.

---

## Negative Numbers

So far, we can store numbers in bits.

But what about negative numbers?

How do we store:
* -1
* -10
* -100
* ...?

---

## Back to Number System

In a **Positional Numeral System**, digits represent **Place Values**, they tell us:

> How big a number is.

` `

But digits have no idea about **direction** (positive or negative).

They only represent magnitude, no sign.

---

## Where does the Sign Come From?

If digits only represent magnitude...

Then we must use some bits to represent **sign**.

` `

` `

> A natural choice is -- using 1 bit to represent the **sign**

---

## Signed Numbers Representation

```text
 bit-width | bits                                                             
-----------+------------------------------------------------------------------
    8-bit  | ◌▢▢▢▢▢▢▢                                                         
   16-bit  | ◌▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢                                                
   32-bit  | ◌▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢                                
   64-bit  | ◌▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢▢


  ◌ → sign     
  ▢ → magnitude
```
<!-- .element: style="text-align:center" -->

---

## Cost of Sign

Using a sign means:
* fewer bits for magnitude
* smaller range of values

` `

What about ...
* age
* number of students
* ...

` `

> Do we always need the **sign**?

---

## Unsigned Numbers

If we don't need negative numbers,

We can use all bits for magnitude.

` `

` `

> This interpretation is called -- **Unsigned**

---

## Integer Range : Signed vs Unsigned

` `

```text
 bit-width |    Unsigned Range    |     Signed Range     
-----------+----------------------+----------------------
    8-bit  |     0 ~ 2^8  − 1     |   −2^7  ~ 2^7  − 1   
   16-bit  |     0 ~ 2^16 − 1     |   −2^15 ~ 2^15 − 1   
   32-bit  |     0 ~ 2^32 − 1     |   −2^31 ~ 2^31 − 1   
   64-bit  |     0 ~ 2^64 − 1     |   −2^63 ~ 2^63 − 1   
```
<!-- .element: style="text-align:center" -->

` `

` `

> Signed numbers give up **half the range** to get **sign**

---

## Non-integers

What about numbers like:
* 3.1415926
* 0.1
* -2.5

` `

Can we just store like this?

$$
3.1415926 \times 10000000 = 31415926
$$

> What about `1/3`?

---

## A New Difficulty

If we scale numbers:
* How many decimal places do we keep?
* What if the number is very large?
* What if it is very small?

` `

` `

> We need to represent both **size** and **precision**

---

## What We Want?

We want a way to represent:
* very large numbers
* very small numbers
* with limited bits

---

## Scientific Notation

In math, we can write:
* `314.15926 = 3.1415926 × 10^2`
* `0.0000121 = 1.21 × 10^−5`

` `

This is **Scientific Notation**.

$$
m \times 10^{n}, \quad 1 \le m < 10
$$


---

## Floating Point Representation

Computers do something similar:

` `

` `

$$
Number = Mantissa \times Base^{exponent}
$$

---

## Representation: Integer vs Floating

* Integers → exact
* Floating Point → approximate

` `

` `

> Floating point numbers trade exactness for range

---

<!-- .slide: class="center" -->
## How Computer Represents Text?

---

## Text as Numbers

Text is fundamentally a sequence of characters, including

* Letters
* Numbers
* Symbols
* Spaces

` `

> As computer can only understand numbers, the core idea is to represent characters as numbers

---

## From Characters to Bits

Each character in a text is mapped to a number:

```text
Text / Characters

↓

Code Points

↓

Encoded Bytes

↓

Binary Bits
```
<!-- .element: style="text-align:center" -->

> **ASCII** was created to ensure that different computers could represent and understand text in the same way, in order to exchange data reliably.

---

## ASCII

```text
HEX |   0     1     2     3     4     5     6     7     8     9     A     B     C     D     E     F
----+-----------------------------------------------------------------------------------------------
 0  | <NUL> <SOH> <STX> <ETX> <EOT> <ENQ> <ACK> <BEL> <BS>  <HT>  <LF>  <VT>  <FF>  <CR>  <SO>  <SI>
 1  | <DLE> <DC1> <DC2> <DC3> <DC4> <NAK> <SYN> <ETB> <CAN> <EM>  <SUB> <ESC> <FS>  <GS>  <RS>  <US>
 2  | <SP>    !     "     #     $     %     &     '     (     )     *     +     ,     -     .     /
 3  |   0     1     2     3     4     5     6     7     8     9     :     ;     <     =     >     ?
 4  |   @     A     B     C     D     E     F     G     H     I     J     K     L     M     N     O
 5  |   P     Q     R     S     T     U     V     W     X     Y     Z     [     \     ]     ^     _
 6  |   `     a     b     c     d     e     f     g     h     i     j     k     l     m     n     o
 7  |   p     q     r     s     t     u     v     w     x     y     z     {     |     }     ~   <DEL>
```
<!-- .element: data-id="ascii" style="margin:0 auto;" -->

---

## English Characters as Numbers

```text[5-10]
HEX |   0     1     2     3     4     5     6     7     8     9     A     B     C     D     E     F
----+-----------------------------------------------------------------------------------------------
 0  | <NUL> <SOH> <STX> <ETX> <EOT> <ENQ> <ACK> <BEL> <BS>  <HT>  <LF>  <VT>  <FF>  <CR>  <SO>  <SI>
 1  | <DLE> <DC1> <DC2> <DC3> <DC4> <NAK> <SYN> <ETB> <CAN> <EM>  <SUB> <ESC> <FS>  <GS>  <RS>  <US>
 2  | <SP>    !     "     #     $     %     &     '     (     )     *     +     ,     -     .     /
 3  |   0     1     2     3     4     5     6     7     8     9     :     ;     <     =     >     ?
 4  |   @     A     B     C     D     E     F     G     H     I     J     K     L     M     N     O
 5  |   P     Q     R     S     T     U     V     W     X     Y     Z     [     \     ]     ^     _
 6  |   `     a     b     c     d     e     f     g     h     i     j     k     l     m     n     o
 7  |   p     q     r     s     t     u     v     w     x     y     z     {     |     }     ~   <DEL>
```
<!-- .element: data-id="ascii" style="margin:0 auto;" -->

---

## English Characters as Numbers

```text[7]
HEX |   0     1     2     3     4     5     6     7     8     9     A     B     C     D     E     F
----+-----------------------------------------------------------------------------------------------
 0  | <NUL> <SOH> <STX> <ETX> <EOT> <ENQ> <ACK> <BEL> <BS>  <HT>  <LF>  <VT>  <FF>  <CR>  <SO>  <SI>
 1  | <DLE> <DC1> <DC2> <DC3> <DC4> <NAK> <SYN> <ETB> <CAN> <EM>  <SUB> <ESC> <FS>  <GS>  <RS>  <US>
 2  | <SP>    !     "     #     $     %     &     '     (     )     *     +     ,     -     .     /
 3  |   0     1     2     3     4     5     6     7     8     9     :     ;     <     =     >     ?
 4  |   @     A     B     C     D     E     F     G     H     I     J     K     L     M     N     O
 5  |   P     Q     R     S     T     U     V     W     X     Y     Z     [     \     ]     ^     _
 6  |   `     a     b     c     d     e     f     g     h     i     j     k     l     m     n     o
 7  |   p     q     r     s     t     u     v     w     x     y     z     {     |     }     ~   <DEL>
```
<!-- .element: data-id="ascii" style="margin:0 auto;" -->


---

## English Characters as Numbers

```text[7]
HEX |   0     1     2     3     4     5     6     7     8     9     A     B     C     D     E     F
----+-----------------------------------------------------------------------------------------------
 0  | <NUL> <SOH> <STX> <ETX> <EOT> <ENQ> <ACK> <BEL> <BS>  <HT>  <LF>  <VT>  <FF>  <CR>  <SO>  <SI>
 1  | <DLE> <DC1> <DC2> <DC3> <DC4> <NAK> <SYN> <ETB> <CAN> <EM>  <SUB> <ESC> <FS>  <GS>  <RS>  <US>
 2  | <SP>    !     "     #     $     %     &     '     (     )     *     +     ,     -     .     /
 3  |   0     1     2     3     4     5     6     7     8     9     :     ;     <     =     >     ?
              A                                                                                      
```
<!-- .element: data-id="ascii" style="margin:0 auto;" -->

---

## English Characters as Numbers

```text[7-15]
HEX |   0     1     2     3     4     5     6     7     8     9     A     B     C     D     E     F
----+-----------------------------------------------------------------------------------------------
 0  | <NUL> <SOH> <STX> <ETX> <EOT> <ENQ> <ACK> <BEL> <BS>  <HT>  <LF>  <VT>  <FF>  <CR>  <SO>  <SI>
 1  | <DLE> <DC1> <DC2> <DC3> <DC4> <NAK> <SYN> <ETB> <CAN> <EM>  <SUB> <ESC> <FS>  <GS>  <RS>  <US>
 2  | <SP>    !     "     #     $     %     &     '     (     )     *     +     ,     -     .     /
 3  |   0     1     2     3     4     5     6     7     8     9     :     ;     <     =     >     ?
              A                                                                                      
                                                                                                     
              ↓                                                                                      
                                                                                                     
          0x41 (65)                                                                                  
```
<!-- .element: data-id="ascii" style="margin:0 auto;" -->


---

## English Characters as Numbers

```text[7-15]
HEX |   0     1     2     3     4     5     6     7     8     9     A     B     C     D     E     F
----+-----------------------------------------------------------------------------------------------
 0  | <NUL> <SOH> <STX> <ETX> <EOT> <ENQ> <ACK> <BEL> <BS>  <HT>  <LF>  <VT>  <FF>  <CR>  <SO>  <SI>
 1  | <DLE> <DC1> <DC2> <DC3> <DC4> <NAK> <SYN> <ETB> <CAN> <EM>  <SUB> <ESC> <FS>  <GS>  <RS>  <US>
 2  | <SP>    !     "     #     $     %     &     '     (     )     *     +     ,     -     .     /
 3  |   0     1     2     3     4     5     6     7     8     9     :     ;     <     =     >     ?
              A                                                                                      
                                                                                                     
              ↓                                                                                      
                                                                                                     
          0x41 (65)                                                                                  
                                                                                                     
              ↓                                                                                      
                                                                                                     
          0100 0001                                                                                  
```
<!-- .element: data-id="ascii" style="margin:0 auto;" -->

---

## English Characters as Numbers

```text[7]
HEX |   0     1     2     3     4     5     6     7     8     9     A     B     C     D     E     F
----+-----------------------------------------------------------------------------------------------
 0  | <NUL> <SOH> <STX> <ETX> <EOT> <ENQ> <ACK> <BEL> <BS>  <HT>  <LF>  <VT>  <FF>  <CR>  <SO>  <SI>
 1  | <DLE> <DC1> <DC2> <DC3> <DC4> <NAK> <SYN> <ETB> <CAN> <EM>  <SUB> <ESC> <FS>  <GS>  <RS>  <US>
 2  | <SP>    !     "     #     $     %     &     '     (     )     *     +     ,     -     .     /
 3  |   0     1     2     3     4     5     6     7     8     9     :     ;     <     =     >     ?
                    B                                                                                
```
<!-- .element: data-id="ascii" style="margin:0 auto;" -->

---

## English Characters as Numbers

```text[7-15]
HEX |   0     1     2     3     4     5     6     7     8     9     A     B     C     D     E     F
----+-----------------------------------------------------------------------------------------------
 0  | <NUL> <SOH> <STX> <ETX> <EOT> <ENQ> <ACK> <BEL> <BS>  <HT>  <LF>  <VT>  <FF>  <CR>  <SO>  <SI>
 1  | <DLE> <DC1> <DC2> <DC3> <DC4> <NAK> <SYN> <ETB> <CAN> <EM>  <SUB> <ESC> <FS>  <GS>  <RS>  <US>
 2  | <SP>    !     "     #     $     %     &     '     (     )     *     +     ,     -     .     /
 3  |   0     1     2     3     4     5     6     7     8     9     :     ;     <     =     >     ?
                    B                                                                                
                                                                                                     
                    ↓                                                                                
                                                                                                     
                0x42 (66)                                                                            
```
<!-- .element: data-id="ascii" style="margin:0 auto;" -->


---

## English Characters as Numbers

```text[7-15]
HEX |   0     1     2     3     4     5     6     7     8     9     A     B     C     D     E     F
----+-----------------------------------------------------------------------------------------------
 0  | <NUL> <SOH> <STX> <ETX> <EOT> <ENQ> <ACK> <BEL> <BS>  <HT>  <LF>  <VT>  <FF>  <CR>  <SO>  <SI>
 1  | <DLE> <DC1> <DC2> <DC3> <DC4> <NAK> <SYN> <ETB> <CAN> <EM>  <SUB> <ESC> <FS>  <GS>  <RS>  <US>
 2  | <SP>    !     "     #     $     %     &     '     (     )     *     +     ,     -     .     /
 3  |   0     1     2     3     4     5     6     7     8     9     :     ;     <     =     >     ?
                    B                                                                                
                                                                                                     
                    ↓                                                                                
                                                                                                     
                0x42 (66)                                                                            
                                                                                                     
                    ↓                                                                                
                                                                                                     
                0100 0010                                                                            
```
<!-- .element: data-id="ascii" style="margin:0 auto;" -->


---

<!-- .slide: class="center" -->
## How Computer Represents Chinese Characters?

---

## Unicode Character Set

```text
Character ('中')

↓

Unicode Code Point (U+4E2D)

↓

Unicode Encoded Bytes (E4 B8 AD)

↓

Bits (11100100 10111000 10101101)
```
<!-- .element: style="text-align:center" -->

---

## Why ASCII is Not Enough?

ASCII can represent:
* English Letters
* Numbers

But not:
* Chinese
* Japanese
* Korean
* Emoji

---

## Other Character Sets

* ISO 8859-1
* GBK
* GB2312
* GB18030
* ...

