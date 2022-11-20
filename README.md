# Exp-6-Synchornous-counters - up counter and down counter 
### AIM: To implement 4 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## UP COUNTER 
The counter is a digital sequential circuit and here it is a 4 bit counter, which simply means it can count from 0 to 15 and vice versa based upon the direction of counting (up/down). 

The counter (“count“) value will be evaluated at every positive (rising) edge of the clock (“clk“) cycle.
The Counter will be set to Zero when “reset” input is at logic high.
The counter will be loaded with “data” input when the “load” signal is at logic high. Otherwise, it will count up or down.
The counter will count up when the “up_down” signal is logic high, otherwise count down

Since we know that binary count sequences follow a pattern of octave (factor of 2) frequency division, and that J-K flip-flop multivibrators set up for the “toggle” mode are capable of performing this type of frequency division, we can envision a circuit made up of several J-K flip-flops, cascaded to produce four bits of output.
The main problem facing us is to determine how to connect these flip-flops together so that they toggle at the right times to produce the proper binary sequence.
Examine the following binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1:
Binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1.

Note that each bit in this four-bit sequence toggles when the bit before it (the bit having a lesser significance, or place-weight), toggles in a particular direction: from 1 to 0.



 
 

Starting with four J-K flip-flops connected in such a way to always be in the “toggle” mode, we need to determine how to connect the clock inputs in such a way so that each succeeding bit toggles when the bit before it transitions from 1 to 0.

The Q outputs of each flip-flop will serve as the respective binary bits of the final, four-bit count:

 
 

Four-bit “Up” Counter
![image](https://user-images.githubusercontent.com/36288975/169644758-b2f4339d-9532-40c5-af40-8f4f8c942e2c.png)



## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.
![image](https://user-images.githubusercontent.com/36288975/169644844-1a14e123-7228-4ed8-81a9-eb937dff4ac8.png)


4-bit Count Down Counter
### Procedure
~~~
1.Create module projectname(input ,output) to start the verilog programming.
2.Create a if loop condition to increase the count in counter_up function.
3.Similarly, create another loop for the down counter.
4.End the verilog program using keyword endmodule.
5.Get the timing diagram and RTL realization diagram for respective Counters.
~~~


### PROGRAM 
~~~
Program for flipflops  and verify its truth table in quartus using Verilog programming.
Developed by:NAVEENKUMAR V 
RegisterNumber:  212221230068
~~~
### UP COUNTER
~~~
module upc(clk,reset,upcounter);
input clk,reset;
output reg[0:2] upcounter;
always@(posedge clk or posedge reset)
begin 
if(reset)
upcounter= 3'b 000;
else
upcounter=upcounter+1;
end 
endmodule 
~~~

### RTL LOGIC UP COUNTER
![image](https://user-images.githubusercontent.com/94165322/202895648-c4fb90a5-790f-47f9-bb8e-d84bfee5cdf4.png)

### TIMING DIAGRAMS FOR COUNTER
![image](https://user-images.githubusercontent.com/94165322/202895670-00c4e8d6-26df-4883-99e5-7ceaf2a64fa3.png)

### TRUTH TABLE
![image](https://user-images.githubusercontent.com/94165322/202895678-9d0d91d4-7648-4214-86ce-7e42afb90fc4.png)

### DOWN COUNTER
~~~
module dc(clock,reset,up);
input clock,reset;
output reg[2:0] up;
always@(posedge clock or posedge reset)
begin
if(reset)
up=3'b 111;
else
up=up-1;
end
endmodule
~~~

### RTL LOGIC DOWN COUNTER:
![image](https://user-images.githubusercontent.com/94165322/202895695-f7cb2a7d-4074-4162-b3dd-468d57596ed0.png)

### TIMING DIAGRAM FOR COUNTER:
![image](https://user-images.githubusercontent.com/94165322/202895706-0ee60787-f269-4aac-8201-c59a558cf3f8.png)

### TRUTH TABLE:
![image](https://user-images.githubusercontent.com/94165322/202895719-58fe5a84-cac3-45d9-95f1-8c6f2ef40191.png)


### RESULTS 
Thus 4 bit up and down counters is implemented and its functionality is validated.
