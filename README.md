# Palindromic PDA Simulator

An interactive and beginner-friendly **Pushdown Automaton (PDA) Simulator** that demonstrates how a PDA recognizes palindromic strings using a stack.

The simulator visualizes the complete execution process, including state transitions, PUSH and POP operations, stack changes, and final acceptance or rejection.

## 🎯 Project Objective

To implement a specific Pushdown Automaton that recognizes the language:

\[
L = \{wcw^R \mid w \in \{0,1\}^*\}
\]

Where:
- `w` is any binary string containing 0s and 1s.
- `c` is the middle marker.
- `wᴿ` represents the reverse of the first half.

**Example:**

`10c01` → Accepted

The PDA pushes the first half onto the stack, encounters the center marker `c`, and then pops and compares symbols with the second half.

## ✨ Features

- **Interactive Input:** Enter any binary string containing a center marker `c`.
- **Stack Visualization:** Watch symbols being pushed onto and popped from the stack.
- **Step-by-Step Simulation:** Execute the PDA one transition at a time.
- **Auto Simulation:** Automatically execute all transitions.
- **State Visualization:** Observe transitions between PDA states.
- **Execution History:** View each step, input symbol, stack contents, and operation.
- **Acceptance & Rejection:** Get instant results based on PDA logic.
- **Example Inputs:** Test predefined accepted and rejected strings.
- **Reset Functionality:** Restart the simulation anytime.

## ⚙️ PDA Working

The PDA operates in two main phases:

### 1. PUSH Phase (q0)

- Read the input from left to right.
- Push every `0` or `1` onto the stack.
- Continue until the center marker `c` is encountered.

### 2. POP and MATCH Phase (q1)

- After reading `c`, switch to POP mode.
- Read the remaining input symbols.
- Compare each symbol with the top of the stack.
- If they match, pop the stack.
- If they do not match, reject the string.

### 3. Final State

The string is accepted if:
- Exactly one center marker `c` exists.
- All input symbols are consumed.
- Only the bottom stack symbol `Z0` remains.

Otherwise, the string is rejected.

## 🔄 State Transition Overview

| State | Input | Operation | Next State |
|---|---|---|---|
| q0 | 0 | Push 0 | q0 |
| q0 | 1 | Push 1 | q0 |
| q0 | c | Switch to POP phase | q1 |
| q1 | 0, stack top 0 | Pop 0 | q1 |
| q1 | 1, stack top 1 | Pop 1 | q1 |
| q1 | Mismatch | Reject | q_reject |
| q1 | End of input, stack Z0 | Accept | q_accept |

## 🧪 Sample Test Cases

| Input String | Expected Result |
|---|---|
| `10c01` | Accepted |
| `101c101` | Accepted |
| `11c11` | Accepted |
| `10c10` | Rejected |
| `101c10` | Rejected |
| `c` | Accepted |
| `10c001` | Rejected |
| `101c011` | Rejected |

## 🛠️ Technologies Used

- HTML5
- CSS3
- JavaScript
- Stack Data Structure
- Pushdown Automata (PDA)
- Finite State Transitions

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/sakshi-exe/CM24108_TAE.git
```

### 2. Navigate to the Project Folder

```bash
cd CM24108_TAE
```

### 3. Run the Application

Open the project's `index.html` file in your browser.

Alternatively, use the Live Server extension in Visual Studio Code.

## 📚 Concepts Demonstrated

- Theory of Computation
- Pushdown Automata
- Context-Free Languages
- Stack Operations
- State Transitions
- String Reversal
- Language Recognition

## 🎓 Academic Purpose

This project is developed as an educational demonstration of Pushdown Automata and their application in recognizing palindromic languages.

It helps students understand how a stack enables a PDA to recognize patterns that require memory of previously read symbols.

---

**Developed by:** Sakshi Rakhade

**GitHub:** [@sakshi-exe](https://github.com/sakshi-exe)

**Repository:** [CM24108_TAE](https://github.com/sakshi-exe/CM24108_TAE)

*Learn. Simulate. Understand.*
