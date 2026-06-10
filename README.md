Tribhuvan University · Bagmati Pradesh University · Nepal — BCA / BIT / BSc CSIT
Digital Logic — Model & Old Questions
Compiled from TU / BPU Old Papers (2065–2081) | BCA 1st Sem · BSc CSIT 1st Sem · BIT
Full Marks: 100
Pass Marks: 40
Time: 3 Hours
Total Questions: 50+
Compiled: 2081 BS
Group A – MCQs
Group B – Short Q
Group C – Number Systems
Group D – Boolean/K-map
Group E – Combinational
Group F – Sequential
Group G – Long Q
Group A — Multiple Choice Questions [10 × 1 = 10]
Attempt ALL questions. Each carries 1 mark.
Q1
Which gate is called the "universal gate"?
MCQ
[1]
Answer
a) AND gate
b) NAND gate
c) OR gate
d) XOR gate
NAND (and NOR) gates are called universal gates because any Boolean function can be implemented using only NAND gates (or only NOR gates). This makes them extremely useful in digital circuit design.
Q2
In 2's complement representation, what is the range of an 8-bit signed integer?
MCQ
[1]
Answer
a) −127 to +127
b) −128 to +127
c) −128 to +128
d) 0 to 255
For an n-bit 2's complement number, the range is −2(n−1) to +2(n−1)−1. For n=8: −128 to +127.
Q3
BCD stands for:
MCQ
[1]
Answer
a) Binary Coded Decimal
a) Binary Coded Decimal ✓
b) Bit Coded Data
c) Binary Conversion Digit
Binary Coded Decimal (BCD) represents each decimal digit (0–9) using a 4-bit binary code. Valid states are 0000 to 1001; states 1010–1111 are invalid in BCD.
Q4
The output of a NOR gate is HIGH only when:
MCQ
[1]
Answer
a) At least one input is HIGH
b) All inputs are LOW
c) All inputs are HIGH
d) Inputs are complementary
NOR = NOT + OR. The output is HIGH (1) only when ALL inputs are 0. If any input is 1, the OR output is 1, and NOT makes it 0.
Q5
Which flip-flop eliminates the race-around condition of SR flip-flop?
MCQ
[1]
Answer
a) D Flip-flop
b) Master-Slave JK Flip-flop
c) T Flip-flop
d) RS Flip-flop with enable
The Master-Slave JK flip-flop resolves the race-around condition. The master captures input on the positive clock edge while the slave is isolated; the slave transfers data on the negative edge, preventing feedback loops.
Q6
A 4-to-1 multiplexer has how many select lines?
MCQ
[1]
Answer
a) 4
b) 2
c) 1
d) 3
A 2n-to-1 MUX needs n select lines. For 4-to-1: n = log2(4) = 2 select lines (S1, S0).
Q7
Gray code is also known as:
MCQ
[1]
Answer
a) Reflected binary code
b) Excess-3 code
c) BCD code
d) ASCII code
Gray code is called reflected binary code because consecutive values differ by exactly one bit, making it ideal for analog-to-digital conversion and reducing errors in mechanical encoders.
Q8
Which Boolean law states: A + A'B = A + B?
MCQ
[1]
Answer
a) Idempotent law
b) Absorption law (Consensus theorem)
c) De Morgan's theorem
d) Distributive law
This is the Consensus / Absorption identity: A + A'B = A + B. Proof: A + A'B = (A+A')(A+B) = 1·(A+B) = A+B.
Q9
A MOD-10 counter counts from:
MCQ
[1]
Answer
a) 0 to 10
b) 0 to 9 (10 states)
c) 1 to 10
d) 0 to 15
A MOD-N counter has N states. MOD-10 (decade counter) counts 0→1→2→…→9→0, resetting after 10 counts. It requires a minimum of 4 flip-flops (24=16 ≥ 10).
Q10
PLA stands for:
MCQ
[1]
Answer
a) Programmable Logic Array
b) Parallel Logic Adder
c) Programmable Latch Array
d) Priority Logic Arrangement
PLA (Programmable Logic Array) is an LSI chip with a programmable AND plane and a programmable OR plane. Unlike ROM, only the needed product terms are implemented, making it more flexible and efficient than PAL.
Group B — Short Answer Questions [8 × 5 = 40]
Attempt any EIGHT questions. Each carries 5 marks.
Q11
State and prove De Morgan's First and Second Theorems with logic gates and truth tables.
TU 2066/2067/2071
[5]
Answer
De Morgan's Theorems:
1st Theorem: (A · B)' = A' + B' — The complement of a product equals the sum of complements.
2nd Theorem: (A + B)' = A' · B' — The complement of a sum equals the product of complements.

Truth Table Verification (1st Theorem):
A	B	A·B	(A·B)'	A'	B'	A'+B'
0	0	0	1	1	1	1
0	1	0	1	1	0	1
1	0	0	1	0	1	1
1	1	1	0	0	0	0
Columns (A·B)' and A'+B' are identical → 1st theorem proved.
Logic Gate: NAND gate directly implements (A·B)'. A NOT on each input followed by OR gives A'+B'. Both give same output — proving NAND = NOT-AND = (De Morgan equivalent of) NOR with complemented inputs.
Q12
What is a K-map? Explain the three-variable K-map with example. Simplify: F(A,B,C) = Σ(0,2,4,5,6)
TU 2065/2070/2071
[5]
Answer
Karnaugh Map (K-map): A graphical method to simplify Boolean expressions by grouping adjacent minterms. Adjacent cells differ by exactly one variable (Gray code ordering).

