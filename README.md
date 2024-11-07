# BOOLEAN_FUNCTION_MINIMIZATION
### Name       :R.LOKESHWARAN
### Ref No     :24011606
### Experiment :BOOLEAN FUNCTION IMPLEMENTATION

#### AIM

To implement the given logic function verify its operation in Quartus using Verilog programming.

F1= A’B’C’D’+AC’D’+B’CD’+A’BCD+BC’D 

F2=xy’z+x’y’z+w’xy+wx’y+wxy

#### EQUIPMENT REQUIRED

Hardware – PCs, Cyclone II , USB flasher
Software – Quartus prime

#### THEORY
Implementing Boolean functions in Quartus using Verilog programming involves a systematic approach to design, synthesize, and verify digital logic functions. Here, we’ll cover the theoretical background and implementation of Boolean functions using Verilog, focusing on the functions:

𝐹1=𝐴′𝐵′𝐶′𝐷′+𝐴𝐶′𝐷′+𝐵′𝐶𝐷′+𝐴′𝐵𝐶𝐷+𝐵𝐶′𝐷 𝐹2=𝑥𝑦′𝑧+𝑥′𝑦′𝑧+𝑤′𝑥𝑦+𝑤𝑥′𝑦+𝑤𝑥𝑦

Theory of Boolean Logic in Digital Circuits In digital electronics, Boolean functions describe the relationships between inputs and outputs using binary logic (0s and 1s). These functions are often represented in Sum of Products (SOP) form, where each term (or "product") represents a specific combination of inputs that will produce a high (1) output. The SOP form uses the following logic operations:

AND Operation: Produces a high output only if all inputs are high. OR Operation: Produces a high output if any of the inputs are high. NOT Operation: Produces the opposite of the input (inverts it).

In SOP form, the function is an OR of multiple AND terms, with each AND term representing a unique combination of the inputs that yield a true (1) output.

Analyzing the Boolean Functions F1 and F2 Function F1 Analysis The function F1 is given as: 𝐹1=𝐴′𝐵′𝐶′𝐷′+𝐴𝐶′𝐷′+𝐵′𝐶𝐷′+𝐴′𝐵𝐶𝐷+𝐵𝐶′𝐷 Terms:

𝐴′𝐵′𝐶′𝐷′:True when A,B,C,𝐷 are all zero.
AC′D′:True when A is 1, C and D are 0.
𝐵′𝐶𝐷′:True when B is 0, C is 1, D is 0.
𝐴′𝐵𝐶𝐷:True when A is 0, B,C, and D are 1.
𝐵𝐶′𝐷:True when B is 1, C is 0, D is 1. Each terms represents a specific input combination that yields an output of 1 for F1. Function F2 Analysis the function F2 given as: 𝐹2=𝑥𝑦′𝑧+𝑥′𝑦′𝑧+𝑤′𝑥𝑦+𝑤𝑥′𝑦+𝑤𝑥𝑦 Terms:
xy'z:True when xix 1,y is 0,z is 1.
x'y'z:True when x andd y are 0, z is 1.
w'x'y:True when w is 0,x and y are 1.
wx'y:True when w,y are 1, and x is 0.
wxy:True when w,x,y are 1. Each of these combination results in an output of 1 for F2.
Implementing Boolean Functions in Verilog To implement these functions in Verilog, we use logical operators to replicate the behavior of AND, OR, and NOT operations.

AND is represented as &. OR is represented as |. NOT is represented as ~.

And start the verilog code for F1 and F2

Quartus Simulation and Verification Once the Verilog code is written, we can verify the logic using Quartus, an FPGA design and simulation tool.

Steps in Quartus

Create a New Project: Open Quartus, create a new project, and add the Verilog file.

Compilation: Compile the Verilog code to synthesize it into logic gates. Quartus will map the Boolean functions to FPGA resources, ensuring that the code is correctly interpreted.

Testing with a Testbench: To verify the function, create a testbench file that applies various combinations of inputs and observes the outputs F1 and F2.

Simulation: Open the simulation tool in Quartus and select the testbench.Run the simulation and observe the waveforms. Each input combination should produce the expected result for F1 and F2 as per the truth table.

Verify Results: Compare the output waveforms against the expected values to confirm correct operation.

Conclusion: By using Quartus and Verilog programming, we can efficiently design, implement, and verify Boolean functions like F1 and F2. Quartus provides a platform for synthesizing the Verilog code into hardware, while simulation allows us to test and ensure that the functions behave as expected across all input combinations. This approach is essential for designing reliable digital systems.

####  PROCEDURE

1.	Type the program in Quartus software.

2.	Compile and run the program.

3.	Generate the RTL schematic and save the logic diagram.

4.	Create nodes for inputs and outputs to generate the timing diagram.

5.	For different input combinations generate the timing diagram.


#### PROGRAM

##### module BOOLEANFUNCTION(a,b,c,d,w,x,y,z,f1,f2);
##### input a,b,c,d,w,x,y,z;
##### output f1,f2;
##### wire x1,x2,x3,x4,x5,x6,x7,x8,x9,x10;
##### assign x1=(~a)&(~b)&(~c)&(~d);
##### assign x2=(a)&(~c)&(~d);
##### assign x3=(~b)&(c)&(~d);
##### assign x4=(~a)&(b)&(c)&(d);
##### assign x5=(b)&(~c)&(d);
##### assign x6=(x)&(~y)&(z);
##### assign x7=(~x)&(~y)&(z);
##### assign x8=(~w)&(x)&(y);
##### assign x9=(w)&(~x)&(y);
##### assign x10=(w)&(x)&(y);
##### assign f1=x1|x2|x3|x4|x5;
##### assign f2=x6|x7|x8|x9|x10;
##### endmodule

##### TRUTH TABLE

![WhatsApp Image 2024-11-07 at 01 32 59_b467b08d](https://github.com/user-attachments/assets/aa6d6c55-c4fb-49dc-ad00-702d750bf8a3)

![WhatsApp Image 2024-11-07 at 01 33 21_272f6939](https://github.com/user-attachments/assets/38f5bb0c-5384-4626-aba8-0a76afa97c4a)

#### RTL OUTPUT
![image](https://github.com/user-attachments/assets/624a3db5-b117-4a2c-b8f0-58b0b3beadde)

#### OUTPUT WAVEFORM

![Screenshot 2024-11-07 014737](https://github.com/user-attachments/assets/52412442-96b7-4a01-8e91-93ca60f5926d)

#### RESULT

Thus the given logic functions are implemented using and their operations are verified using Verilog programming.

