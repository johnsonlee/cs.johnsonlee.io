<!-- .slide: class="center" -->

## 1.2. How Computer Represents Text?

*From symbols to bytes*

----

## Text as Numbers

Text is fundamentally a sequence of characters, including

* Letters
* Numbers
* Symbols
* Spaces

> As computer can only understand numbers, the core idea is to represent characters as numbers

----

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

----

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

----

## English Characters as Numbers

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

## English Characters as Numbers

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

## English Characters as Numbers

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

## English Characters as Numbers

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

## English Characters as Numbers

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

## English Characters as Numbers

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
## How Computer Represents Chinese Characters?

----

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

----

## Why ASCII is Not Enough?

ASCII can represent:
* English Letters
* Numbers
But not:
* Chinese
* Japanese
* Korean
* Emoji

----

## Other Character Sets

* ISO 8859-1
* GBK
* GB2312
* GB18030
* ...
