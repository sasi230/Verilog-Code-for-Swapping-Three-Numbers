                                             # Verilog-Code-for-Swapping-Three-Numbers
Aim
To design and simulate a Verilog HDL code for swapping the values of three numbers without using any temporary variables, and verify the correctness of the swapping operation through a testbench using the Vivado 2023.1 simulation environment.

Apparatus Required
Vivado 2023.1 or equivalent Verilog simulation tool.

Procedure
Launch Vivado 2023.1:

Open Vivado and create a new project.
Write the Verilog Code for Swapping:

Write the Verilog code that swaps the values of three numbers (a, b, and c) using basic arithmetic or bitwise operations without using temporary variables.
Create the Testbench:

Write a testbench to simulate the swapping operation. The testbench should initialize three numbers, trigger the swapping module, and check if the values are swapped correctly.
Add the Verilog Files:

Add the Verilog module and the testbench file to the Vivado project.
Run Simulation:

Run the behavioral simulation in Vivado to verify the swapping operation.
Observe the Waveforms:

Examine the waveform to confirm that the values of the three numbers are swapped as expected.
Save and Document Results:

Capture the waveform output and include the results in your report for verification.

Verilog Code:

// swap_three_numbers.v
```
module swap_three_numbers(
    input [7:0] a, b, c,   
    output reg [7:0] a_out, b_out, c_out 
);

    always @(*) begin
        a_out = b;   
        b_out = c;   
        c_out = a;   
    end

endmodule
```



Testbench for Swapping Three Numbers:

// swap_three_numbers_tb.v
`timescale 1ns / 1ps
```
module tb_swap_three_numbers;

    // Testbench variables
    reg [7:0] a, b, c;    // Inputs: 8-bit numbers
    wire [7:0] a_out, b_out, c_out; // Outputs: swapped numbers

    // Instantiate the swap module
    swap_three_numbers uut (
        .a(a), 
        .b(b), 
        .c(c),
        .a_out(a_out), 
        .b_out(b_out), 
        .c_out(c_out)
    );

    // Test procedure
    initial begin
        // Initial values for a, b, and c
        a = 8'd10;
        b = 8'd20;
        c = 8'd30;

        // Monitor the values
        $monitor("Time = %0t : a = %0d, b = %0d, c = %0d, a_out = %0d, b_out = %0d, c_out = %0d",
                  $time, a, b, c, a_out, b_out, c_out);

        // Wait for 10 time units and then check the swap
        #10;

        // Change input values for another swap test
        a = 8'd50;
        b = 8'd60;
        c = 8'd70;
        
        #10;
        
        // End the simulation
        $finish;
    end

endmodule
```
OUTPUT:
![Screenshot 2024-10-04 211852](https://github.com/user-attachments/assets/eec40af9-f50d-4866-86cd-aaf1df3bdddc)



Conclusion
In this experiment, a Verilog HDL code for swapping three numbers was designed and successfully simulated. The testbench verified the swapping operation, showing that the values of three input numbers (a, b, and c) were swapped correctly without the use of temporary variables. This experiment demonstrated the effectiveness of Verilog in implementing logical operations and control mechanisms such as swapping values. The simulation results confirm the correct functionality of the design.
