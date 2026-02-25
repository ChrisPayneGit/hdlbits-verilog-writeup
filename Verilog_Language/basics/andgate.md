# 🧩 AND Gate (andgate)

> HDLBits – Verilog Basics

---

## 📌 Problem Statement

Create a module that implements a **AND gate**.

The module has **two inputs** and **one output**.
The output must continuously drive the **sum** of the inputs.

---

![Image](https://hdlbits.01xz.net/mw/images/7/78/Andgate.png)

---

## 🧠 Concept Covered

* **Bitwise / logical AND**
* **Continuous assignment**
* **Combinational logic**

---

## 🧱 Module Interface

```verilog
module top_module( 
    input a, 
    input b, 
    output out );

endmodule
```

* `a, b`  → input signals
* `out` → output signal

---

## ✅ Verilog Solution

```verilog
module top_module( 
    input a, 
    input b, 
    output out );
    
    assign out = a && b;

endmodule
```

### ✅ Alternative (Bitwise NOT)

```verilog
module top_module( 
    input a, 
    input b, 
    output out );
    
    assign out = a & b;

endmodule
```

Both are valid here since `a and b` are **1-bit wide**.

---

<img width="1366" height="657" alt="Solutions waveform for 2-input And gate" src="../assets/ANDGATE_wavedrom.svg" />

## 🔍 Explanation

* The `assign` statement creates a **continuous connection**
* `a&&b` (logical And) sums the values of `a and b`
* Whenever `a or b` change, `out` updates immediately
* No procedural blocks are required

---

## 🧪 Expected Behavior

* `a = 0; b = 0` → `out = 0`
* `a = 0; b = 1` → `out = 0`
* `a = 1; b = 0` → `out = 0`
* `a = 1; b = 1` → `out = 1`

The timing diagram confirms **perfect summation**.

✔️ HDLBits Simulation Status: **SUCCESS**

---

## ⚠️ Common Mistakes

* ❌ Forgetting `assign`
* ❌ Using `always` for simple logic
* ❌ Confusing `&&` and `&` for multi-bit signals
* ❌ Declaring `out` as `reg`

---

## 🎯 Takeaway

> **Continuous assignments are ideal for simple combinational logic like logic gates.**

This problem introduces the **first logic operation** beyond simple wiring.

---

### 🟢 Difficulty

**Easy**

---
