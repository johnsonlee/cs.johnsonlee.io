<!-- .slide: class="center" -->

## 1.2. 计算机如何表示文字？

*从符号到字节*

----

## 文字即数字

文字本质上是一系列字符的序列，包括

* 字母
* 数字
* 符号
* 空格

> 由于计算机只能理解数字，核心思想是将字符表示为数字

----

## 从字符到比特

文字中的每个字符都映射到一个数字：

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

> **ASCII** 的诞生是为了确保不同的计算机能够以相同的方式表示和理解文字，从而可靠地交换数据。

----

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

----

## 英文字符即数字

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

----

## 英文字符即数字

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

----

## 英文字符即数字

```text[7-15]
HEX |   0     1     2     3     4     5     6     7     8     9     A     B     C     D     E     F
----+-----------------------------------------------------------------------------------------------
 0  | <NUL> <SOH> <STX> <ETX> <EOT> <ENQ> <ACK> <BEL> <BS>  <HT>  <LF>  <VT>  <FF>  <CR>  <SO>  <SI>
 1  | <DLE> <DC1> <DC2> <DC3> <DC4> <NAK> <SYN> <ETB> <CAN> <EM>  <SUB> <ESC> <FS>  <GS>  <RS>  <US>
 2  | <SP>    !     "     #     $     %     &     '     (     )     *     +     ,     -     .     /
 3  |   0     1     2     3     4     5     6     7     8     9     :     ;     <     =     >     ?
 4  |   @     A     B     C     D     E     F     G     H     I     J     K     L     M     N     O

             ↓

         0x41 (65)
```
<!-- .element: data-id="ascii" style="margin:0 auto;" -->


----

## 英文字符即数字

```text[7-15]
HEX |   0     1     2     3     4     5     6     7     8     9     A     B     C     D     E     F
----+-----------------------------------------------------------------------------------------------
 0  | <NUL> <SOH> <STX> <ETX> <EOT> <ENQ> <ACK> <BEL> <BS>  <HT>  <LF>  <VT>  <FF>  <CR>  <SO>  <SI>
 1  | <DLE> <DC1> <DC2> <DC3> <DC4> <NAK> <SYN> <ETB> <CAN> <EM>  <SUB> <ESC> <FS>  <GS>  <RS>  <US>
 2  | <SP>    !     "     #     $     %     &     '     (     )     *     +     ,     -     .     /
 3  |   0     1     2     3     4     5     6     7     8     9     :     ;     <     =     >     ?
 4  |   @     A     B     C     D     E     F     G     H     I     J     K     L     M     N     O

             ↓

         0x41 (65)

             ↓

         0100 0001
```
<!-- .element: data-id="ascii" style="margin:0 auto;" -->

----

## 英文字符即数字

```text[7-15]
HEX |   0     1     2     3     4     5     6     7     8     9     A     B     C     D     E     F
----+-----------------------------------------------------------------------------------------------
 0  | <NUL> <SOH> <STX> <ETX> <EOT> <ENQ> <ACK> <BEL> <BS>  <HT>  <LF>  <VT>  <FF>  <CR>  <SO>  <SI>
 1  | <DLE> <DC1> <DC2> <DC3> <DC4> <NAK> <SYN> <ETB> <CAN> <EM>  <SUB> <ESC> <FS>  <GS>  <RS>  <US>
 2  | <SP>    !     "     #     $     %     &     '     (     )     *     +     ,     -     .     /
 3  |   0     1     2     3     4     5     6     7     8     9     :     ;     <     =     >     ?
 4  |   @     A     B     C     D     E     F     G     H     I     J     K     L     M     N     O

                    ↓

                0x42 (66)
```
<!-- .element: data-id="ascii" style="margin:0 auto;" -->

----

## 英文字符即数字

```text[7-15]
HEX |   0     1     2     3     4     5     6     7     8     9     A     B     C     D     E     F
----+-----------------------------------------------------------------------------------------------
 0  | <NUL> <SOH> <STX> <ETX> <EOT> <ENQ> <ACK> <BEL> <BS>  <HT>  <LF>  <VT>  <FF>  <CR>  <SO>  <SI>
 1  | <DLE> <DC1> <DC2> <DC3> <DC4> <NAK> <SYN> <ETB> <CAN> <EM>  <SUB> <ESC> <FS>  <GS>  <RS>  <US>
 2  | <SP>    !     "     #     $     %     &     '     (     )     *     +     ,     -     .     /
 3  |   0     1     2     3     4     5     6     7     8     9     :     ;     <     =     >     ?
 4  |   @     A     B     C     D     E     F     G     H     I     J     K     L     M     N     O

                    ↓

                0x42 (66)

                    ↓

                0100 0010
```
<!-- .element: data-id="ascii" style="margin:0 auto;" -->

----

## 英文字符即数字

```text[7-15]
HEX |   0     1     2     3     4     5     6     7     8     9     A     B     C     D     E     F
----+-----------------------------------------------------------------------------------------------
 0  | <NUL> <SOH> <STX> <ETX> <EOT> <ENQ> <ACK> <BEL> <BS>  <HT>  <LF>  <VT>  <FF>  <CR>  <SO>  <SI>
 1  | <DLE> <DC1> <DC2> <DC3> <DC4> <NAK> <SYN> <ETB> <CAN> <EM>  <SUB> <ESC> <FS>  <GS>  <RS>  <US>
 2  | <SP>    !     "     #     $     %     &     '     (     )     *     +     ,     -     .     /
 3  |   0     1     2     3     4     5     6     7     8     9     :     ;     <     =     >     ?
 4  |   @     A     B     C     D     E     F     G     H     I     J     K     L     M     N     O

                          ↓

                      0x43 (67)
```
<!-- .element: data-id="ascii" style="margin:0 auto;" -->

----

## 英文字符即数字

```text[7-15]
HEX |   0     1     2     3     4     5     6     7     8     9     A     B     C     D     E     F
----+-----------------------------------------------------------------------------------------------
 0  | <NUL> <SOH> <STX> <ETX> <EOT> <ENQ> <ACK> <BEL> <BS>  <HT>  <LF>  <VT>  <FF>  <CR>  <SO>  <SI>
 1  | <DLE> <DC1> <DC2> <DC3> <DC4> <NAK> <SYN> <ETB> <CAN> <EM>  <SUB> <ESC> <FS>  <GS>  <RS>  <US>
 2  | <SP>    !     "     #     $     %     &     '     (     )     *     +     ,     -     .     /
 3  |   0     1     2     3     4     5     6     7     8     9     :     ;     <     =     >     ?
 4  |   @     A     B     C     D     E     F     G     H     I     J     K     L     M     N     O

                          ↓

                      0x43 (67)

                          ↓

                      0100 0011
```
<!-- .element: data-id="ascii" style="margin:0 auto;" -->

----

<!-- .slide: class="center" -->
## 计算机如何表示汉字？

----

## Unicode 字符集

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

----

## 为什么 ASCII 不够用？

ASCII 可以表示：
* 英文字母
* 数字
但不能表示：
* 中文
* 日文
* 韩文
* 表情符号

----

## 其他字符集

* ISO 8859-1
* GBK
* GB2312
* GB18030
* ……
