### Ex. No. 6
#### Date: 19.5.23
# Implementation of 4 bit synchronous counters using Verilog HDL
## Aim:
To design and implement the following synchronous counters using Verilog HDL.
1.	UP counter
2.	DOWN counter
## Components Required:
1.	Laptop with Quartus software and modelsim software.
## Theory:
A Synchronous counter is the counter in which the clock input with all the flip-flops uses the same source and produces the output at the same time.
## UP Counter
### State table
![image](https://github.com/rvinifa/Counter/assets/133735746/ede78598-89fd-4aeb-9d82-329e45d05f2a)

### K-map Simplification

   ![image](https://github.com/rvinifa/Counter/assets/133735746/21554263-611b-44a2-8f78-7b2220ef5a05)
   
### Logic Diagram
![image](https://github.com/rvinifa/Counter/assets/133735746/2ab715d3-f6d5-4cf6-8fda-8fa666518c0b)



## Down Counter
### State Table
 ![image](https://github.com/rvinifa/Counter/assets/133735746/5be9585c-11aa-47c3-beaf-0dca916750f2)

### K-map simplification
 ![image](https://github.com/rvinifa/Counter/assets/133735746/dde7bc60-3a4f-4fb7-811d-f420cb74bdef)

### Logic Diagram
 ![image](https://github.com/rvinifa/Counter/assets/133735746/64e2d7b7-1646-4ca7-bc6c-c7c10881223c)

## Procedure:
1.	Type the program in Quartus software.
2.	Compile and run the program.
3.	Generate the RTL schematic and save the logic diagram.
4.	Create nodes for inputs and outputs to generate the timing diagram.
5.	For different input combinations, generate the timing diagram.


## Program:
## UP Counter
module exp6(clk,q1,q2,q3,q4);
input clk;
output reg q1,q2,q3,q4;
always @(posedge clk)
begin
q4=(q1&q2&q3)^q4;
q3=(q1&q2)^q3;
q2=q1^q2;
q1=1^q1;
end
endmodule
## DOWN Counter
module ex6b(clk,q1,q2,q3,q4);
input clk;
output reg q1,q2,q3,q4;
always@ (posedge clk)
begin
 q4=((~q1)&(~q2)&(~q3))^q4;
 q3=((~q1)&(~q2))^q3;
 q2=(~q1)^q2;
 q1=1^q1;
end
endmodule 
## RTL Schematic:
## UP Counter
![244741821-cc33d135-1675-4b89-9dd0-a28645df7b43](https://github.com/NaveenSivamalai/Counter/assets/123792574/247810fe-3ea2-4799-a7a3-1e18a65aad60)

## DOWN Counter
![244741990-48eb23ce-80e8-4338-84ac-efb7b887e75b](https://github.com/NaveenSivamalai/Counter/assets/123792574/7420fe14-d9c2-4e47-a251-1269105b8a5e)


## Timing Diagram:
## UP Counter
![244741885-3b7f4219-1ddd-4a88-925a-ea89ae1a9460](https://github.com/NaveenSivamalai/Counter/assets/123792574/895e13a5-c50c-4ee4-9609-0291c4eeb2e0)

## DOWN Counter
![244742045-75bb0fed-123a-442c-a018-d3534037cccb](https://github.com/NaveenSivamalai/Counter/assets/123792574/c3890444-4db9-4802-80d3-3b693d1e652f)

## Result:
Thus the Synchronous UP and DOWN counters using T flipflops are implemented and the state tables are verified.

