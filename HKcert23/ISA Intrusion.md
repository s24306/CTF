Documentation: <https://hackmd.io/@blackb6a/bauhinia-isa>  
We run the code - it crashes.  
![image](https://github.com/s24306/CTF/assets/91730770/882bcc48-2c3f-40ec-997b-0f88f17b05ba)  

Line 4 is unreasonable, so we'll copy the entire code to the Playground and change 100000 to 1.  
![image](https://github.com/s24306/CTF/assets/91730770/41512330-154e-47d5-9dd8-0557a9618957)  

Now the program completes its execution correctly, but that's it, the terminal is empty.

We can notice that some characters are being pushed onto the stack. Let's try to print what's behind them by calling a SYSCALL that prints them to the terminal:  
![image](https://github.com/s24306/CTF/assets/91730770/24920af9-39ed-4151-88b4-721d494bfb61)  

Gibberish.

The last few dozen lines involve juggling the contents of registers; I'm not even going to try to understand that.  
![image](https://github.com/s24306/CTF/assets/91730770/227a8427-fba7-4bde-ae52-f36b269ac28c)  

After the program finished running, I accidentally scrolled through the memory view to the place where the earlier gibberish was pushed:  
![image](https://github.com/s24306/CTF/assets/91730770/a77825d7-704b-49c0-9a8d-49469e92a99f)  

It turns out that those few dozen sets of funny operations transformed the gibberish into human-readable text.
I'll print the stack to make it easier to copy:  
![image](https://github.com/s24306/CTF/assets/91730770/0cbd3313-35e3-4411-a639-b98f63fe79c3)  

**hkcert23{s0m3t1m3_i7s_e4si3r_70_dyn4m1c_r3v_ju5t_p4tch&l0ok_4t_m3mory}**  
A very meaningful flag name, and I agree with it 100%.
