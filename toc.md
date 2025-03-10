

# **Unit 1: Introduction (4 hrs.)**

### **1.1 Review of Set, Relation, and Function**
- **Set**: A collection of distinct objects (e.g., {1, 2, 3}).
- **Relation**: A subset of the Cartesian product of two sets (e.g., R ⊆ A × B).
- **Function**: A special relation where each element in the domain maps to a unique element in the codomain.

### **1.2 Proof Techniques**
- **Proof by Contradiction**: Assume the opposite of what you want to prove, derive a contradiction.
- **Pigeonhole Principle**: If n items are placed in m containers (n > m), at least one container holds more than one item.
- **Mathematical Induction**:
  - Base case: Prove for the smallest value (e.g., n = 1).
  - Inductive step: Assume true for n, prove for n+1.
- **Diagonalization**: Used to show some sets are uncountable (e.g., Cantor’s diagonal argument).

### **1.3 Alphabets and Language**
- **Alphabet (Σ)**: A finite set of symbols (e.g., Σ = {0,1}).
- **String**: A finite sequence of symbols from an alphabet (e.g., 0101).
- **Language**: A set of strings over an alphabet (e.g., L = {010, 101, 11}).

### **1.4 Chomsky’s Hierarchy**
- **Type 0 (Recursively Enumerable)**: Recognized by a Turing Machine.
- **Type 1 (Context-Sensitive)**: Recognized by a Linear Bounded Automaton.
- **Type 2 (Context-Free)**: Recognized by a Pushdown Automaton.
- **Type 3 (Regular)**: Recognized by a Finite Automaton.

---

# **Unit 2: Finite Automata and Regular Language (10 hrs.)**

### **2.1 Deterministic Finite Automata (DFA) and Non-Deterministic Finite Automata (NFA)**
- **DFA**: A finite automaton where each state has exactly one transition per input symbol.
- **NFA**: A finite automaton where multiple transitions per input symbol are allowed, including ε-moves.

### **2.2 Regular Expressions and Regular Language**
- **Regular Expression**: A notation for defining regular languages using symbols, union (|), concatenation, and Kleene star (*).
- **Equivalence of Regular Language and Finite Automata**: Any regular language can be represented by both an FA and a regular expression.

### **2.3 Properties of Regular Language**
- **Closure Properties**:
  - Union
  - Concatenation
  - Kleene Star
  - Intersection
  - Complement

### **2.4 Pumping Lemma for Regular Sets**
- Used to prove that a language is **not regular** by showing that long enough strings must repeat in a way that violates the properties of regular languages.

### **2.5 Closure Properties of Regular Sets**
- Regular languages are closed under:
  - Union
  - Concatenation
  - Intersection
  - Complement
  - Difference
  - Reversal

### **2.6 Decision Algorithms for Regular Sets**
- **Membership Problem**: Determine if a string belongs to a regular language.
- **Equivalence Problem**: Check if two DFAs recognize the same language.
- **Emptiness Problem**: Check if a DFA accepts no strings.
- **Minimization**: Reduce the number of states in a DFA while preserving language recognition.

---

Here are the notes for the topics mentioned in the image:

---

# **Unit 3: Context-Free Language and Pushdown Automata (13 hrs.)**

### **3.1 Context-Free Grammar (CFG)**
- A **Context-Free Grammar (CFG)** consists of:
  - **V**: A set of variables (non-terminals)
  - **Σ**: A set of terminals (alphabet)
  - **P**: A set of production rules (e.g., S → aSb | ε)
  - **S**: The start symbol
- **Example**:  
  ```
  S → aSb | ε
  ```
  This generates palindromes with 'a' and 'b'.

### **3.2 Derivation Trees and Simplification of CFG**
- **Derivation Tree** (Parse Tree): A tree representation of derivations in a CFG.
- **Simplification**:
  - **Removing Useless Symbols** (symbols that never produce a terminal string)
  - **Eliminating Null Productions** (productions of the form A → ε)
  - **Eliminating Unit Productions** (A → B, where A and B are non-terminals)

### **3.3 Normal Forms (CNF, GNF)**
- **Chomsky Normal Form (CNF)**:
  - Every production is of the form:
    - A → BC (where B and C are non-terminals)
    - A → a (where a is a terminal)
- **Greibach Normal Form (GNF)**:
  - Every production is of the form:
    - A → aα (where a is a terminal and α is a string of non-terminals)

### **3.4 Pushdown Automata (PDA)**
- **Definition**: A finite automaton with a stack as additional memory.
- **Components**:
  - A finite set of states
  - Input alphabet
  - Stack alphabet
  - Transition function
  - Initial state
  - Final states
