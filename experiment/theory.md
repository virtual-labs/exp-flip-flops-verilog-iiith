This page provides an overview of Verilog, its significance, and practical examples of digital design using Verilog. We will explore three fundamental designs in this experiment:

1. **T-Flip Flop**
2. **Counter**
3. **T-Flip Flop Using D-Flip Flop**

---

Verilog is a hardware description language (HDL) developed to model electronic systems. It enables designers to describe the structure and behavior of digital circuits, facilitating simulation, synthesis, and verification. The modular nature of Verilog allows for efficient design, testing, and reuse of code.

---

## 1. T-Flip Flop

The Verilog code for a T-Flip Flop is shown below, accompanied by an explanation of its components:

<p align="center">
  <img src="images/t.jpg" alt="T-Flip Flop Verilog Code">
</p>

### Key Concepts

- **Module:**  
  A module is the fundamental building block in Verilog. It can represent a single element or a collection of lower-level design blocks. Modules encapsulate functionality and expose interfaces through input and output ports, allowing for abstraction and reuse.

- **Module Name:**  
  The module name is user-defined and is used to instantiate the module elsewhere in the design. Instantiation is demonstrated in the third example.

- **Module Arguments:**  
  Similar to function arguments in C, module arguments specify the input and output ports used for communication with other modules or the external environment.

- **Input/Output Ports:**  
  These ports facilitate data transfer into and out of the module. All arguments listed in the module declaration must be defined as either input or output within the module.

- **Data Types:**  
  In this example, the `reg` data type is used. Other data types, such as `wire`, will be introduced in subsequent examples. Refer to the chart below for an overview of Verilog data types:

  <p align="center">
    <img src="images/data.jpg" alt="Verilog Data Types">
  </p>

- **Always Block:**  
  The `always` block contains statements that execute repeatedly, triggered by changes in specified signals (e.g., clock or reset).

- **Posedge Clock:**  
  The `posedge` (positive edge) of the clock triggers the execution of statements within the `always` block, corresponding to a transition from low to high voltage.

- **Negedge Reset:**  
  The `negedge` (negative edge) of the reset signal asynchronously sets the output to zero, regardless of the clock.

- **Operators and Lexical Conventions:**  
  Operators such as `~` (bitwise NOT) and `!` (logical NOT) are used in Verilog. The chart below summarizes various operators and conventions:

  <p align="center">
    <img src="images/lex.jpg" alt="Verilog Operators and Lexical Conventions">
  </p>

- **Loops:**  
  Verilog supports control structures such as `for`, `if-else`, and `while`, similar to C. These structures use `begin` and `end` to define statement blocks.

- **Blocking and Non-Blocking Assignments:**
  - **Blocking (`=`):** Statements execute sequentially.
  - **Non-Blocking (`<=`):** Statements execute concurrently.  
    For example:
    ```
    a = b;
    b = a;
    ```
    Both `a` and `b` will have the value of `b`.  
    Using non-blocking assignment:
    ```
    a <= b;
    b <= a;
    ```
    The values are swapped simultaneously.

---

## 2. Counter

The Verilog code for a counter is provided below, with explanations for each part:

<p align="center">
  <img src="images/c.jpg" alt="Counter Verilog Code">
</p>

### Additional Notes

- **Assign Statement:**  
  The `assign` keyword is used for continuous assignment. For example, `assign Q = tmp;` ensures that `Q` is updated immediately whenever `tmp` changes, regardless of execution sequence.

---

## 3. T-Flip Flop Using D-Flip Flop

The Verilog code for implementing a T-Flip Flop using a D-Flip Flop is shown below:

<p align="center">
  <img src="images/td.jpg" alt="T-Flip Flop using D-Flip Flop Verilog Code">
</p>

### Key Concepts

- **Module Instantiation:**  
  Modules are not defined within other modules; instead, they are instantiated (called) as needed. The module is referenced by its original name, but each instance must have a unique identifier. For example, the module `D_FF` is instantiated as `dff0`.

- **Verilog Primitives:**  
  Verilog provides built-in primitives such as `not`. In `not (d, q);`, `d` is the output and `q` is the input.

- **Compiler Directives and System Tasks:**  
  While not used in the above examples, Verilog supports compiler directives and system tasks for advanced functionality. Refer to the flowcharts below for more information:

  <p align="center">
    <img src="images/task.jpg" alt="Verilog System Tasks">
  </p>
  <p align="center">
    <img src="images/direc.jpg" alt="Verilog Compiler Directives">
  </p>

---

## Flip-Flops

Flip-flops are fundamental building blocks in digital electronics, used for storing binary information. They are bistable devices, meaning they have two stable states and can store one bit of data. Flip-flops are widely used in registers, counters, memory devices, and various sequential circuits.

### Types of Flip-Flops

The most common types of flip-flops are:

- **SR (Set-Reset) Flip-Flop**
- **D (Data or Delay) Flip-Flop**
- **JK Flip-Flop**
- **T (Toggle) Flip-Flop**

Each type has its own characteristic table and behavior, making them suitable for different applications.

### SR (Set-Reset) Flip-Flop

The SR flip-flop has two inputs, Set (S) and Reset (R), and two outputs, Q and Q'. The outputs change state based on the input conditions as shown below:

| S   | R   | Q(next) | Description |
| --- | --- | ------- | ----------- |
| 0   | 0   | Q       | No Change   |
| 0   | 1   | 0       | Reset       |
| 1   | 0   | 1       | Set         |
| 1   | 1   | Invalid | Not Allowed |

### D (Data) Flip-Flop

The D flip-flop captures the value of the D input at the moment of a clock edge (usually the rising edge) and holds it until the next clock event.

| D   | Q(next) | Description |
| --- | ------- | ----------- |
| 0   | 0       | Reset       |
| 1   | 1       | Set         |

### JK Flip-Flop

The JK flip-flop is a refinement of the SR flip-flop, eliminating the invalid state. It has two inputs, J and K, and operates as follows:

| J   | K   | Q(next) | Description |
| --- | --- | ------- | ----------- |
| 0   | 0   | Q       | No Change   |
| 0   | 1   | 0       | Reset       |
| 1   | 0   | 1       | Set         |
| 1   | 1   | Q'      | Toggle      |

### T (Toggle) Flip-Flop

The T flip-flop toggles its output on each clock pulse if the T input is high.

| T   | Q(next) | Description |
| --- | ------- | ----------- |
| 0   | Q       | No Change   |
| 1   | Q'      | Toggle      |

### Applications of Flip-Flops

- **Data Storage:** Used in registers and memory elements to store binary data.
- **Counters:** Flip-flops are cascaded to build binary and decade counters.
- **Frequency Division:** Used to divide the frequency of clock signals.
- **State Machines:** Serve as memory elements in finite state machines.

### Edge-Triggered Flip-Flops

Most flip-flops used in digital circuits are edge-triggered, meaning they change state only at the rising or falling edge of the clock signal. This ensures precise timing and synchronization in sequential circuits.

<p align="center">
  <img src="images/flipflop_types.png" alt="Types of Flip-Flops">
</p>

---
