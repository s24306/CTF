As part of the task, we receive a PowerPoint file and need to win a gacha, meaning getting a 5* character.
Problem? The chance of rolling a 5* character is exactly 0%.  
![image](https://github.com/s24306/CTF/assets/91730770/33da7dbd-38ee-4f0e-afca-9e1297f9781b)  

We need to open the macros in PowerPoint and do what we want - we can change the chances to be 100%, extract the flag directly from the code, etc.  
![image](https://github.com/s24306/CTF/assets/91730770/b94ba70c-c0f4-4463-929a-8f7040ab878b)  
![image](https://github.com/s24306/CTF/assets/91730770/f9cb1d05-27dd-4b3b-b615-835237e24ae0)  
![image](https://github.com/s24306/CTF/assets/91730770/8932f84c-8c6a-4f5b-8e5a-09a97a40aefc)  

What was the problem here?
The VBA project was password-protected, and we didn't know the password.  
Solution: <https://stackoverflow.com/questions/1026483/is-there-a-way-to-crack-the-password-on-an-excel-vba-project>  
![image](https://github.com/s24306/CTF/assets/91730770/760e80ba-b588-448c-ad4c-6001104a0c9a)  

Alternatively, if you open it on Linux in LibreOffice, it doesn't ask for any passwords.

However, I couldn't run this in LibreOffice, so I had to work on Windows.

After modifying the chances, we get a 5* character, and the flag scrolls across the screen, which not only has an inhuman color, on an inhuman background, not only moves, and makes it hard to distinguish between "I" and "l", but also can't be copied.

Some manipulation in the macros allows us to print the link to the image under the image.

After pasting the link into the browser, the image with the flag opens, and it can be easily selected and copied with the mouse.  
![image](https://github.com/s24306/CTF/assets/91730770/b60865dd-9fed-4b87-8ca9-89986dde596c)  

I hate PowerPoint.