- **Formal Description**: δ(q, a, X) = (p, Y), where:
  - q = current state
  - a = input symbol
  - X = top of stack
  - p = next state
  - Y = stack replacement

### **3.5 Equivalence of PDA and CFG**
- Every **context-free language** can be recognized by a PDA.
- For every **PDA**, there exists an equivalent **CFG**.

### **3.6 Properties of Context-Free Languages (CFL)**
- **Closed under**:
  - Union
  - Concatenation
  - Kleene star
- **Not closed under**:
  - Intersection
  - Complementation

### **3.7 Pumping Lemma for CFL**
- Used to prove that a language **is not context-free**.
- If a language is context-free, any sufficiently long string can be "pumped" into different valid strings.

### **3.8 Closure Properties of CFL**
- Context-free languages are **closed** under:
  - Union
  - Concatenation
  - Kleene Star
- **Not closed** under:
  - Intersection with another CFL
  - Complementation

### **3.9 Decision Algorithms for CFL**
- **Membership Problem**: Given a string w and a CFG G, does w ∈ L(G)?
- **Equivalence Problem**: Are two CFGs equivalent?
- **Emptiness Problem**: Does a CFG generate any string?

---

# **Unit 4: Turing Machines (10 hrs.)**

### **4.1 Introduction to Turing Machine**
- A Turing Machine (TM) is a theoretical machine that models computation.
- **Components**:
  - Infinite tape divided into cells
  - Read/Write head
  - Finite control with states
  - Transition function δ(q, X) = (p, Y, D)  
    - q = current state
    - X = current tape symbol
    - p = next state
    - Y = symbol to write
    - D = move direction (Left/Right)

### **4.2 Computing with a Turing Machine**
- **Steps**:
  1. Read the current tape symbol.
  2. Based on the transition function, change state and write a new symbol.
  3. Move the head left or right.
  4. Repeat until a halt state is reached.

### **4.3 Extensions of Turing Machines**
- **Multi-tape Turing Machine**: Uses multiple tapes for parallel processing.
- **Non-deterministic Turing Machine (NTM)**: Can make multiple moves for a given state and input symbol.
- **Universal Turing Machine (UTM)**: A Turing machine that can simulate other TMs.

### **4.4 Unrestricted Grammar**
- **Type-0 Grammar**: Recognized by TMs.
- Productions are of the form:  
  ```
  α → β
  ```
  where α and β are arbitrary strings over terminals and non-terminals.

### **4.6 Recursively Enumerable Languages**
- A language is **recursively enumerable (RE)** if a TM exists that can list all valid strings in the language.
- A language is **recursive** if a TM always halts with a yes/no answer.

---

# **Unit 5: Undecidability (4 hrs.)**

### **5.1 The Church-Turing Thesis**
- **States that any computation that can be performed algorithmically can be done by a Turing Machine**.
- Defines the limits of computability.

### **5.2 The Halting Problem**
- **Can a TM decide whether another TM halts on a given input?**
- **Answer**: No, it is undecidable.
- **Proof**: Assumed solution leads to a contradiction (Diagonalization Argument).

### **5.3 Universal Turing Machine**
- A **Turing Machine that can simulate any other Turing Machine**.
- **Input**: Description of a TM and an input string.
- **Output**: The simulated TM’s result.

### **5.4 Undecidable Problems about Turing Machines**
- **Halting Problem** (proven undecidable).
- **Equivalence Problem**: Check if two TMs recognize the same language.
- **Post Correspondence Problem (PCP)**: Given two lists of strings, determine if they can be arranged to form the same string.

### **5.5 Properties of Recursive and Recursively Enumerable Languages**
- **Recursive Language**:
  - Decidable by a TM that always halts.
- **Recursively Enumerable Language**:
  - Accepted by a TM that may **not** halt on all inputs.

---

# **Unit 6: Computational Complexity (4 hrs.)**  

## **6.1 Introduction to Complexity Theory**  
**Computational Complexity Theory** studies the efficiency of algorithms in terms of **time** and **space**. It helps classify problems based on their difficulty and solvability.  

### **Tractable vs. Intractable Problems**  
- **Tractable Problems**: Problems that can be solved efficiently (i.e., in polynomial time, denoted as O(n^k) for some constant k).  
- **Intractable Problems**: Problems for which no polynomial-time algorithm is known (i.e., they require exponential time or worse, such as O(2^n)).  

### **Time and Space Complexity**  
- **Time Complexity**: The number of computational steps required to solve a problem as a function of input size **n**.  
- **Space Complexity**: The amount of memory required by an algorithm.  

