The task mentioned that they received a file from somewhere.  
Upon opening the pcap file, I found several thousand packets, which was far more than I had anticipated. Manually reviewing each one was out of the question.

I focused on attempting to locate the file.
<https://ask.wireshark.org/question/13516/looking-for-a-file/>

After following the steps listed in the link above, I found one file that was nearly 3MB, which was significantly larger than any other transmitted data.  
![image](https://github.com/s24306/CTF/assets/91730770/6d7adac6-a4ed-44a0-b465-f60973bafc4d)  

Unfortunately, this was a dead end.

I returned to the starting point and tried to locate the file using **File -> Export Objects**.
In the HTTP section, I found two files.  
![image](https://github.com/s24306/CTF/assets/91730770/4510ed64-45f2-455c-9ab4-016e13665b7b)  

The first was worthless:  
![image](https://github.com/s24306/CTF/assets/91730770/ecc3ba08-c74e-468b-aa3c-e97069ec9ec0)  

However, the second one showed promise:  
![image](https://github.com/s24306/CTF/assets/91730770/55de949e-e2f6-4a4e-9ac2-722b774ed709)  

When I scrolled to the bottom of the file, I found exactly what I was looking for.  
![image](https://github.com/s24306/CTF/assets/91730770/ba3e45e3-047a-4934-84c7-78d5ddbbe50f)  

- File: `secrets.txt`
- DNS: `igotoschoolbybus`
- Password: `K#2dF!8t@1qZ`

A quick Google search led me to this tool:
<https://github.com/Arno0x/DNSExfiltrator>

The data was sent over DNS, encoded in base64URL, with option 32, and protected by a password.
Base64 and base64url differ in that URL replaces “/” with “_” and “+” with “-”.
Let's see if we can find any entries with the domain `igotoschoolbybus` in Wireshark:  
![image](https://github.com/s24306/CTF/assets/91730770/b990026d-4c44-4aa4-b996-7f8536af9ae0)  

We have three queries, the first being `init`, which does not interest me.
I examined the second one.  
![image](https://github.com/s24306/CTF/assets/91730770/6cccd7a9-4d6f-45a7-becc-adf6d216e1d0)  

I copied the subdomain, noting that the encoding - as established earlier - is base64url, so I omitted the “0?”  
![image](https://github.com/s24306/CTF/assets/91730770/ea99e371-d641-4ba8-88f5-a4709ce2ac2d)  

The best tool for decoding on the internet:
<https://gchq.github.io/CyberChef/>

I added the “from base64” option and under the arrow, I selected the “URL safe” variant, which converts base64 to base64URL.  
![image](https://github.com/s24306/CTF/assets/91730770/f029af85-0568-4efa-a70f-fc75008356ef)  

The output didn’t appear to make sense initially, BUT, earlier we found the password, and from the program’s documentation, we know it was used with RC4.  
![image](https://github.com/s24306/CTF/assets/91730770/5bc936ea-0ef7-4525-9636-5b2fb9b4d8f5)  

Bingo.
Not only did we see the file name “secrets.txt.txt,” but also “PK” indicating it is a ZIP file.

I downloaded the decrypted message using the floppy disk icon.

Let’s unpack the contents using `binwalk`.  
![image](https://github.com/s24306/CTF/assets/91730770/1e0fd90e-675b-460a-8cdf-5c101512200f)  

Let's navigate to the folder and read what we found.  
![image](https://github.com/s24306/CTF/assets/91730770/d7c4ea2a-d81a-4771-8bd7-904032021258)  

An identical task on YouTube:
<https://youtu.be/aj3auvz0sZc?si=B2PW1gsxItqmpTHo>
