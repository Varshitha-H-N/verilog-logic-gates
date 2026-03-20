# verilog-logic-gates
Basic logic gates implemented in Verilog HDL
# 🔌 Verilog Logic Gates

A collection of all basic digital logic gates implemented in Verilog HDL, complete with a combined testbench and truth table simulation.

---

## Project Structure
```
verilog-logic-gates/
├── README.md
├── src/
│   ├── and_gate.v
│   ├── or_gate.v
│   ├── not_gate.v
│   ├── nand_gate.v
│   ├── nor_gate.v
│   ├── xor_gate.v
│   └── xnor_gate.v
└── testbench/
    └── gates_tb.v
```

## Gates Implemented

| Gate | Symbol | Expression |
|------|--------|------------|
| AND  | `&`    | `Y = A & B` |
| OR   | `\|`   | `Y = A \| B` |
| NOT  | `~`    | `Y = ~A` |
| NAND | `~&`   | `Y = ~(A & B)` |
| NOR  | `~\|`  | `Y = ~(A \| B)` |
| XOR  | `^`    | `Y = A ^ B` |
| XNOR | `~^`   | `Y = ~(A ^ B)` |



