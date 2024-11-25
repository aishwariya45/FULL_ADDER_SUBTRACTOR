# FULL_ADDER_SUBTRACTOR

Implementation-of-Full-Adder-and-Full-subtractor-circuit

**AIM:**

To design a Full Adder and Full Subtractor circuit and verify its truth table in Quartus using Verilog programming.

**Equipments Required:**

Hardware – PCs, Cyclone II , USB flasher

Software – Quartus prime

**Full Adder and Full Subtractor**

**Full Adder**

Full adder is a digital circuit used to calculate the sum of three binary bits. It consists of three inputs and two outputs. Two of the input variables, denoted by A and B, represent the two significant bits to be added. The third input, Cin, represents the carry from the previous lower significant position. Two outputs are necessary because the arithmetic sum of three binary digits ranges in value from 0 to 3, and binary 2 or 3 needs two digits. The two outputs are sum and carry.

Sum =A’B’Cin + A’BCin’ + ABCin + AB’Cin’ = A ⊕ B ⊕ Cin 

Carry = AB + ACin + BCin

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/0f30ba51-5ffb-4198-845f-18e054f675e7)

**Figure -1 FULL ADDER**

**Full Subtractor**

A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow.

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/02b24f51-ab51-4304-9ad6-7b81ffc1ead5)

Diff = A ⊕ B ⊕ Bin 

Borrow out = A'Bin + A'B + BBin

**Truthtable**

**Procedure**

Write the detailed procedure here

**Program:**
```
/* Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming. Developed by:aishwariya.s RegisterNumber:24900840
module exp4(sum, cout, a, b, cin);
    output sum;
    output cout;  // Corrected the name here
    input a;
    input b;
    input cin;

    // Internal nets
    wire s1, c1, c2;

    // Instantiate logic gate primitives
    xor(s1, a, b);
    and(c1, a, b);
    xor(sum, s1, cin);
    and(c2, s1, cin);
    or(cout, c2, c1);  // Consistent with the output port name

endmodule

module exp41(df, bo, a, b, bin);
    output df;
    output bo;
    input a;
    input b;
    input bin;
    wire w1, w2, w3;

    // XOR for difference
    assign w1 = a ^ b;
    assign w2 = (~a & b);
    assign w3 = (~w1 & bin);
    assign df = w1 ^ bin;
    assign bo = w2 | w3;

endmodule

*/
```

**RTL Schematic**
![exp4](https://github.com/user-attachments/assets/811c5591-11ee-4c5d-badf-21fa14f8e09a)


**Output Timing Waveform**
![Screenshot 2024-11-25 161804](https://github.com/user-attachments/assets/37e067a9-85b3-4072-ac9d-e2661764ea19)


**Result:**

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



