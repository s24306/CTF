The password game, but with a flag and much more inhuman.

While my teammate was doing this:  
![image](https://github.com/s24306/CTF/assets/91730770/6344b24d-1c9e-4cf0-8392-ec499079b597)  

I was doing this:  
![image](https://github.com/s24306/CTF/assets/91730770/ed85a342-f883-4d5f-b89c-5022fba624b7)  

I was convinced that since this was a CTF competition, it wouldn't be possible to get the flag just by playing the game.  
Through scanning, but you could also just read the script name in the page source, I found these files:  
![image](https://github.com/s24306/CTF/assets/91730770/9cb81893-4193-4f8c-8b42-16d01b66af6b)  

After accessing them, I saw this:  
![image](https://github.com/s24306/CTF/assets/91730770/636d065a-ae43-4156-bf8d-4f0713b77a8d)  

Very exciting, since you can see the rules one by one, so maybe there will be a flag at the end?  
![image](https://github.com/s24306/CTF/assets/91730770/c702046d-0090-4b30-a885-21baacc3f50a)  

This doesn't look good, I told my teammate that the next questions might be intentionally broken, to which he responded - "nah"  
.  
.  
.  
![image](https://github.com/s24306/CTF/assets/91730770/c11568e4-f50b-4826-8256-248332abf415)  


After about two hours of staring at black-and-white text, I noticed something I'd been ignoring the whole time at the very bottom of the page:  
![image](https://github.com/s24306/CTF/assets/91730770/469ffa36-579f-45d7-bb6b-a4ec99981eac)  

By adding .map to the page address, I downloaded a file that looked like this:  
![image](https://github.com/s24306/CTF/assets/91730770/7c5554b1-6fce-4d2f-8d9c-3818dd97f541)  

It looked like real progress, so I decided to Google what these source maps in JS are and found this site: <https://web.dev/articles/source-maps>  
And on it, another site that allowed uploading the map file:  
![image](https://github.com/s24306/CTF/assets/91730770/7e38a125-2f47-4af6-994f-34618f873509)  

BINGO  
The map allows you to read the entire code as it was originally written.  
A quick glance to see if there's a flag anywhere, but no, there wasn't.  
So let's look at the rules:  
![image](https://github.com/s24306/CTF/assets/91730770/c473f858-85ee-4a0a-9c42-ca3017e375d8)  

Intentionally broken, however, there's something interesting under each -> the result of sha224/256, starting with specific characters.  
My teammate wrote a quick program:  
![image](https://github.com/s24306/CTF/assets/91730770/f0d6cde0-81ce-44fc-bc8f-05897eaef623)  

That was it.  
Unfortunately, we still couldn't decode the next parts of the flag.
