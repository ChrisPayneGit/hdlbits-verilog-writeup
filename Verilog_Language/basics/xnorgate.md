# 🧩 XNOR Gate (xnorgate)

> HDLBits – Verilog Basics

---

## 📌 Problem Statement

Create a module that implements a **XNOR gate**. A **XNOR** function needs two operators when written in Verilog. **XNOR** is only bitwise and does not have a logical operator.

The module has **two inputs** and **one output**.
The output must continuously drive the **opposite of the xor** of the inputs.

---

![Image](https://hdlbits.01xz.net/mw/images/6/6d/Xnorgate.png)

---

## 🧠 Concept Covered

* **Bitwise / logical XNOR**
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
    
    assign out = ~(a ^ b);

endmodule
```

### ✅ Alternatives (Bitwise NOR)

```verilog
module top_module( 
    input a, 
    input b, 
    output out );
    
    assign out = !(a ^ b);

endmodule
```

Both are valid here since `a and b` are **1-bit wide**.

---

<img width="1366" height="657" alt="Solutions waveform for 2-input XNOR gate" src="../assets/XNORGATEwavedrom.svg" />

## 🔍 Explanation

* The `assign` statement creates a **continuous connection**
* `!(a^b)` (logical XNOR) is the opposite of the exclusive sum of `a and b`
* Whenever `a or b` change, `out` updates immediately
* No procedural blocks are required

---

## 🧪 Expected Behavior

* `a = 0; b = 0` → `out = 1`
* `a = 0; b = 1` → `out = 0`
* `a = 1; b = 0` → `out = 0`
* `a = 1; b = 1` → `out = 1`

The timing diagram confirms **perfect opposite of the exclusive summation**.

✔️ HDLBits Simulation Status: **SUCCESS**

---

## ⚠️ Common Mistakes

* ❌ Forgetting `assign`
* ❌ Using `always` for simple logic
* ❌ Forgetting `^` is only for single-bit signals
* ❌ Confusing `!` and `~` for multi-bit signals
* ❌ Declaring `out` as `reg`

---

## 🎯 Takeaway

> **Continuous assignments are ideal for simple combinational logic like logic gates.**

This problem introduces the **Another logic operation with two operators** beyond simple wiring.

---

### 🟢 Difficulty

**Easy**

---
