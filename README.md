# 🔌 Verilog Logic Gates

Basic logic gates implemented in Verilog HDL, simulated using Cadence irun.

---

## 📁 Project Structure

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
├── testbench/
│   ├── and_gate_tb.v
│   ├── or_gate_tb.v
│   ├── not_gate_tb.v
│   ├── nand_gate_tb.v
│   ├── nor_gate_tb.v
│   ├── xor_gate_tb.v
│   └── xnor_gate_tb.v
└── *.f  (compile files for each gate)
```

---

## 🧩 Gates Implemented

| Gate | Expression |
|------|------------|
| AND  | `Y = A & B` |
| OR   | `Y = A \| B` |
| NOT  | `Y = ~A` |
| NAND | `Y = ~(A & B)` |
| NOR  | `Y = ~(A \| B)` |
| XOR  | `Y = A ^ B` |
| XNOR | `Y = ~(A ^ B)` |

---

## 💻 Gate Source Code

### AND Gate
```verilog
module and_gate(input A, input B, output Y);
  assign Y = A & B;
endmodule
```

### OR Gate
```verilog
module or_gate(input A, input B, output Y);
  assign Y = A | B;
endmodule
```

### NOT Gate
```verilog
module not_gate(input A, output Y);
  assign Y = ~A;
endmodule
```

### NAND Gate
```verilog
module nand_gate(input A, input B, output Y);
  assign Y = ~(A & B);
endmodule
```

### NOR Gate
```verilog
module nor_gate(input A, input B, output Y);
  assign Y = ~(A | B);
endmodule
```

### XOR Gate
```verilog
module xor_gate(input A, input B, output Y);
  assign Y = A ^ B;
endmodule
```

### XNOR Gate
```verilog
module xnor_gate(input A, input B, output Y);
  assign Y = ~(A ^ B);
endmodule
```

---

## 🧪 Testbench Example (AND Gate)

```verilog
module and_gate_tb;
  reg A, B;
  wire Y;
  and_gate dut(.A(A), .B(B), .Y(Y));
  initial begin
    $monitor("A=%b, B=%b, Y=%b", A, B, Y);
    A = 1'b0; B = 1'b0; #10;
    A = 1'b0; B = 1'b1; #10;
    A = 1'b1; B = 1'b0; #10;
    A = 1'b1; B = 1'b1; #10;
  end
endmodule
```

---

## ▶️ How to Simulate (Cadence irun)

```bash
# Run individual gate simulation
irun -f and_gate_compile.f
irun -f or_gate_compile.f
irun -f not_gate_compile.f
irun -f nand_gate_compile.f
irun -f nor_gate_compile.f
irun -f xor_gate_compile.f
irun -f xnor_gate_compile.f
```


### compile.f format
```
-timescale 1ns/1ps
-access +rwc
-top <gate_name>_tb
src/<gate_name>.v
testbench/<gate_name>_tb.v
```

---

## 📊 Expected Output 
## (AND Gate)
```
A=0, B=0, Y=0
A=0, B=1, Y=0
A=1, B=0, Y=0
A=1, B=1, Y=1
```
## (OR Gate)
```
A=0, B=0, Y=0
A=0, B=1, Y=1
A=1, B=0, Y=1
A=1, B=1, Y=1
```
## (NOT Gate)
```
A=0, Y=1
A=1, Y=0
```
## (NAND Gate)
```
A=0, B=0, Y=1
A=0, B=1, Y=1
A=1, B=0, Y=1
A=1, B=1, Y=0
```
## (NOR Gate)
```
A=0, B=0, Y=1
A=0, B=1, Y=0
A=1, B=0, Y=0
A=1, B=1, Y=0
```
## (XOR Gate)
```
A=0, B=0, Y=0
A=0, B=1, Y=1
A=1, B=0, Y=1
A=1, B=1, Y=0
```
## (XNOR Gate)
```
A=0, B=0, Y=1
A=0, B=1, Y=0
A=1, B=0, Y=0
A=1, B=1, Y=1
```
---

## 🛠️ Tools Used

- **Language:** Verilog HDL
- **Simulator:** Cadence Incisive (irun)
- **Waveform Viewer:** SimVision