### **Big-O Notation** (Asymptotic Complexity)  
Used to express the worst-case runtime of an algorithm:  
- **O(1)** → Constant time (e.g., accessing an array element).  
- **O(log n)** → Logarithmic time (e.g., binary search).  
- **O(n)** → Linear time (e.g., iterating through an array).  
- **O(n log n)** → Log-linear time (e.g., merge sort, quicksort).  
- **O(n²), O(n³), O(2^n), O(n!)** → Polynomial to exponential time (slower algorithms).  

---

## **6.3 Class P and Class NP Problems**  

### **Class P (Polynomial Time Problems)**  
- Problems that can be solved in **polynomial time** (O(n^k) for some constant k).  
- Efficiently solvable using deterministic algorithms.  
- Examples:
  - **Sorting** (Merge Sort, Quick Sort → O(n log n))  
  - **Graph Algorithms** (Dijkstra’s algorithm → O(V²))  
  - **Matrix Multiplication** (O(n³))  

### **Class NP (Nondeterministic Polynomial Time Problems)**  
- Problems for which a solution can be **verified** in polynomial time but may not be **solvable** in polynomial time.  
- Can be solved efficiently using a **non-deterministic** machine (e.g., guessing the solution and verifying it in polynomial time).  
- Examples:
  - **Traveling Salesman Problem (TSP)**
  - **Graph Coloring Problem**
  - **Boolean Satisfiability (SAT)**

### **P vs. NP Question**  
- **Does P = NP?**  
  - If every problem whose solution can be verified in polynomial time (NP) can also be solved in polynomial time (P), then **P = NP**.  
  - If not, **P ≠ NP**.  
  - This is one of the biggest **open problems** in computer science.

---

## **6.4 NP-Complete Problems**  

### **Definition**  
- **NP-Complete (NPC) problems** are the hardest problems in **NP**.  
- If any NP-Complete problem can be solved in polynomial time, then **P = NP**.  
- **All NP problems can be reduced to an NP-Complete problem in polynomial time.**  

### **Steps to Prove a Problem is NP-Complete**
1. **Show the problem is in NP** (i.e., a solution can be verified in polynomial time).  
2. **Reduce a known NP-Complete problem** to the given problem in polynomial time.  

### **Examples of NP-Complete Problems**
- **Boolean Satisfiability (SAT) Problem**  
- **Traveling Salesman Problem (TSP)**  
- **3-SAT Problem**  
- **Graph Coloring Problem**  
- **Knapsack Problem**  

### **NP-Hard vs. NP-Complete**
- **NP-Hard**: At least as hard as NP problems but **not necessarily in NP** (may not be verifiable in polynomial time).  
- **NP-Complete**: A subset of NP-Hard problems that are in NP.  

---

### **Summary**
| **Class**     | **Definition** | **Examples** |
|--------------|----------------|-------------|
| **P** | Problems that can be **solved in polynomial time**. | Sorting, Graph Traversal, Shortest Path |
| **NP** | Problems whose **solutions can be verified in polynomial time**. | SAT, Graph Coloring, TSP |
| **NP-Complete** | The hardest problems in NP. If one can be solved in **P**, then **P = NP**. | SAT, 3-SAT, TSP |
| **NP-Hard** | At least as hard as NP problems but may not be in NP. | Halting Problem, Generalized Chess |

---

### **Open Question: Does P = NP?**
- If **P = NP**, then all NP problems become solvable in polynomial time → huge impact on cryptography, AI, and optimization.
- If **P ≠ NP**, it means some problems are inherently difficult to solve but easy to verify.


### **Numerical and Problem-Solving Questions for Theory of Computation**  
Below are **problems and solutions** for **every major topic** in the syllabus.

---

## **Unit 1: Introduction**
### **Problem 1: Set, Relation, and Function**
🔹 **Problem:**  
Let **A = {1,2,3,4}** and **B = {a,b,c}**. Define a relation **R** from **A** to **B** as:  
**R = {(1,a), (2,b), (3,c), (4,a)}**  
- Is **R** a function?  
- If yes, is it one-to-one (injective) or onto (surjective)?  

✅ **Solution:**  
- **Function Check:** Every element of **A** has exactly **one** image in **B**, so **R is a function**.  
- **Injective:** Different elements of **A** map to different elements in **B**, except **4 → a** and **1 → a**. So, **not injective**.  
- **Surjective:** Since **b** and **c** are mapped, but **d** is missing in **B**, it is **not onto**.

---

### **Problem 2: Proof by Contradiction**
🔹 **Problem:**  
Prove that **√2 is irrational** using contradiction.

