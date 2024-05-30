> ##  “Can you run Internet Explorer on Linux?”

As part of the task, we received a link to the site: [https://internet-explorer.knping.pl/](https://internet-explorer.knping.pl/).
Our task is to "run" Internet Explorer on Linux.
It is obvious that this is physically impossible since IE was an exclusive browser for Windows.
When I opened the page, I saw the following message:  
![image](https://github.com/s24306/CTF/assets/91730770/ca887562-abf2-4064-afc9-66cd9439dbd8)  

Burp Suite allows us to run a proxy with an interception option where we can view and edit what our browser sends in the request.  
![image](https://github.com/s24306/CTF/assets/91730770/df8ba543-bbaf-47a2-8d1d-09b5f4256ec0)  

Information about the browser and operating system we are using is sent via the "User-Agent" header.

Here we see that our operating system is Windows, and the browser is Chrome:  
![image](https://github.com/s24306/CTF/assets/91730770/201d1cf3-f78b-424b-b601-80d227503406)  

Information on Mozilla's site:
[https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/User-Agent](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/User-Agent)

So, let's change the system to Linux and the browser to IE 9:  
![image](https://github.com/s24306/CTF/assets/91730770/81e2616d-d3fd-483c-a31c-0f7f48ac23c8)  

Since we completed the task, we were presented with the flag:  
![image](https://github.com/s24306/CTF/assets/91730770/a92aa688-1545-4b2f-a76d-5a07ce6727e1)  

The answer to the challenge is: **ping{the_best_browser_ever_made111}**
