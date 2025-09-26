> **Important Note:** This simulation is designed for desktop view only. For the best experience, please use a desktop monitor with a minimum resolution of 1280x720 pixels. The simulation may not function properly on smaller screens like mobile devices or tablets.

### 1. Understanding the Simulation

This simulation helps you learn about D-Flip-Flop implementation in Verilog:

- **D-Flip-Flop Design:** A sequential circuit that stores a single bit of data and transfers it to the output on a clock edge.
- The simulation covers both positive and negative edge-triggered D-Flip-Flops:
  - **Positive Edge:** Output Q gets the value of input D at the rising edge of CLK
  - **Negative Edge:** Output Q gets the value of input D at the falling edge of CLK
- It demonstrates sequential logic behavior using clocked always blocks.

### 2. Getting Started

1. Enter your module name and testbench name in the respective fields:
   - Module names must follow [Verilog naming conventions](https://www.chipverify.com/verilog/verilog-syntax).
   - Only letters, numbers, and underscores are allowed (no hyphens or special characters).
   - Testbench name must end with '_tb'.

### 3. Building the Verilog Module

1. In the first column, arrange the code blocks in the correct order by dragging and dropping them:
   - The code block that defines inputs, outputs, and module name should be placed first
   - Followed by the code block that defines the module functionality
   - Finally, the end of module block

2. Select the appropriate signals:
   - Inputs: D (data input), CLK (clock input)
   - Output: Q (data output)

3. Define the functionality using the always block:
   - Select the condition of always block as 'posedge CLK' for positive edge flip-flop or 'negedge CLK' for negative edge flip-flop
   - The Q output must be assigned the value of D at the chosen clock edge
   - Fill in the LHS and RHS of the assignment keeping in mind what value should be assigned at the clock edge
   - The assignment operator must be '<=' (not '=') because for sequential storage behavior, we always need to select the non-blocking assignment operator (<=)

### 4. Creating the Testbench

1. In the second column, arrange the testbench code blocks in the correct order:
   - Testbench name definition
   - Signal declarations (reg for inputs, wire for outputs)
   - Module instantiation
   - Input and clock wave definitions
   - End of module

2. Define the testbench signals:
   - `reg D, CLK; wire Q` (Q is the output here)

3. Connect the ports correctly in the module instantiation:
   - Enter the name of the verilog module you have earlier coded
   - Select the arguments in the same order as you have chosen in the D flip-flop module
   - **Important:** Maintain correct order - incorrect order like (D, Q, CLK) would make D, Q as inputs and CLK as output which is not desired
   - Select the input D wave as per your choice from the options given in the dropdown list

### 5. Validation and Observation

1. Click the "Validate" button to check your code.
2. The observation column will show:
   - Error messages in red if there are mistakes. Refer to the [Troubleshooting](#6-troubleshooting) section below for dealing with the Error messages.
   - A truth table for the input D wave you have selected if the code is correct.
3. If you need to start over, click the "Reset" button to shuffle the code blocks.

#### Verilog Syntax Reference

- For detailed Verilog syntax rules, refer to the [Verilog Syntax Guide](https://www.chipverify.com/verilog/verilog-syntax).
- For module and testbench examples, visit [ASIC World Verilog Tutorial](https://www.asic-world.com/verilog/veritut.html).

### 6. Troubleshooting

If you see error messages, carefully check:

- Module and testbench names follow the naming rules.
- Code blocks are in the correct order.
- D and CLK are properly declared as inputs, Q as output.
- The always block condition matches your choice (posedge or negedge CLK).
- Non-blocking assignment (<=) is used for sequential logic.
- Port connections are properly defined in the module instantiation.
- Input D wave is selected from the dropdown options.

Additional tips:

- Use the Reset button to start fresh if needed.
- Observe the fluctuations in input wave and corresponding expected and observed output Q wave.
- Verify the flip-flop behavior matches expected timing for the selected clock edge.

#### Important Reminders

- Verilog is case-sensitive.
- All signals must be properly declared before use.
- Testbench signals must match the module ports.
- Code blocks must be in the correct order for the simulation to work.
- Use non-blocking assignment (<=) for sequential logic in always blocks.
- The flip-flop behavior depends on the chosen clock edge (posedge or negedge).
- Ensure correct port order in module instantiation to avoid signal misconnection.
