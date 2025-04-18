# ➕ Carry Save Adder (CSA) – Verilog Implementation

This project demonstrates a **4-bit Carry Save Adder** in Verilog, along with a comprehensive testbench that verifies its functionality across a range of inputs.

---

## 📁 Files Included

| File Name       | Description                                |
|------------------|--------------------------------------------|
| `csavea.v`       | Main Verilog module: 4-bit CSA using Full Adders |
| `tb_csavea.v`    | Testbench for CSA, includes random tests and error checking |
| `fa` (in `csavea.v`) | Full Adder module used inside the CSA |

---

## 🧠 Functionality

- Takes three 4-bit inputs: `x`, `y`, and `z`.
- Outputs a 5-bit sum (`s[4:0]`) and carry out (`cout`).
- Internally uses **full adders** to perform carry-save operations in two stages.
- Testbench runs combinations of inputs and checks output accuracy.

---

## 🧪 Testbench Details

The testbench:
- Iterates through values of `x`, `y`, and `z` from `0` to `9`.
- Compares the expected result of `(x + y + z)` with `{cout, s}`.
- Displays mismatches and counts errors.
- Dumps waveform to `csavea_wave.vcd`.

---

## 🚀 How to Run (with Icarus Verilog)

### 🛠️ Simulation:

Make sure you have [Icarus Verilog](http://iverilog.icarus.com/) installed.

```bash
iverilog -o csavea_tb csavea.v tb_csavea.v
vvp csavea_tb
