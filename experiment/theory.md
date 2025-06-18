Flip-flops are fundamental building blocks in digital electronics, used for storing binary information. They are bistable devices with two stable states, capable of storing one bit of data.

### Types of Flip-Flops

#### 1. SR (Set-Reset) Flip-Flop

##### Truth Table
| $S$ | $R$ | $Q_{next}$ | Description |
|-----|-----|------------|-------------|
| $0$ | $0$ | $Q$        | No Change   |
| $0$ | $1$ | $0$        | Reset       |
| $1$ | $0$ | $1$        | Set         |
| $1$ | $1$ | Invalid    | Not Allowed |

##### Verilog Implementation
```verilog
module sr_flipflop(
    input clk, input S, input R,
    output reg Q, output Qn
);
    assign Qn = ~Q;
    always @(posedge clk) begin
        if (S && R)
            Q <= 1'bx;  // Invalid state
        else if (S)
            Q <= 1'b1;  // Set
        else if (R)
            Q <= 1'b0;  // Reset
    end
endmodule
```

#### 2. D (Data) Flip-Flop

##### Truth Table
| $D$ | $Q_{next}$ | Description |
|-----|------------|-------------|
| $0$ | $0$        | Reset       |
| $1$ | $1$        | Set         |

##### Verilog Implementation
```verilog
module d_flipflop(
    input clk, input D,
    output reg Q, output Qn
);
    assign Qn = ~Q;
    always @(posedge clk) begin
        Q <= D;
    end
endmodule
```

#### 3. JK Flip-Flop

##### Truth Table
| $J$ | $K$ | $Q_{next}$ | Description |
|-----|-----|------------|-------------|
| $0$ | $0$ | $Q$        | No Change   |
| $0$ | $1$ | $0$        | Reset       |
| $1$ | $0$ | $1$        | Set         |
| $1$ | $1$ | $\overline{Q}$ | Toggle  |

##### Verilog Implementation
```verilog
module jk_flipflop(
    input clk, input J, input K,
    output reg Q, output Qn
);
    assign Qn = ~Q;
    always @(posedge clk) begin
        case ({J,K})
            2'b00: Q <= Q;      // No change
            2'b01: Q <= 1'b0;   // Reset
            2'b10: Q <= 1'b1;   // Set
            2'b11: Q <= ~Q;     // Toggle
        endcase
    end
endmodule
```

#### 4. T (Toggle) Flip-Flop

##### Truth Table
| $T$ | $Q_{next}$ | Description |
|-----|------------|-------------|
| $0$ | $Q$        | No Change   |
| $1$ | $\overline{Q}$ | Toggle  |

##### Verilog Implementation
```verilog
module t_flipflop(
    input clk, input T,
    output reg Q, output Qn
);
    assign Qn = ~Q;
    always @(posedge clk) begin
        if (T)
            Q <= ~Q;
    end
endmodule
```

### Design Considerations

#### Performance Metrics
- Setup time: $t_{setup}$
- Hold time: $t_{hold}$
- Clock-to-Q delay: $t_{cq}$
- Maximum frequency: $f_{max} = \frac{1}{t_{setup} + t_{cq}}$

#### Power and Area
- Dynamic power: $P_{dynamic} = \alpha \cdot C \cdot V_{dd}^2 \cdot f$
- Static power: $P_{static} = I_{leakage} \cdot V_{dd}$
- Area optimization through gate count minimization

### Applications
- Data storage in registers
- State machines and counters
- Clock domain crossing
- Frequency division

> **Note:** For practical implementation steps, refer to the procedure.md file.
