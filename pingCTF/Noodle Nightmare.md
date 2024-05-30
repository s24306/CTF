> ## In the last programming session, Bajtek unleashed a coding catastrophe – his spaghetti code was so messy that even the compiler threw up its hands in surrender. Colleagues attempted to debug it, but the code was like a Rubik's Cube on a caffeine overdose. Bajtek proudly declared it an avant-garde programming masterpiece, leaving his coworkers wondering if they should call a programmer's version of an exorcist. In the end, they renamed his file "spaghetti.cpp" to "noodleNightmare.cpp" as a memorial to the chaotic session.

As part of the challenge, we received a package containing the file noodleNightmare.cpp and a folder "spaghetti" containing over 800 cpp files, where the content of each file was limited to a few characters.

The content of noodleNightmare.cpp looked like this:  
![image](https://github.com/s24306/CTF/assets/91730770/7ff943d1-dc08-41a5-b450-ddb49b6b7da8)  

To debug the code, I wrote a script that would copy the content of the above, replacing each "#include" with the characters it contains.  
![image](https://github.com/s24306/CTF/assets/91730770/90a19f1e-0b8c-4434-94ae-fa20da587d41)  

The script's output:  
![image](https://github.com/s24306/CTF/assets/91730770/f4ef5f20-65dd-4547-a972-f7d8453ce4c4)  

After some beautification, here is how the code looked:  
![image](https://github.com/s24306/CTF/assets/91730770/356f6dd7-a612-4ee5-8c1f-33d8293f5805)  

The program collected input from the user and - if it matched the flag - returned a congratulatory message.

As you can see, the flag is 55 characters long.
One possible approach would be to write a script that iterates through every possible combination of characters starting with "ping{" and ending with "}", until the program returns a congratulatory message, indicating that the combination is the correct flag.

Unfortunately, I am lazy and only added cout of the completed flag before the if statement.  
![image](https://github.com/s24306/CTF/assets/91730770/707e12b8-a620-49bc-a159-34fbe05321c8)  

The program's output:  
![image](https://github.com/s24306/CTF/assets/91730770/c6e921d8-20d5-49df-a847-96a90890d746)  

The answer to the challenge is: **ping{it_is_bad_when_code_is_easier_to_read_in_assembly}**
