# Unicode vs UTF-8

http://kunststube.net/encoding/

- Unicode is a large table mapping characters to numbers and the different UTF encodings specify how these numbers are encoded as bits.

- Unicode first and foremost defines a table of code points for characters. That's a fancy way of saying "65 stands for A, 66 stands for B and 9,731 stands for ☃" (seriously, it does).  How these code points are actually encoded into bits is a different topic.

- If the letter "A" was always encoded to ```00000000 00000000 00000000 01000001```, "B" always to ```00000000 00000000 00000000 01000010``` and so on, any document would bloat to four times the necessary size.

- To optimize this, there are several ways to encode Unicode code points into bits. UTF-32 is such an encoding that encodes all Unicode code points using 32 bits. That is, four bytes per character. It's very simple, but often wastes a lot of space. UTF-16 and UTF-8 are variable-length encodings.

- If a character can be represented using a single byte (because its code point is a very small number), UTF-8 will encode it with a single byte. If it requires two bytes, it will use two bytes and so on. It has elaborate ways to use the highest bits in a byte to signal how many bytes a character consists of. This can save space, but may also waste space if these signal bits need to be used often. UTF-16 is in the middle, using at least two bytes, growing to up to four bytes as necessary.

![lookup](https://raw.githubusercontent.com/SeanPlusPlus/Notes/master/imgs/utf_lookup.png)

https://docs.python.org/2/howto/unicode.html

- A Unicode string is a sequence of code points, which are numbers from 0 to 0x10ffff.

- The rules for translating a Unicode string into a sequence of bytes are called an encoding.

- UTF stands for “Unicode Transformation Format”, and the ‘8’ means that 8-bit numbers are used in the encoding.
