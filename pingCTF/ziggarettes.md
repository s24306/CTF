> "Don't smoke cigarettes, kids!"

As part of the task, we receive a file named `main` that, when run, asks us if we know the flag. If we enter the correct flag, we get the response “Correct!”; otherwise, it will be “Wrong!”.

Of course, we could write a script to brute-force the program, but that's not where the fun lies.

So, I ran Ghidra, which is used for reverse engineering.

In the main window of the program, we can view the assembly code, but those who are less adept can also try their hand by looking at the window on the right, which contains the same code in C.
![image](https://github.com/s24306/CTF/assets/91730770/83c30e9f-32aa-4940-84c9-8bda78bedba0)

Every program starts somewhere, usually with “main” or “entry.” In our case, it’s the latter.  
![image](https://github.com/s24306/CTF/assets/91730770/a2aa8b18-97d0-42fd-8057-311f536cb1a6)  

The actual code of the program and the real “main” is found in `(FUN_0020215e)`.
Let's proceed to it.

In the second half of the function, we encounter the text we are familiar with:  
![image](https://github.com/s24306/CTF/assets/91730770/5fce5303-86c0-4665-9e1e-5408e8cbe837)  

And below it, there is a switch statement:  
![image](https://github.com/s24306/CTF/assets/91730770/5f57efe0-2bef-4d29-a425-a153ba924e5e)  

Unfortunately, `WrongFunction`, `CorrectFunction`, and `LAB_002025e0` cut directly into the switch, which makes it a bit harder to read but not impossible.

At the beginning, a variable named `uVar7` by Ghidra is initialized with the value 0. The switch checks its value, and after the cases, it increments its value by 1. When the variable reaches the value `0x23`, which is 35 in decimal, the program ends, congratulating us on the correct answer.

The switch checks whether the characters in the string are in the correct positions, and if not, the program ends.

Knowing this, we can rewrite the switch into a separate file and replace the validity check with printing the character to the terminal.  
![image](https://github.com/s24306/CTF/assets/91730770/70a52e2d-cdeb-4b30-8899-320b2a3e928a)  

After compiling and running the program, we will get our flag.  
![image](https://github.com/s24306/CTF/assets/91730770/c88bab72-1b51-49d9-b46d-ada9266a3340)  


The answer to the challenge is: `ping{z1G_1S_v3RY_C0Ol_234mKIKIO2pl}`
