> ## “Welcome to the "private-conversation" challenge, where you find yourself in the role of a cryptanalyst facing an intriguing encrypted message.
> ## Scenario
> ## In the midst of your cryptographic investigations, you stumble upon a fragment of a conversation that appears to be encoded in a highly unusual and complex manner. The content of this conversation could potentially hold significant information or secrets.
> ## Your challenge is to decrypt the message and reveal its content. The fate of uncovering valuable information lies in your decryption skills. Can you decipher the message and unveil the hidden message within?”

As part of the challenge, we received HTML, CSS files, and a folder with three images.

Upon opening the HTML, we saw a hilariously funny conversation.  
![image](https://github.com/s24306/CTF/assets/91730770/ec4987e7-102d-4685-8fd8-f0f27abd6129)  

It was immediately noticeable that the encrypted message consisted only of two characters - X and D. I assumed it was binary code.

First, I wrote a program that extracted only uppercase letters from the text, but the decrypted result was gibberish.
I rewrote the program to extract only lowercase letters - this time, it was also gibberish.

After two hours of struggling, I came up with a solution I hadn't tried yet - substituting 1 for each uppercase letter and 0 for each lowercase letter:  
![image](https://github.com/s24306/CTF/assets/91730770/5d1eab23-d285-4e1a-92a1-ca280abbf44c)  

After pasting the result into CyberChef, I got a C++ code:  
![image](https://github.com/s24306/CTF/assets/91730770/6e9459f6-c66e-4fbc-a743-85db559bb28a)  

After compiling the code and running the file, we got the result:  
![image](https://github.com/s24306/CTF/assets/91730770/9903ab2e-8111-4fb5-98e0-71f7e377c1e4)  

The answer to the challenge is: **ping{why_so_serious_XD}**
