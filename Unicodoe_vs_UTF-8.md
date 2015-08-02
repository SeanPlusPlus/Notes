# Unicode vs utf-8

http://kunststube.net/encoding/

- Unicode first and foremost defines a table of code points for characters. That's a fancy way of saying "65 stands for A, 66 stands for B and 9,731 stands for ☃" (seriously, it does).  How these code points are actually encoded into bits is a different topic.

- If the letter "A" was always encoded to ```00000000 00000000 00000000 01000001```, "B" always to ```00000000 00000000 00000000 01000010``` and so on, any document would bloat to four times the necessary size.
