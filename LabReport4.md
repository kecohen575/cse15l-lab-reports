# Lab Report 4

> ## Part 1:
For the Week 6 lab, my group chose to change the main method to take a command-line argument. We did it using the following key presses:
```
/pars<Enter>y$/"<Enter>d$"0pi))<<<<delete>1<esc>:wq
```
After entering vim for DocSearch.java, typing /pars<Enter> brought me to this place in the code.

  ![Image](findparse<Enter>.png)
  
Using y$ copies the rest of the line we're on, while /"<Enter> brings us here.
  
  ![Image](find".png)
  
  Using d$ deletes the rest of the line, leaving us with this.
  
  ![Image](d$.png)
  
  "0p pastes what we originally copied, not what we just deleted.
  
  ![Image]("0p.png)
  
  Entering insert mode with i, I added two parenthesis, used arrow keys to go left three times, and then deleted the 0 replacing it with a one leaving us with this final result:
  
  ![Image](finalResult.png)
  
  Lastly use <esc> to exit insert mode, and :wq to save and quit.
  
> ## Part 2
