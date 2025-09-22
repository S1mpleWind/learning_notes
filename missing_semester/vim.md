# Vim 

## What is Vim

vim is a very powerful text-editing tool .
If u can master Vim , then u'll get a better efficiency when editing codes .

## Modes

Vim has 4 modes basically : **normal** , **insert** , **visual** , **command**

we can switch between the 4 modes :


normal(default) --i--> Insert / --v--> Visual / --:--> command

in other modes , press <Esc> to go back to normal

1. in ***normal*** mode we have the most commands for *move,edit,find*


- [move] : 
    - hjkl : directions
    - w,b,e : words
    - 0,$,^ : line
    - ^u,^d : scroll
    - h,m,l : page
    - % + bracket : go to the other bracket
    - gg,[n]G : entire content
    - [verb] + `i/a` : inside and around a pair of brackets

- [Edit]:
    - x,X : delete one character
    - d+w : delete word
    - dd  : CUT the line 
    - a   : append after the cursor
    - i   : insert before the cursor (enter insert mode)
    - y   : yank a charecter
    - yy  : yank the whole line
    - c<noun> : change <noun> = x + i

- [Find]
    - /<target> : forward to target
    - ?<target> : backforward search
    - n : next , continue previous search

 
 2. in Command mode , after pressing `:`
 
 - w : write the file 
 - q : quit 
 - q!: force quit
 - s : substitude in form `{range}s/{old}/{new}/{flag}`
    - range : current line(default) , `%`(whole content) , `n,m `(n-m lines)
    - flage : g (global) , c (confirm) , i (ignore upper and lower)

 3. in **Visual** Mode 
 move the cursor to select content

 4. in **Insert** Mode
    just type whatever u want 
    
