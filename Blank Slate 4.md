# Blank Slate 4

Looks like a blank file but it's actually whitespace.

There are 2 different spaces (`ef bb bf` and `20`), it encodes binary.

Cyberchef solve: https://gchq.github.io/CyberChef/#recipe=To_Hex('Space',0)Find_/_Replace(%7B'option':'Regex','string':'20'%7D,'1',true,false,true,false)Find_/_Replace(%7B'option':'Regex','string':'e2%2080%208b'%7D,'0',true,false,true,false)Find_/_Replace(%7B'option':'Regex','string':'ef%20bb%20bf'%7D,'',true,false,true,false)Find_/_Replace(%7B'option':'Regex','string':'%20'%7D,'',true,false,true,false)From_Binary('Space',8)&input=77u/4oCLICDigIvigIsgIOKAi%2BKAiyAg4oCLICDigIvigIvigIsgIOKAi%2BKAi%2BKAi%2BKAiyDigIsgIOKAi%2BKAiyAgIOKAiyAgICDigIsgIOKAiyAgIOKAi%2BKAiyAg4oCLICAg4oCLIOKAi%2BKAi%2BKAiyAg4oCLIOKAi%2BKAiyDigIvigIsgIOKAi%2BKAi%2BKAiyDigIvigIsgIOKAi%2BKAi%2BKAiyDigIsg4oCLICAgICDigIsgIOKAiyAgIOKAi%2BKAi%2BKAiyAg4oCL4oCL4oCL4oCL4oCLICAg4oCLIOKAi%2BKAi%2BKAiyDigIsgICAgIOKAiyAg4oCL4oCL4oCLIOKAi%2BKAi%2BKAiyAg4oCL4oCL4oCLIOKAiyAg4oCL4oCL4oCL4oCLIOKAiyAg4oCLICAg4oCL4oCLICDigIsg4oCLICDigIsgICAgIOKAiw

Flag: `flag{sti11_n0t_b1ank}`