✅ **Solution:**  
1. Assume **√2 is rational**, i.e., **√2 = p/q**, where **p** and **q** are integers with **no common factors**.  
2. Squaring both sides:  
   \[
   2 = p^2 / q^2 \Rightarrow p^2 = 2q^2
   \]
   This means **p² is even**, so **p is even** (let **p = 2k**).  
3. Substituting in **p² = 2q²**,  
   \[
   (2k)^2 = 2q^2 \Rightarrow 4k^2 = 2q^2 \Rightarrow q^2 = 2k^2
   \]
   So **q is also even**, contradicting our assumption that **p and q have no common factors**.  
4. **Thus, √2 is irrational.** ❌

---

## **Unit 2: Finite Automata and Regular Language**
### **Problem 3: Construct a DFA for a language accepting all strings over {0,1} ending in "01"**  
✅ **Solution:**
- **States:** \( q_0, q_1, q_2 \)
- **Transitions:**
  - \( q_0 \to q_0 \) on 0
  - \( q_0 \to q_1 \) on 1
  - \( q_1 \to q_2 \) on 0
  - \( q_2 \to q_2 \) on 0,1 (final state)  

| State | 0 | 1 |
|---|---|---|
| q0 (start) | q0 | q1 |
| q1 | q2 | q1 |
| q2 (final) | q2 | q2 |

---

### **Problem 4: Pumping Lemma for Regular Languages**
🔹 **Problem:**  
Prove that the language **L = {0^n1^n | n ≥ 0}** is not regular using the **Pumping Lemma**.

✅ **Solution:**  
1. **Assume L is regular.**  
2. Let **p** be the pumping length. Choose **w = 0^p 1^p**.  
3. Split **w = xyz**, where **|xy| ≤ p**, and **y ≠ ε**.  
   - Since **|xy| ≤ p**, **y** consists only of **0’s**.  
4. Pumping **y** → If we remove or add occurrences of **y**, the number of 0s ≠ number of 1s.  
5. Contradiction! **L is not regular.** ❌

---

## **Unit 3: Context-Free Grammar and Pushdown Automata**
### **Problem 5: Convert CFG to CNF**
🔹 **Problem:** Convert the CFG  
\[
S \to AB \ | \ aA, A \to b \ | \ bS
\]  
to **Chomsky Normal Form (CNF)**.

✅ **Solution:**  
1. **Introduce new variables for terminals:**  
   - Let **X → a**, **Y → b**  
   - Rewrite as:  
     \[
     S \to AB \ | \ XA, A \to Y \ | \ YS
     \]
2. **Check CNF rules**: Each rule now fits **A → BC or A → a**, so this is CNF. ✅

---

## **Unit 4: Turing Machines**
### **Problem 6: Design a Turing Machine for L = {0^n1^n | n ≥ 1}**
✅ **Solution:**
1. **Replace the first 0 with X, find the first 1, replace it with Y.**  
2. **Repeat until all 0’s and 1’s are replaced.**  
3. **If extra 0’s or 1’s remain, reject. Otherwise, accept.**

| State | Read | Write | Move | Next State |
|---|---|---|---|---|
| q0 | 0 | X | R | q1 |
| q1 | 0 | 0 | R | q1 |
| q1 | 1 | Y | L | q2 |
| q2 | 0 | 0 | L | q2 |
| q2 | X | X | R | q0 |
| q0 | Y | Y | R | q3 |
| q3 | (blank) | (blank) | - | Accept |

---

## **Unit 5: Undecidability**
### **Problem 7: Halting Problem**
🔹 **Problem:** Prove that the **Halting Problem** is undecidable.

✅ **Solution:**  
1. Assume there is a **decider T** that determines if a program **halts**.  
2. Construct a new program **H**:  
   - If T says the program **halts**, H enters an infinite loop.  
   - If T says the program **loops**, H halts.  
3. This creates a contradiction! **No such T can exist, so the problem is undecidable.** ❌

---

## **Unit 6: Computational Complexity**
### **Problem 8: Prove that SAT is NP-Complete**
✅ **Solution:**  
1. **SAT is in NP**: Given a satisfying assignment, we can verify it in polynomial time.  
2. **Reduction from 3-SAT**: Convert any boolean formula into conjunctive normal form (CNF).  
3. **If SAT could be solved in polynomial time, P = NP.**  
4. Since no polynomial-time algorithm exists, **SAT is NP-Complete.**

---

## **Conclusion**
These are the key **problems and solutions** that can be asked from **Theory of Computation**. Let me know if you need **more examples or explanations**! 🚀
