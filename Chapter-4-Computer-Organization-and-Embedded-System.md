## **4.1 Control and Central Processing Units**

This section is about how a computer actually **executes instructions** — how data moves inside, how the CPU controls everything, and how modern processors achieve speed and efficiency (RISC, CISC, pipelining, etc.).

---

### 1. Control Memory and Address Sequencing

#### 🔹 What is Control Memory?

* It is a **special memory** inside the **control unit** of CPU that stores **microinstructions**.
* Each **microinstruction** defines a **micro-operation** (like load, add, store, etc.) that the CPU performs.
* So, Control Memory = “memory of the control unit”.

#### 🔹 Types of Control Unit:

1. **Hardwired Control Unit**

   * Uses fixed logic circuits (like gates, flip-flops).
   * Very fast but **difficult to modify**.
   * Used in **RISC processors**.
2. **Microprogrammed Control Unit**

   * Uses control memory (stores microinstructions).
   * **Easier to modify**, slower than hardwired.
   * Used in **CISC processors**.

#### 🔹 Address Sequencing

* Determines the **order in which microinstructions are read** from control memory.
* Control memory has an address register → points to the next microinstruction.
* Sequencing can depend on:

  * Next sequential instruction
  * Jump or branch conditions
  * Interrupts

**MCQ Tip:**
Q: *Control memory is part of which unit?*
→ **Control Unit**

---

### 2. Computer Configuration

* Refers to the **arrangement of components** (CPU, memory, I/O units, etc.) in a computer system.
* Includes:

  * Number and type of registers
  * ALU structure
  * Memory hierarchy (RAM, cache)
  * Bus connections

**MCQ Tip:**
“Computer configuration” mainly describes **the functional organization of the computer system**.

---

### 3. Microinstruction Format

A **microinstruction** is a binary word that specifies micro-operations.

Typical fields:

1. **Control field** – specifies what micro-operations to perform
2. **Address field** – next microinstruction address
3. **Condition field** – branching or decision info

So, microinstruction = (Control signals + Next Address info + Condition info)

**MCQ Tip:**
Microinstruction → stored in **control memory**
Micro-operation → executed by **CPU hardware**

---

### 4. Design of Control Unit

Control unit = part of CPU that **generates control signals** to direct other units.

#### Two main designs:

1. **Hardwired Control Unit**

   * Fixed logic circuits
   * Fast, less flexible
   * Suitable for simple instructions
2. **Microprogrammed Control Unit**

   * Uses control memory
   * Slower, more flexible
   * Easier to modify or add instructions

**MCQ Tip:**

* “Hardwired control” → **faster execution**
* “Microprogrammed control” → **ease of modification**

---

### 5. CPU Structure and Function

**CPU Components:**

1. **Arithmetic Logic Unit (ALU)** – performs arithmetic & logical operations.
2. **Control Unit (CU)** – directs the operations of CPU.
3. **Registers** – high-speed storage for instructions and data.

**Main CPU Functions:**

* Fetch → Decode → Execute → Store
* This is called the **instruction cycle**.

**MCQ Tip:**
Program Counter (PC) → Holds address of next instruction.
Instruction Register (IR) → Holds current instruction.

---

### 6. Arithmetic and Logic Unit (ALU)

* Performs **mathematical** (add, sub, multiply, divide) and **logical** (AND, OR, NOT, XOR) operations.
* ALU works on **operands stored in registers**.

**MCQ Tip:**
ALU → Performs **operations**
Control Unit → **Directs** operations

---

### 7. Instruction Formats

* Instructions are stored in **binary form** and generally have:

  ```
  [Opcode | Address or Operand(s)]
  ```
* **Opcode** – operation code (what to do)
* **Operand** – data or memory address

**Common formats:**

* 0-address (e.g., stack-based)
* 1-address
* 2-address
* 3-address instructions

 **MCQ Tip:**
Instruction format defines the **layout of bits** of an instruction.

---

### 8. Addressing Modes

Used to **specify where the operand is**.

| Mode      | Description                | Example       |
| --------- | -------------------------- | ------------- |
| Immediate | Operand given directly     | MOV A, #5     |
| Direct    | Address given directly     | MOV A, [1000] |
| Indirect  | Address stored in register | MOV A, [R1]   |
| Register  | Operand in register        | MOV A, B      |
| Indexed   | Base + offset              | MOV A, [R1+5] |

 **MCQ Tip:**