3-variable K-map layout (rows: A; cols: BC in Gray order 00, 01, 11, 10):
A \ BC	00 (m0)	01 (m1)	11 (m3)	10 (m2)
0	1	0	0	1
1	1	1	0	1
Minterms present: m0(000), m2(010), m4(100), m5(101), m6(110)
Groups:
• Group 1: m0, m2, m4, m6 → A column (B=0 in all): simplifies to B' (4-cell group, varies A and C, B=0)
• Group 2: m4, m5 → AB=10, C varies: simplifies to AB'... Reconsidering careful grouping:
• {m0,m2,m4,m6}: all have B=0 → B'
• {m4,m5}: A=1, B=0 → already covered by B'
Minimized expression: F = B' + AC'
(m5 = ABC' also covered by AC' grouping {m4,m5} = AC')
Final SOP: F(A,B,C) = B' + AC'
Q13
Design a Half Adder circuit using only NAND gates. Give truth table, logic equations and gate diagram.
TU 2065/2067/2070
[5]
Answer
Half Adder: Adds two 1-bit numbers. Outputs: Sum (S) and Carry (C).
Equations: S = A ⊕ B   C = A · B

Truth Table:
A	B	Sum (S)	Carry (C)
0	0	0	0
0	1	1	0
1	0	1	0
1	1	0	1
Implementation using only NAND gates:
Let G1 = NAND(A,B) → output = (AB)'
G2 = NAND(A, G1) → A·(AB)' = AB' (part of XOR)
G3 = NAND(G1, B) → (AB)'·B = A'B
G4 = NAND(G2, G3) → S = (AB)' ⊕-like = A⊕B (XOR using 4 NAND gates)
G5 = NAND(G1, G1) → (G1)' = AB → Carry C = AB
Total: 5 NAND gates implement a complete Half Adder.
Q14
Differentiate between Combinational and Sequential Logic Circuits with examples.
TU BCA 2024 / 2069
[5]
Answer
Feature	Combinational Logic	Sequential Logic
Memory	No memory element	Has memory (flip-flops)
Output depends on	Current inputs only	Current inputs + past state
Clock	Not required	Usually required
Feedback	No feedback	Feedback present
Examples	Adder, MUX, Decoder, Encoder	Flip-flop, Counter, Register
Design method	Boolean algebra / K-map	State diagrams / tables
Combinational circuit example: A half adder's output (Sum, Carry) depends only on current A and B inputs.
Sequential circuit example: A 2-bit counter's next state depends on the current count stored in flip-flops.
Q15
Define flip-flop. Explain the Clocked SR Flip-Flop with logic diagram, truth table, characteristic table and excitation table.
TU BCA 2024
[5]
Answer
Flip-flop: A bistable multivibrator — a sequential circuit element that stores one bit (0 or 1) and changes state based on inputs and clock.

Clocked SR Flip-Flop: Has Set (S), Reset (R) inputs and a Clock (CLK). Changes state only on active clock edge.

Truth Table:
CLK	S	R	Q(next)	Condition
↑	0	0	Q	No change
↑	0	1	0	Reset
↑	1	0	1	Set
↑	1	1	X	Forbidden (invalid)
Characteristic equation: Q(t+1) = S + R'Q with condition SR = 0
Excitation Table (what inputs needed for a given state transition):
Q(t)	Q(t+1)	S	R
0	0	0	X
0	1	1	0
1	0	0	1
1	1	X	0
Logic diagram: Two NAND-based SR latches cascaded (master + slave) with CLK gating.
Q16
Define Priority Encoder. Explain the 8-to-3 Priority Encoder in detail.
TU BCA 2024
[5]
Answer
Encoder: Converts 2n input lines to n output lines (reverse of decoder).
Priority Encoder: When multiple inputs are HIGH simultaneously, it encodes the input with the highest priority (usually highest number).

8-to-3 Priority Encoder: 8 inputs (I0–I7), 3 outputs (A2 A1 A0), plus a Valid output (V).
Priority: I7 > I6 > I5 > … > I0
Truth Table (partial):
I7	I6	I5	I4	I3	I2	I1	I0	A2	A1	A0
0	0	0	0	0	0	0	1	0	0	0
0	0	0	0	0	0	1	X	0	0	1
0	0	0	0	0	1	X	X	0	1	0
0	0	0	1	X	X	X	X	1	0	0
1	X	X	X	X	X	X	X	1	1	1
Output equations:
A2 = I4 + I5 + I6 + I7
A1 = I2 + I3 + I6·I4' + I7·I5'·I4'
A0 = I1 + I3 + I5 + I7
Q17
Explain the Duality Theorem with example. Draw logic gates for: F = AB + CB'D' + BC'
TU BCA 2024
[5]
Answer
Duality Theorem: Every Boolean identity has a dual obtained by: (1) replacing AND (·) with OR (+), (2) replacing OR (+) with AND (·), and (3) replacing 0 with 1 and 1 with 0. The dual expression is also valid.

Example:
Original: A + 0 = A    Dual: A · 1 = A ✓
Original: A + A = A    Dual: A · A = A ✓
Original: A + A' = 1   Dual: A · A' = 0 ✓

Logic circuit for F = AB + CB'D' + BC':
Level 1 (AND gates): Gate1 = A·B, Gate2 = C·B'·D', Gate3 = B·C'
Level 2 (OR gate): F = Gate1 + Gate2 + Gate3
Three 2-input AND gates (Gate2 is 3-input) feeding into a 3-input OR gate.
Q18
What is a Ripple Counter? Explain the 4-bit Ripple (Asynchronous) Counter with truth table and timing diagram description.
TU CSIT 2065/2070/2073
[5]
Answer
Ripple Counter (Asynchronous Counter): A counter where flip-flops are connected in series. The output of each flip-flop acts as the clock for the next. The signal "ripples" through — hence the name.

4-bit ripple counter using T flip-flops (or JK with J=K=1):
• FF0 clocked by external CLK → toggles every clock pulse
• FF1 clocked by Q0 → toggles every 2 pulses
• FF2 clocked by Q1 → toggles every 4 pulses
• FF3 clocked by Q2 → toggles every 8 pulses

Count Sequence (Q3 Q2 Q1 Q0):
Count	Q3	Q2	Q1	Q0
0	0	0	0	0
1	0	0	0	1
2	0	0	1	0
4	0	1	0	0
8	1	0	0	0
15	1	1	1	1
16→0	0	0	0	0
Disadvantage: Propagation delay accumulates — Q3 changes long after CLK edge. This is the main limitation vs. synchronous counters.
Q19
What is a Shift Register? Explain types of shift registers.
TU CSIT 2065/2072/2073
[5]
Answer
Shift Register: A group of flip-flops connected in series used to store and shift data (left or right) by one bit position on each clock pulse.

Types:
1. SISO (Serial-In, Serial-Out): Data enters one bit at a time from one end and exits one bit at a time from the other end. Used in data transmission/communication.

2. SIPO (Serial-In, Parallel-Out): Data enters serially but all bits are available simultaneously. Used for serial-to-parallel conversion (e.g., UART receiver).

3. PISO (Parallel-In, Serial-Out): Data is loaded in parallel but shifted out serially. Used for parallel-to-serial conversion (e.g., UART transmitter).

4. PIPO (Parallel-In, Parallel-Out): Data enters and exits simultaneously. Fastest type; used as a buffer or temporary storage.

5. Bidirectional Shift Register: Can shift both left and right, controlled by a direction bit. The 74HC194 is a classic IC example.
Q20
Design a Full Adder circuit using a Decoder and two OR gates.
TU BCA 2024
[5]
Answer
Full Adder: Has inputs A, B, Cin and outputs Sum (S) and Carry-out (Cout).

Minterms:
S = Σ(1, 2, 4, 7) — sum is 1 for odd number of 1s
Cout = Σ(3, 5, 6, 7) — carry is 1 when two or more inputs are 1

Implementation using a 3-to-8 Decoder:
• A 3-to-8 decoder with inputs A, B, Cin generates all 8 minterms (m0–m7)
• Sum S: Connect outputs m1, m2, m4, m7 to a 4-input OR gate
• Carry Cout: Connect outputs m3, m5, m6, m7 to another 4-input OR gate

Why it works: Each decoder output is exactly one minterm. OR-ing the required minterms directly gives the output function without any additional logic simplification needed.
Group C — Number System & Arithmetic [5 × 5 = 25]
Attempt any FIVE. Each carries 5 marks.
Q21
Convert the following: (a) (304)10 → Hex & Octal   (b) (1760.46)8 → Hex
TU CSIT 2065/2066
[5]
Answer
(a) 304₁₀ → Hexadecimal:
304 ÷ 16 = 19 remainder 0 19 ÷ 16 = 1 remainder 3 1 ÷ 16 = 0 remainder 1 Reading remainders bottom to top: (304)₁₀ = (130)₁₆
304₁₀ → Octal:
304 ÷ 8 = 38 remainder 0 38 ÷ 8 = 4 remainder 6 4 ÷ 8 = 0 remainder 4 Result: (304)₁₀ = (460)₈
(b) (1760.46)₈ → Hexadecimal:
Step 1 – Convert each octal digit to 3-bit binary:
1=001 7=111 6=110 0=000 . 4=100 6=110 Binary: 001 111 110 000 . 100 110
Step 2 – Regroup in groups of 4 from the decimal point:
Integer: 0001 1111 1000 0000 → 1 F 8 0 Fraction: .1001 10__ → .98__ Result: (1760.46)₈ = (1F80.98...)₁₆
Q22
Subtract 1010101.101 − 1000100.001 using (a) 1's complement and (b) 2's complement method.
TU BCA 2024
[5]
Answer
A = 1010101.101   B = 1000100.001   We compute A − B.

(a) 1's Complement Method:
1's complement of B (1000100.001): 0111011.110 Add A + 1's comp(B): 1010101.101 + 0111011.110 ----------- 10010001.011 ← carry out (end-around carry) + 0000000.001 ← add carry back ----------- 0010001.100
Result: 0010001.100₂ = (17.5)₁₀ (positive, correct since A > B)

(b) 2's Complement Method:
2's complement of B = 1's comp + 1: 0111011.110 + 0000000.001 = 0111011.111 Add A: 1010101.101 + 0111011.111 ----------- 10010001.100 ← carry out, discard it Result: 0010001.100
Result: 0010001.100₂ — identical, confirmed.
Q23
Convert (A08E.FA)₁₆ to decimal. Also convert (0FFF)₁₆ to decimal and octal.
TU CSIT 2072
[5]
Answer
A08E.FA₁₆ → Decimal:
A=10, 0=0, 8=8, E=14, F=15, A=10 Integer part A08E: 10×16³ + 0×16² + 8×16¹ + 14×16⁰ = 10×4096 + 0 + 128 + 14 = 40960 + 128 + 14 = 41102 Fraction .FA: 15×16⁻¹ + 10×16⁻² = 0.9375 + 0.039063 = 0.976563 Result: (A08E.FA)₁₆ = (41102.9766)₁₀
0FFF₁₆ → Decimal:
0×16³ + 15×16² + 15×16 + 15 = 0 + 3840 + 240 + 15 = 4095 (0FFF)₁₆ = (4095)₁₀
4095₁₀ → Octal:
4095 ÷ 8 = 511 r 7 511 ÷ 8 = 63 r 7 63 ÷ 8 = 7 r 7 7 ÷ 8 = 0 r 7 (4095)₁₀ = (7777)₈
Q24
Convert (3EC8)₁₆ into binary, decimal and octal.
TU CSIT 2071
[5]
Answer
Hex to Binary (direct substitution):
3 E C 8 0011 1110 1100 1000 (3EC8)₁₆ = (0011111011001000)₂
Hex to Decimal:
3×16³ + 14×16² + 12×16¹ + 8×16⁰ = 3×4096 + 14×256 + 12×16 + 8 = 12288 + 3584 + 192 + 8 = (16072)₁₀
Hex to Octal (via binary, regroup in 3s):
Binary: 0 011 111 011 001 000 Octal: 0 3 7 3 1 0 (3EC8)₁₆ = (37310)₈
Q25
What is Gray code? Convert (13)₁₀ to Gray code and back. State its applications.
TU CSIT 2072
[5]
Answer
Gray Code: A binary numbering system where consecutive values differ by only one bit. Also called reflected binary code. It minimizes switching errors in digital systems.

Decimal 13 → Binary → Gray:
(13)₁₀ = (1101)₂ Binary to Gray conversion rules: - MSB of Gray = MSB of binary - Each subsequent Gray bit = XOR of current and previous binary bit Binary: 1 1 0 1 ↓ ↓ ↓ ↓ Gray: 1 1⊕1 1⊕0 0⊕1 = 1 0 1 1 (13)₁₀ = (1011) in Gray code
Gray back to Binary:
Gray: 1 0 1 1 Binary: 1 1⊕0 1⊕1 1⊕1 = 1 1 0 1 = 1101₂ = 13 ✓
Applications: Analog-to-digital converters, shaft encoders (optical/magnetic), error detection in digital communication, Karnaugh map cell ordering.
Group D — Boolean Algebra & K-map Simplification [5 × 5 = 25]
Attempt any FIVE.
Q26
Simplify using K-map: F(A,B,C,D) = Σ(0,1,3,7,8,9,11,15)
Classic TU type
[5]
Answer
4-variable K-map (AB vs CD, Gray order):
AB\CD	00	01	11	10
00	1(m0)	1(m1)	1(m3)	0
01	0	0	1(m7)	0
11	0	0	1(m15)	0
10	1(m8)	1(m9)	1(m11)	0
Groups:
• {m0, m1, m8, m9}: AB=00 or 10, CD=00 or 01 → B'D'... check: all have B=0, D=0 or 1. Actually B=0 for all, C=0 for all → B'C'
• {m1, m3, m9, m11}: D=1, B=0 → B'D
• {m3, m7, m11, m15}: CD=11 for all → CD
Simplifying overlaps: using essential prime implicants:
Minimized: F = B'C' + CD
(Verify: m0✓m1✓m3✓m7✓m8✓m9✓m11✓m15✓ — all covered)
Q27
Simplify using K-map: F(p,q,r,s) = Σ(3,4,7,8,14) with don't-care d(p,q,r,s) = Σ(1,6,9,13). Design using minimum NAND gates.
TU BCA 2024
[5]
Answer
4-variable K-map with don't cares (X):
pq\rs	00	01	11	10
00	0	X(1)	1(3)	0
01	1(4)	0	1(7)	X(6)
11	0	X(13)	1(15)→dc	1(14)
10	1(8)	X(9)	0	0
Groups using don't-cares:
• {m3, m7, X6, X1} area: consider {m3,m7,X6}: q=0 covered, check → qs (m3,m7) = group of 2
• {m4, m7, X6}: q=1,r=0... → form groups carefully. Best PI groups:
– {m3, m7}: p=0, r=1, s=1 → p'rs
– {m4, X6}: p=0,q=1, s=0 → p'qs' (uses X6)
– {m8, X9}: p=1,q=0,r=0 → pq'r'
– {m14}: p=1,q=1,r=1,s=0 → pqrs'
F = p'rs + p'qs' + pq'r' + pqrs'

NAND implementation: Apply De Morgan's twice (double inversion): each AND term becomes a NAND gate; the OR becomes a NAND of inverted inputs = final NAND-NAND two-level circuit.
Q28
Prove the following Boolean identities: (a) A + A'B = A + B   (b) A(A'+B) = AB
Boolean Algebra
[5]
Answer
(a) Proof: A + A'B = A + B
LHS = A + A'B = (A + A')(A + B) [Distributive: X + YZ = (X+Y)(X+Z)] = 1 · (A + B) [A + A' = 1] = A + B = RHS ✓
Truth Table Verification:
A	B	A'B	A+A'B	A+B
0	0	0	0	0
0	1	1	1	1
1	0	0	1	1
1	1	0	1	1
(b) Proof: A(A'+B) = AB
LHS = A·A' + A·B [Distributive] = 0 + AB [A·A' = 0] = AB = RHS ✓
Q29
Simplify using K-map: F(X,Y,Z) = Σ(0,3,2,5) and F(A,B,C) = Σ(0,2,4,5,6)
TU CSIT 2071
[5]
Answer
F(X,Y,Z) = Σ(0,2,3,5) — 3-variable K-map:
X\YZ	00	01	11	10
0	1(m0)	0	1(m3)	1(m2)
1	0	1(m5)	0	0
Groups: {m0,m2}: X=0,Z=0 → X'Z'; {m2,m3}: X=0,Y=1 → X'Y; {m3}: standalone → already grouped; {m5}: XYZ'→XY'Z
F = X'Z' + X'Y + XY'Z (or simplified further using consensus)

F(A,B,C) = Σ(0,2,4,5,6):
A\BC	00	01	11	10
0	1(0)	0	0	1(2)
1	1(4)	1(5)	0	1(6)
Groups: {m0,m2,m4,m6}: C=0 → C'; {m4,m5}: A=1,B=0 → AB'
F(A,B,C) = C' + AB'
Q30
Show that both NAND and NOR gates are universal gates. Realize AND, OR, NOT using (a) only NAND, (b) only NOR.
TU CSIT 2072
[5]
Answer
Using only NAND gates:
NOT: Connect both inputs of NAND to same signal A NAND(A,A) = (A·A)' = A' ✓ AND: NAND output = (AB)'. Apply NOT: NAND(NAND(A,B), NAND(A,B)) = AB ✓ OR: By De Morgan: A+B = (A'·B')' = NAND(A',B') = NAND(NAND(A,A), NAND(B,B)) ✓
Using only NOR gates:
NOT: NOR(A,A) = (A+A)' = A' ✓ OR: NOR output = (A+B)'. Apply NOT: NOR(NOR(A,B), NOR(A,B)) = A+B ✓ AND: By De Morgan: A·B = (A'+B')' = NOR(A',B') = NOR(NOR(A,A), NOR(B,B)) ✓
Since any combinational function can be built from NOT, AND, and OR — and both NAND and NOR can implement all three — they are universal gates.
Group E — Combinational Circuits [5 × 5 = 25]
Attempt any FIVE.
Q31
What is a Multiplexer? Draw the logic diagram and truth table of a 4×1 MUX. Implement it using only universal gates.
TU CSIT 2069/2073
[5]
Answer
Multiplexer (MUX): A data selector — it connects one of 2n input lines to a single output line based on n select signals.

4×1 MUX: 4 data inputs (I0–I3), 2 select lines (S1, S0), 1 output Y.
Boolean expression:
Y = I0·S1'·S0' + I1·S1'·S0 + I2·S1·S0' + I3·S1·S0

Truth Table (function selection):
S1	S0	Output Y
0	0	I0
0	1	I1
1	0	I2
1	1	I3
Logic diagram: Four 3-input AND gates (each gated by S1, S0 and one data input) feeding into a 4-input OR gate.
NAND implementation: Replace each AND gate with NAND, then use NAND-NAND equivalent of the final OR gate (De Morgan: OR = NAND of NANDs).
Q32
What is a Decoder? Design a 3-to-8 line decoder using two 2-to-4 line decoders. Implement F(W,X,Y,Z) = Σ(0,1,3,4,8,9,10) using a 4-to-16 decoder.
TU CSIT 2067/2069
[5]
Answer
Decoder: Converts n input lines to a maximum of 2n unique output lines (exactly one output is HIGH for each input combination).

3-to-8 Decoder from two 2-to-4 decoders:
• Use the MSB (A2) as the enable signal.
• When A2=0: first 2-to-4 decoder is enabled → outputs m0–m3
• When A2=1: second 2-to-4 decoder is enabled → outputs m4–m7
• Inputs A1, A0 connect to both decoders in parallel.

Implementing F(W,X,Y,Z) = Σ(0,1,3,4,8,9,10):
With a 4-to-16 decoder generating all 16 minterms:
Connect decoder outputs m0, m1, m3, m4, m8, m9, m10 to a 7-input OR gate.
F = D0 + D1 + D3 + D4 + D8 + D9 + D10
where D_i is the i-th decoder output.
Q33
What is a magnitude comparator? Design a 4-bit magnitude comparator explaining A>B, A=B, A<B conditions.
TU CSIT 2067/2070/2072/2073
[5]
Answer
Magnitude Comparator: A combinational circuit that compares two n-bit binary numbers A and B and produces three outputs: A>B, A=B, A<B.

1-bit comparator logic:
A = B ↔ xi = (Ai XNOR Bi) = Ai'Bi' + AiBi A > B ↔ Ai=1 and Bi=0 → AiBi' A < B ↔ Ai=0 and Bi=1 → Ai'Bi
4-bit (A = A3A2A1A0, B = B3B2B1B0):
Define xi = Ai⊙Bi (XNOR of each bit pair) — xi=1 means bits are equal.
A = B : x3·x2·x1·x0 = 1 A > B : A3B3' + x3·A2B2' + x3·x2·A1B1' + x3·x2·x1·A0B0' A < B : A3'B3 + x3·A2'B2 + x3·x2·A1'B1 + x3·x2·x1·A0'B0
The 74HC85 is a standard IC implementing a 4-bit magnitude comparator with cascadable inputs for larger comparisons.
Q34
Explain the Programmable Logic Array (PLA) with block diagram. Compare PLA with PAL.
TU CSIT 2068/2069/2071
[5]
Answer
PLA (Programmable Logic Array): An LSI device with two programmable planes:
1. Programmable AND plane — generates required product terms (minterms)
2. Programmable OR plane — sums selected product terms to produce outputs

Block structure:
[Inputs] → [Programmable AND plane] → [Product terms] → [Programmable OR plane] → [Outputs] (generates minterms) (ORs selected terms)
PLA vs PAL Comparison:
Feature	PLA	PAL
AND plane	Programmable	Programmable
OR plane	Programmable	Fixed
Flexibility	More flexible	Less flexible
Speed	Slower (two delays)	Faster (one delay)
Area	Larger	Smaller
Cost	Higher	Lower
PLA advantage: Multiple outputs can share product terms, saving silicon area for complex multi-output functions.
Q35
Design a BCD to 2's complement converter (4 inputs representing BCD digit, 4 outputs). Give truth table and circuit.
TU BCA 2024 (Group C)
[5]
Answer
BCD inputs: A, B, C, D (ABCD = 0000 to 1001). States 1010–1111 are don't-cares.

Truth Table (BCD → 2's complement):
Decimal	A	B	C	D	W	X	Y	Z
0	0	0	0	0	0	0	0	0
1	0	0	0	1	1	1	1	1
2	0	0	1	0	1	1	1	0
3	0	0	1	1	1	1	0	1
4	0	1	0	0	1	1	0	0
5	0	1	0	1	1	0	1	1
6	0	1	1	0	1	0	1	0
7	0	1	1	1	1	0	0	1
8	1	0	0	0	1	0	0	0
9	1	0	0	1	0	1	1	1
The 2's complement of decimal 0 is 0; for 1–9, negate and add 1. W=1 indicates a negative number (two's complement representation).
Minimize each output (W, X, Y, Z) using 4-variable K-maps with don't-cares for inputs 10–15.
Group F — Sequential Circuits & Flip-Flops [5 × 5 = 25]
Attempt any FIVE.
Q36
How does a JK flip-flop differ from an SR flip-flop? Draw the JK FF logic diagram and truth table. Convert JK to D flip-flop.
TU CSIT 2069/2071/2072
[5]
Answer
SR vs JK Differences:
Feature	SR Flip-Flop	JK Flip-Flop
Invalid state	S=R=1 is forbidden	No forbidden state
J=K=1 behavior	Undefined	Toggles (Q changes)
Race condition	Possible	Resolved with Master-Slave
Versatility	Less versatile	Most versatile FF
JK Truth Table:
J	K	Q(t+1)	Operation
0	0	Q(t)	No change
0	1	0	Reset
1	0	1	Set
1	1	Q'(t)	Toggle
Characteristic equation: Q(t+1) = JQ' + K'Q

JK → D conversion:
D FF: Q(t+1) = D
JK: Q(t+1) = JQ' + K'Q = D
Set J = D and K = D' → then JQ'+K'Q = DQ' + DQ = D(Q'+Q) = D ✓
Q37
Design a MOD-6 Synchronous Counter using T flip-flops. Give state diagram, excitation table and logic diagram.
TU CSIT 2069 / 2071
[5]
Answer
MOD-6 counter: Counts 0→1→2→3→4→5→0. Needs 3 flip-flops (2³=8 ≥ 6). States 6 and 7 are unused (don't-care for T inputs).

State/Excitation Table (Q2 Q1 Q0 → next state, T inputs):
Q2	Q1	Q0	Q2+	Q1+	Q0+	T2	T1	T0
0	0	0	0	0	1	0	0	1
0	0	1	0	1	0	0	1	1
0	1	0	0	1	1	0	0	1
0	1	1	1	0	0	1	1	1
1	0	0	1	0	1	0	0	1
1	0	1	0	0	0	1	0	1
T flip-flop: T=Q⊕Q_next (toggles when T=1, holds when T=0)

K-map simplified equations:
T0 = 1 (always toggles)
T1 = Q1'Q0 + Q1Q0 = Q0 (simplified)
T2 = Q2'Q1Q0 + Q2Q0 = Q2Q0 + Q1Q0 → T2 = Q0(Q2+Q1)
Q38
Explain the Master-Slave SR Flip-Flop with logic diagram, truth table and timing diagram. How does it resolve the race condition?
TU CSIT 2067/2072
[5]
Answer
Race Condition: In a level-triggered SR FF, when CLK=1, the output Q changes and feeds back through the gates while the clock is still HIGH, causing unpredictable oscillations.

Master-Slave solution:
Master FF ←── Inputs S, R ←── CLK (active HIGH) Slave FF ←── Master output ←── CLK' (active LOW, inverted) Sequence: 1. CLK=1: Master is ENABLED, captures S and R. Slave is DISABLED (CLK'=0). 2. CLK=0: Master is DISABLED (inputs locked). Slave is ENABLED, transfers master output to Q. Result: Output Q changes ONLY at the falling edge of CLK. Master captures → Slave transfers → never both active simultaneously.
Truth Table: Same as SR flip-flop (no forbidden behavior for S=R=1 in JK version, but SR master-slave still has S=R=1 forbidden).
Key advantage: The master's output is stable before the slave captures it, eliminating oscillation.
Q39
Differentiate between counter and shift register. Explain serial-in parallel-out (SIPO) shift register with diagram.
TU CSIT 2072
[5]
Answer
Counter vs Shift Register:
Feature	Counter	Shift Register
Primary function	Count events/pulses	Store and shift data
Input	Clock only (usually)	Serial or parallel data
Feedback	Has feedback	No feedback (linear)
Applications	Frequency divider, timers	Data conversion, delay lines

SIPO Shift Register (4-bit):
4 D flip-flops connected in series. Serial data enters FF0; Q0 feeds D of FF1; Q1 feeds FF2; Q2 feeds FF3.
CLK 1 2 3 4 D_in 1 0 1 1 (input bits, MSB first) After CLK1: FF0=1, rest=0 → Q3Q2Q1Q0 = 0001 After CLK2: FF0=0, FF1=1 → 0010 After CLK3: FF0=1, FF1=0, → 0101 After CLK4: FF0=1, → 1011 ← all 4 bits available in parallel
Application: UART receiver converting serial data from RS-232 to parallel bus data.
Q40
A sequential circuit has 2 D flip-flops A, B; inputs x, y; output z. Given: A(t+1)=xy'+xB, B(t+1)=x'B+xA, z=A. Derive state table and state diagram.
TU BCA 2024 (Group C)
[10]
Answer
Next-state equations (given):
A(t+1) = xy' + xB
B(t+1) = x'B + xA
z = A

State Table (current state AB, inputs xy → next state A+B+, output z):
A	B	x	y	A+	B+	z
0	0	0	0	0	0	0
0	0	0	1	0	0	0
0	0	1	0	1	0	0
0	0	1	1	0	0	0
0	1	0	0	0	1	0
0	1	0	1	0	1	0
0	1	1	0	1	0	0
0	1	1	1	1	0	0
1	0	0	0	0	0	1
1	0	0	1	0	0	1
1	0	1	0	1	1	1
1	0	1	1	0	1	1
1	1	0	0	0	1	1
1	1	0	1	0	1	1
1	1	1	0	1	1	1
1	1	1	1	1	1	1
State diagram: 4 states (S00, S01, S10, S11) with arcs labeled xy/z. The output z=1 whenever A=1 (Moore machine).
Group G — Long Answer Questions [2 × 10 = 20]
Attempt any TWO. Each carries 10 marks.
Q41
Design a 4-bit Synchronous Up/Down Counter using JK flip-flops. Give truth table, excitation table, K-map simplification and timing diagram description.
TU CSIT 2072 (Long)
[10]
Answer
Up/Down Counter: A control input M selects direction. M=1 → count up (0→15→0), M=0 → count down (0→15→14→...→0).

Design approach: Using JK flip-flops (Q3 Q2 Q1 Q0)

Key equations derived from excitation tables:
For UP counter (M=1):
J0=K0=1 (Q0 always toggles)
J1=K1=Q0 (Q1 toggles when Q0=1)
J2=K2=Q1Q0 (Q2 toggles when Q1=Q0=1)
J3=K3=Q2Q1Q0 (Q3 toggles when Q2=Q1=Q0=1)

For DOWN counter (M=0):
J0=K0=1
J1=K1=Q0' (toggle on borrow)
J2=K2=Q1'Q0'
J3=K3=Q2'Q1'Q0'

Combined Up/Down expressions:
J1=K1 = MQ0 + M'Q0'
J2=K2 = M(Q1Q0) + M'(Q1'Q0')
J3=K3 = M(Q2Q1Q0) + M'(Q2'Q1'Q0')

Count sequence (Up, M=1):
Count	Q3	Q2	Q1	Q0
0	0	0	0	0
1	0	0	0	1
2	0	0	1	0
7	0	1	1	1
15	1	1	1	1
16→0	0	0	0	0
Timing diagram: Q0 toggles every clock; Q1 toggles every 2 clocks; Q2 every 4; Q3 every 8 — all flip-flops are clocked by the same CLK (synchronous), so no ripple delay.
Q42
Explain the 16×1 Multiplexer with block diagram, truth table and logic circuit. Also explain the 4-bit Ripple Counter with timing diagram.
TU CSIT 2065 (Long)
[10]
Answer
16×1 Multiplexer:
• 16 data inputs: I0–I15
• 4 select lines: S3, S2, S1, S0
• 1 output: Y
• Output equation: Y = I(S3S2S1S0) — selects the input whose binary address equals the select value

Implementation: A 16×1 MUX can be built from:
Option 1: Two 8×1 MUXes + one 2×1 MUX (use S3 to select between them)
Option 2: Four 4×1 MUXes feeding into a 4×1 MUX (two levels)

Truth Table (partial):
S3	S2	S1	S0	Output Y
0	0	0	0	I0
0	0	0	1	I1
0	0	1	0	I2
1	1	1	1	I15
4-bit Ripple Counter (see Q18 for detail):
Each FF clocked by previous FF's Q output. Q0 at f, Q1 at f/2, Q2 at f/4, Q3 at f/8.
Timing: Q0 has the fastest waveform (half CLK period), each subsequent FF is half the frequency of the previous one. The 4-bit counter divides the input clock by 16.
Q43
Design a Synchronous MOD-10 counter to count in sequence 0,2,4,5,6,8 using T flip-flops. Give the state diagram and next-state table.
TU BCA 2024 (Long)
[10]
Answer
Count sequence: 0→2→4→5→6→8→0 (6 states, non-standard)
Needs 4 flip-flops (Q3Q2Q1Q0). States not in sequence are don't-cares.

State Table:
State	Q3	Q2	Q1	Q0	Q3+	Q2+	Q1+	Q0+	T3	T2	T1	T0
0	0	0	0	0	0	0	1	0	0	0	1	0
2	0	0	1	0	0	1	0	0	0	1	1	0
4	0	1	0	0	0	1	0	1	0	0	0	1
5	0	1	0	1	0	1	1	0	0	0	1	1
6	0	1	1	0	1	0	0	0	1	1	1	0
8	1	0	0	0	0	0	0	0	1	0	0	0
T = Q ⊕ Q_next (T flip-flop toggles when T=1, holds when T=0)

Minimize T equations using K-maps (with don't-cares for unused states 1,3,7,9,10–15):
From the table above, derive minimized SOP expressions for T3, T2, T1, T0.
Example: T3 = Q2Q1 + Q3 (resets to 0 after state 8)

State Diagram:
0 → 2 → 4 → 5 → 6 → 8 → 0 (circular sequence)
Bonus — Short Notes & Additional Questions
Additional questions frequently asked in VIT/BIT/BCA exams.
Q44
Write short note on: Synchronous vs Asynchronous Counter
TU 2068/2070
[5]
Answer
Feature	Synchronous Counter	Asynchronous Counter
Clock	All FFs share same CLK	Each FF clocked by previous Q
Speed	Faster (no ripple delay)	Slower (cumulative delay)
Glitches	None	Present (ripple effect)
Complexity	More complex logic	Simpler design
Power	More power	Less power
Example IC	74HC163	74HC93
Q45
Write short note on: State Reduction Table
TU BCA 2024 / 2068
[5]
Answer
State Reduction: The process of minimizing the number of states in a sequential circuit without changing its input-output behavior.

Steps:
1. Build the state table with present state, input, next state, output
2. Identify equivalent states: two states are equivalent if for all inputs they produce the same output and transition to equivalent next states
3. Merge equivalent states — replace them with a single state
4. Repeat until no further reduction is possible

Implication chart method: A triangular table of state pairs. Mark pairs that cannot be equivalent (different outputs). Propagate: if Si≡Sj requires Sk≡Sl and Sk≢Sl, then Si≢Sj. Remaining unmarked pairs are equivalent.

Benefit: Reduces hardware (fewer flip-flops, simpler combinational logic) and improves reliability.
Q46
Explain triggering of flip-flops: level triggering vs edge triggering
TU CSIT 2069
[5]
Answer
Triggering determines when a flip-flop responds to its inputs relative to the clock signal.

Level Triggering: FF responds when clock is at a specific level (HIGH or LOW). The output can change multiple times during the active level if inputs change — susceptible to glitches and race conditions.

Edge Triggering: FF responds only at the transition of the clock signal (rising or falling edge).
• Positive edge triggered: responds on 0→1 transition (↑)
• Negative edge triggered: responds on 1→0 transition (↓)
Input changes between edges are ignored — more reliable and predictable.

Comparison:
Feature	Level Triggered	Edge Triggered
Trigger condition	CLK = 1 or 0	CLK ↑ or ↓
Race condition	Possible	Eliminated
Usage	Latches (SR, D latch)	Flip-flops (D-FF, JK-FF)
Q47
What is EBCDIC? Compare ASCII, EBCDIC, and Unicode.
TU CSIT 2065
[5]
Answer
Feature	ASCII	EBCDIC	Unicode (UTF-8)
Full form	American Standard Code for Information Interchange	Extended Binary Coded Decimal Interchange Code	Universal Character Set
Bits per char	7-bit (128 chars) / Extended 8-bit	8-bit (256 chars)	Variable (8–32 bits)
Developed by	ANSI (1963)	IBM (1964)	Unicode Consortium (1991)
Usage	Most computers, internet	IBM mainframes	Web, all modern systems
Characters	English + control codes	English + IBM extensions	All world languages (1M+)
Backward compat	—	Not compatible with ASCII	ASCII subset (first 128)
Q48
Explain the Decimal Adder (BCD Adder) with circuit diagram and example.
TU CSIT 2066/2067/2069
[5]
Answer
BCD Adder: Adds two BCD digits (0–9). Since BCD only uses 0000–1001, sums ≥ 10 (1010–10010) must be corrected by adding 6 (0110) to get valid BCD result + carry.

Correction logic: If sum S ≥ 10, add 6 (0110).
Correction needed when: Z = C_out + S3S2 + S3S1 (Z=1 means correction required)

Example: 8 + 5 = 13 (BCD)
Binary: 1000 + 0101 = 1101 (=13, but invalid BCD!) Correction: Z=1 (>9), add 0110 1101 + 0110 = 10011 Result: carry=1, BCD digit=0011 → (1)(3) = 13 in BCD ✓
Circuit: Two stages — (1) 4-bit binary adder sums the two BCD digits, (2) correction logic detects overflow and a second adder adds 0110 if needed.
Q49
What is a Demultiplexer? Draw a 1-to-16 DEMUX and explain its working principle.
TU CSIT 2068/2071
[5]
Answer
Demultiplexer (DEMUX): The reverse of a MUX — routes one input signal to one of 2n output lines based on n select lines. Also called a data distributor.

1-to-16 DEMUX:
• 1 data input (D)
• 4 select lines (S3, S2, S1, S0)
• 16 output lines (Y0–Y15)

Output equation: Yi = D · (select = i)
e.g., Y0 = D·S3'·S2'·S1'·S0'   Y15 = D·S3·S2·S1·S0

Working: The select lines form a 4-bit address. The AND gate corresponding to that address is enabled, routing D to that output only. All other outputs remain 0.

Implementation: A 1-to-16 DEMUX can be built from one 1-to-2 DEMUX (using S3) → two 1-to-4 DEMUXes → four 1-to-4 DEMUXes (hierarchical expansion).

Applications: Data routing in networks, address decoding in memory systems, time-division demultiplexing.
Q50
Write short notes on: (a) Memory Unit (RAM vs ROM)   (b) CMOS Technology   (c) Error Detection Codes (Parity)
TU CSIT 2069/2071
[5]
Answer
(a) Memory Unit:
Feature	RAM	ROM
Full form	Random Access Memory	Read Only Memory
Type	Volatile	Non-volatile
R/W	Read and Write	Read only
Use	Temporary storage, working memory	Firmware, BIOS, bootloader

(b) CMOS (Complementary Metal-Oxide Semiconductor):
CMOS uses complementary pairs of p-type and n-type MOSFETs. When input is HIGH, NMOS turns ON, PMOS OFF → output LOW. When input is LOW, PMOS ON, NMOS OFF → output HIGH. Key advantage: Very low static power consumption (current flows only during switching). Used in modern CPUs, FPGAs, and all digital ICs.

(c) Parity — Error Detection:
A parity bit is an extra bit added to a binary data word to make the total number of 1s either even (even parity) or odd (odd parity).
Example: Data = 1011001. Count of 1s = 4 (even). For even parity → parity bit = 0. Transmitted: 10110010.
If one bit flips during transmission, the parity count changes and an error is detected. Parity cannot detect 2-bit errors or correct errors (for correction, use Hamming code).
Compiled from TU BCA / BSc CSIT old papers (2065–2081) + BPU / Nepal University sources
Sources: ictbyte.com · sbhuwan.com.np · bcanotesnepal.com · hamrocsit.com
Prepared for: BCA 1st Sem · BSc CSIT 1st Sem · BIT students — Nepal
For study use only · Verify with your college's official syllabus
