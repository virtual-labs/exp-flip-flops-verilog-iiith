# Verilog Design of Negative and Positive edged D-Flip-Flop

## Modules Required -

- Verilog Module
- Verilog Test bench

## Code -

### Verilog Module -  

- The code block that defines inputs, outputs, module name should be placed first, followed by the code block that defines the module functionality and then finally the end of module block.
- Drag and drop the code blocks to arrange them in the order mentioned above.
- Now enter a name for the verilog module. Make sure that the name begins with alphabets and can only include alphanumeric characters and '_' character without any spaces or other special characters in between.
- Select the inputs as D, CLK and the output as Q.
- Now, to define the functionality of the module, the always block has to be filled. The Q input has to be assigned the value of D at the positive edge of the CLK for a positive edge flip flop and at the negative edge of CLK for a negative edged flip flop.
- Select the condition of always block as 'posedge CLK' or 'negedge CLK' accordingly.
- Fill in the LHS and RHS of the assignment accordingly keeping in mind what value sould be assigned to whom at the clock edge.
- The assignment operator must be selected as '<=' and not '=' because for a sequential storage behaviour, we always need to select the non-blocking assignment operator (<=).

### Verilog Test Bench -

- The code block that defines test bench name should be placed first, followed by the code block that declares input, output registers and wires, then the block that instantiates the D Flip Flop module, then the blocks that define the input and clock waves and finally the end of module block.
- Drag and drop the code blocks to arrange them in the order mentioned above.
- Now enter a name for the verilog test bench. Make sure that the name begins with alphabets and can only include alphanumeric characters and '_' character without any spaces or other special characters in between and it does not match with the verilog module name you have entered earlier.
- Then declare D and CLK as registers and Q as a wire. (*Q is the output here*).
- Now instantiate the D flip flop module by entering the name of the verilog module you have earlier coded. Select the arguments in the same order as you have chosen in the D flip Flop module. The order in which you give the arguments here, the inputs and outputs will be used in the same order in the module. For example, you give arguments in the module instantiation in the test bench in the order D,Q,CLK, then the inputs of the module will become D,Q and the output will become CLK which is not desired.
- Finally select the input D wave as per your choice from the options given in the drop down list.

## Observations -

- On clicking "validate" option after completing the code (assuming everything is filled correctly) you should see a "Success" message and a truth table for the input D wave you have selected, under the observations section.
- Observe the fluctuations in input wave and the corresponding expected and observed output Q wave.