Immediate addressing → Fastest
Indirect addressing → Requires extra memory access

---

### 9. Data Transfer and Manipulation

**Data Transfer:** Move data between CPU, memory, or I/O.

* MOV, LOAD, STORE

**Data Manipulation:** Perform arithmetic or logic operations.

* ADD, SUB, AND, OR, COMPARE

**MCQ Tip:**

* Data movement = **transfer**
* Arithmetic/logic = **manipulation**

---

### 10. RISC and CISC

| Feature            | RISC                             | CISC                             |
| ------------------ | -------------------------------- | -------------------------------- |
| Full form          | Reduced Instruction Set Computer | Complex Instruction Set Computer |
| Instruction length | Fixed                            | Variable                         |
| Control            | Hardwired                        | Microprogrammed                  |
| Execution speed    | Fast                             | Slower                           |
| Example            | ARM, MIPS                        | Intel x86                        |

 **MCQ Tip:**

* RISC → simpler, faster
* CISC → more complex, more instructions

---

### 11. Pipelining and Parallel Processing

#### 🔹 Pipelining

* Overlaps execution of multiple instructions.
* Example: one instruction fetched while another is executed.
* Increases throughput (instructions per unit time).

**Stages of pipeline:** Fetch → Decode → Execute → Memory → Write-back

#### 🔹 Parallel Processing

* Multiple processors or cores execute **different instructions simultaneously**.
* Used in multicore CPUs and GPUs.

 **MCQ Tip:**

* Pipelining → **instruction-level parallelism**
* Parallel processing → **processor-level parallelism**

---

### **Quick Summary Table**

| Concept                      | Key Point                 |
| ---------------------------- | ------------------------- |
| Control Memory               | Stores microinstructions  |
| Hardwired vs Microprogrammed | Fast vs Flexible          |
| ALU                          | Performs arithmetic/logic |
| Instruction Format           | Defines bit layout        |
| Addressing Mode              | Tells how to access data  |
| RISC vs CISC                 | Simple/Fast vs Complex    |
| Pipelining                   | Overlapping execution     |

---

## **Section 4.1 – MCQs (Conceptual Quick Practice)**

**1.** Control Memory is a part of:<br>
A. ALU<br>
B. Main Memory<br>
C. Control Unit<br>
D. Cache Memory<br>
✅ **Answer:** C — *It stores microinstructions for control signals.*

---

**2.** The unit that generates control signals to direct the operations of other parts of the CPU is:<br>
A. ALU<br>
B. Register<br>
C. Control Unit<br>
D. Memory Unit<br>
✅ **Answer:** C

---

**3.** Hardwired control unit is ______ than a microprogrammed control unit.<br>
A. Slower<br>
B. Faster<br>
C. More flexible<br>
D. Easier to modify<br>
✅ **Answer:** B — *Hardwired is faster but less flexible.*

---

**4.** Which register holds the address of the next instruction to be executed?<br>
A. Instruction Register<br>
B. Program Counter<br>
C. Memory Address Register<br>
D. Stack Pointer<br>
✅ **Answer:** B

---

**5.** In a CPU, ALU is used to:<br>
A. Perform arithmetic and logical operations<br>
B. Store data and instructions<br>
C. Control data flow<br>
D. Decode instructions<br>
✅ **Answer:** A

---

**6.** Immediate addressing mode means:<br>
A. Operand is stored in memory<br>
B. Operand is part of the instruction itself<br>
C. Operand address is in a register<br>
D. Operand address is computed<br>
✅ **Answer:** B

---

**7.** In RISC architecture, instructions are:<br>
A. Complex and variable length<br>
B. Simple and fixed length<br>
C. Microprogrammed<br>
D. None of the above<br>
✅ **Answer:** B

---

**8.** Pipelining increases:<br>
A. Instruction latency<br>
B. Instruction throughput<br>
C. Memory size<br>
D. Cache size<br>
✅ **Answer:** B — *More instructions executed per unit time.*

---

**9.** The microinstruction format generally contains:<br>
A. Opcode and data<br>
B. Control signals, condition, next address<br>
C. Operand and address<br>
D. Instruction register<br>
✅ **Answer:** B

---

**10.** Parallel processing is used to:<br>
A. Increase instruction speed<br>
B. Execute multiple instructions simultaneously<br>
C. Increase cache size<br>
D. Reduce instruction size<br>
✅ **Answer:** B

---
