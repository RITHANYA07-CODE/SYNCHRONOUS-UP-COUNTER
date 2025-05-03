### SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

**Procedure**

Step 1: Open Quartus II in your laptop. 

Step 2: Write code to implement SR flipflop using verilog and validating their functionality using their functional tables. 

Step 3: Run compilation to check for errors. 

Step 4: Open waveform output and load input values. 

Step 5: Run simulation to get the output. 

Step 6: Open in RTL viewers to get RTL diagram output.


**PROGRAM**
UPCOUNTER : 
```
module ex11(out,clk,rst);
input clk,rst;
output reg [3:0]out;
always @ (posedge clk)
begin
if(rst)
out<=0;
else
out <= out+1;
end
endmodule
```
DOWNCOUTNER :
```
module ex11(out,clk,rst);
input clk,rst;
output reg [3:0]out;
always @ (posedge clk)
begin
if(rst)
out<=0;
else
out <= out+1;
end
endmodule
```
/*
Developed by: Rithanya D
RegisterNumber: 212224050038
*/

**RTL LOGIC UP COUNTER**
UPCOUNTER:
![image](https://github.com/user-attachments/assets/0a49ce91-d8f0-44c3-8544-bd0ba2bb4109)

DOWNCOUNTER:
![image](https://github.com/user-attachments/assets/918e3b48-cfb3-4e76-ad08-acac1278bc3a)


**TIMING DIAGRAM FOR IP COUNTER**
UPCOUNTER:
![image](https://github.com/user-attachments/assets/41f2700a-36b2-433a-ad41-1adcf30646d0)

DOWNCOUNTER:
![image](https://github.com/user-attachments/assets/d701a02b-b299-4847-9090-4a6ed2208605)
![image](https://github.com/user-attachments/assets/fe47118b-3c54-4602-ad02-81a6200f51cf)



**TRUTH TABLE**


UPCOUNTER:


![image](https://github.com/user-attachments/assets/c40df89a-af3d-49f2-bf82-ec189f6ff6a6)

DOWNCOUNTER:


![image](https://github.com/user-attachments/assets/32dd86b8-8a13-4d9a-9a4c-48b99b9de385)
![image](https://github.com/user-attachments/assets/e5c6e076-4a50-4a27-bc7e-9f2f87e44bb8)



**RESULTS**
Thus, the program to implement a 4-bit synchronous up counter using Verilog and to validate its functionality using its truth table was successfully completed.
