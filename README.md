# Experiment--04-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure
Create a New Project:

Open Quartus and create a new project by selecting "File" > "New Project Wizard."
Follow the wizard's instructions to set up your project, including specifying the project name, location, and target device (FPGA).
Create a New Design File:

Once the project is created, right-click on the project name in the Project Navigator and select "Add New File."
Choose "Verilog HDL File" or "VHDL File," depending on your chosen hardware description language.
Write the Combinational Logic Code:

Open the newly created Verilog or VHDL file and write the code for your combinational logic.
Compile the Project:

To compile the project, click on "Processing" > "Start Compilation" in the menu.
Quartus will analyze your code, synthesize it into a netlist, and perform optimizations based on your target FPGA device.
Analyze and Fix Errors:

If there are any errors or warnings during the compilation process, Quartus will display them in the Messages window.
Review and fix any issues in your code if necessary.
View the RTL diagram.
Verification:

Click on "File" > "New" > "Verification/Debugging Files" > "University Program VWF".
Once Waveform is created Right Click on the Input/Output Panel > " Insert Node or Bus" > Click on Node Finder > Click On "List" > Select All.
Give the Input Combinations according to the Truth Table amd then simulate the Output Waveform.

## Program:
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.<br>
Developed by: sivaram R
RegisterNumber:  212222100050
## HALF SUBTRACTER:
```
module EX04(a,b,difference,borrow);
input a,b;
output difference,borrow;
wire x;
xor (difference,a,b);
not (x,a);
and (borrow,x,b);
endmodule
```
## FULL SUBTRACTOR:
```
module FullSub04(a,b,bin,difference,borrow);
input a,b,bin;
output difference,borrow;
wire p;
assign difference=((a^b)^bin);
not (p,a);
assign borrow=((p&b)|(p&bin)|(b&bin));
endmodule
```

## RTL DIAGRAM:
## HALF SUBTRACTOR:
![HALF SUB](https://github.com/sivaram-R/Experiment--04-Half-Subtractor-and-Full-subtractor/assets/121165794/35be1aa3-4cab-4ba1-8ce0-5e2dc7b3094e)
## FULL SUBTRACTOR:
![FULL SUB](https://github.com/sivaram-R/Experiment--04-Half-Subtractor-and-Full-subtractor/assets/121165794/48374200-66d5-4881-a297-18cb38631211)

## TRUTH TABLE:
## HALF SUBTRACTOR:
![SUB TT](https://github.com/sivaram-R/Experiment--04-Half-Subtractor-and-Full-subtractor/assets/121165794/eba85315-31f7-4c25-8659-006059939dd9)
## FULL SUBTRACTOR:
![FULL TT](https://github.com/sivaram-R/Experiment--04-Half-Subtractor-and-Full-subtractor/assets/121165794/c1e1fbf1-3b67-4332-b037-de3f01dc2a44)

## OUTPUT:
## HALF SUBTRACTOR:
![OP HALF](https://github.com/sivaram-R/Experiment--04-Half-Subtractor-and-Full-subtractor/assets/121165794/4361d01b-3fde-429d-9575-385dc2f4583b)
## FULL SUBTRATCTOR:
![OP FULL](https://github.com/sivaram-R/Experiment--04-Half-Subtractor-and-Full-subtractor/assets/121165794/7a6852e0-fb11-43bd-a017-f56b75954058)

## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
