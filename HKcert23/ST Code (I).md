After entering the website, we get "links".  
![image](https://github.com/s24306/CTF/assets/91730770/00de2342-f067-4625-9b38-0315b82c4dee)  

Upon accessing /flag1, we get a strange-looking QR code, which, after being scanned, tells us that this is not it.  
![image](https://github.com/s24306/CTF/assets/91730770/57bb2c48-0889-48c2-b2c6-a90e0df041e5)  

We go to /source, where we can see that the QR code is actually an SVG.  
![image](https://github.com/s24306/CTF/assets/91730770/180b3bdd-19b1-4480-a80e-d83be18f6819)  

Returning to /flag1 and inspecting the source.  
![image](https://github.com/s24306/CTF/assets/91730770/82feef97-ab0f-4c72-a19f-e76e4fcc11d1)  

The image looks strange because of the “rx” attributes, but even after removing them, nothing changes.
But why do the rx values range between 0 and 1, when they can be much larger?

Quickly copying the contents of the page to a txt file and processing it in bash:  
![image](https://github.com/s24306/CTF/assets/91730770/7185e917-14cb-4a9e-a814-c28f9eaee078)  

A quick trip to the reliable CyberChef -> From binary.  
![image](https://github.com/s24306/CTF/assets/91730770/23d9503f-715c-4e44-902d-79d282ffb89c)
