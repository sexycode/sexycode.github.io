---
title : "Draw box character in termial"
#excerpt : ""

categories:
   - Blog
tags:
   - Blog
---

- Draw box character in terminal 

	1. https://unix.stackexchange.com/questions/559708/how-to-draw-a-continuous-line-in-terminal



```
shkim@shkim-desktop:~$ echo $TERM
xterm
shkim@shkim-desktop:~$ tput smacs
printf "%s\n%s\n" 'lqqqqqk' 'mqqqqqj'
tput rmacs
┌─────┐
└─────┘
```
- whole char

```
echo '+ , - . 0 ` a f g h i j k l m n o p q r s t u v w y x z { | } ~'
tput smacs
echo '+ , - . 0 ` a f g h i j k l m n o p q r s t u v w y x z { | } ~'
tput rmacs

+ , - . 0 ` a f g h i j k l m n o p q r s t u v w y x z { | } ~
+ , - . 0 ♦ # ° ± n ↓ ┘ ┐ ┌ └ ┼ ⎺ ⎻ ─ ⎼ ⎽ ├ ┤ ┴ ┬ ≤ │ ≥ # ≠ £ ·

```


- https://www.tecmint.com/boxes-draws-ascii-art-boxes-in-linux-terminal/
