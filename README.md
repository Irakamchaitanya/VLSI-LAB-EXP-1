# VLSI-LAB-EXPERIMENTS

# AIM:
To simulate and synthesis Logic Gates,Adders and Subtractor using vivado 2023.2.

# APPARATUS REQUIRED:
vivado 2023.2

# PROCEDURE:
STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation adn then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table.

# Logic Diagram :
# Logic Gates:
![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/161814091/61bff1d1-9f3e-4902-9cae-56356b913b64)
# Half Adder:
![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/161814091/388546dd-3048-4cd6-95c8-ae9e24e5b81b)
# Full adder:
![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/161814091/7aa97b6d-c59a-4c0e-8aea-9ab46edee61c)
# Half Subtractor:
![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/161814091/8b0a2591-66bf-4086-a630-af19f7f6d68f)
# Full Subtractor:
![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/161814091/081357af-0f79-484f-9fa0-708ab51a00d3)
# 8 Bit Ripple Carry Adder:
![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/161814091/a07f599e-9836-4ce4-98c7-2752dc6e98e8)
# VERILOG CODE:
module logic(a,b,andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate );

input a,b;

output andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate;

and(andgate,a,b);

or(orgate,a,b);

xor(xorgate,a,b);

nand(nandgate,a,b);

nor(norgate,a,b);

xnor(xnorgate,a,b);

not(notgate,a);

endmodule

# HALF ADDER:
module HalfAdder(a,b,sum,carry);

input a,b;

output sum,carry;

xor (sum,a,b);

and (carry,a,b);

endmodule

# FULL ADDER:
module FA(a,b,cin,sum,cout);

input a,b,cin;

output sum,cout;

wire w1,w2,w3;

xor g1(w1,a,b);

and g2(w2,w1,cin);

and g3(w3,a,b);

xor g4(sum,w1,cin);

or g5(cout,w2,w3);

endmodule

# HALF SUBTRACTOR:
module halfsubtractor(a,b,diff,borrow);

input a,b;

output diff,borrow;

xor g1(diff,a,b);

and g2(borrow,~a,b);

endmodule

# FULL SUBTRACTOR:
module full_sub(a,b,bin,diff,borrow);

input a,b,bin;

output diff,borrow;

wire w1,w2,w3;

xor g1(w1,a,bin);

and g2(w2,~a,b);

xor g3(diff,w1,bin);

or g4(borrow,w2,w3);

and g5(w3,~w1,bin);

endmodule

# 8 BIT RIPPLE CARRY ADDER:
module fa(a,b,c,sum,carry);

input a,b,c;

output sum,carry;

assign sum = a^b^c;

assign carry=(a&b)|(b&c)|(c&a);

endmodule

module rca(a,b,cin,sum,cout);

input [7:0]a,b;

input cin;

output [7:0]sum;

output cout;

wire c1,c2,c3,c4,c5,c6,c7;

fa fa1(a[0],b[0],cin,sum[0],c1);

fa fa2(a[1],b[1],c1,sum[1],c2);

fa fa3(a[2],b[2],c2,sum[2],c3);

fa fa4(a[3],b[3],c3,sum[3],c4);

fa fa5(a[4],b[4],c4,sum[4],c5);

fa fa6(a[5],b[5],c5,sum[5],c6);

fa fa7(a[6],b[6],c6,sum[6],c7);

fa fa8(a[7],b[7],c7,sum[7],cout);

endmodule

# OUTPUT:
# LOGIC GATES:
![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/161814091/31082d76-e370-4a5e-8d98-6e1a0532d090)
# HALF ADDER:
![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/161814091/0cbf06c7-5412-4e27-bac5-d9a90f176378)
# FULL ADDER:
![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/161814091/77cb1832-6aef-41a3-916f-1264bca70ebe)
# HALF SUBTRACTOR:
![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/161814091/afd3ab77-ee9d-4073-8c80-48fc316dd318)
# FULL SUBTRACTOR:
![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/161814091/2f7072bd-e8f9-426f-9b73-1503c8a22055)
# 8 BIT RIPPLE CARRY ADDER:
![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/161814091/2e07f9b6-eacb-480c-9d3a-5e85ece3160f)
# RESULT:
Thus the simulation and synthesis of Logic Gates,Adders and Subtractors using vivado has been sucessfully executed and verified .






