# Lab 1: Introduction to Digital Logic
## Instalation of Logisim evaluation :

<img width="836" height="533" alt="image" src="https://github.com/user-attachments/assets/f94ff62c-6380-4f7b-9e57-854596494d57" />

## Experiment 1: OR Gate Using NOR Gates

### Objective

To implement an OR gate using only NOR gates.

### Theory

A NOR gate produces the inverse of an OR operation:

$$
A \downarrow B = \overline{A+B}
$$

Using two NOR gates, the OR output becomes:

$$
Y = (A \downarrow B) \downarrow (A \downarrow B) = A+B
$$

### NOR Gate Truth Table

| A | B | A NOR B |
|---|---|---------|
| 0 | 0 | 1 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 0 |

### Circuit Steps

1. Connect `A` and `B` to the first NOR gate.
2. Connect the first NOR output to both inputs of the second NOR gate.
3. The output of the second NOR gate is the OR result.

 
<img width="674" height="218" alt="image" src="https://github.com/user-attachments/assets/c6d7cc69-947d-4569-bb91-e56105b5aad3" />

### Output Table

| A | B | Y = A OR B |
|---|---|------------|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |




### Conclusion

An OR gate was implemented successfully with two NOR gates.

---

## Experiment 2: OR Gate Using NAND Gates

### Objective

To implement an OR gate using only NAND gates.

### Theory

A NAND gate can act as a NOT gate when both of its inputs are connected together:

$$
\overline{A} = A \text{ NAND } A
$$

By De Morgan's law:

$$
A+B = \overline{\overline{A} \cdot \overline{B}}
$$

### NAND Gate Truth Table

| A | B | A NAND B |
|---|---|----------|
| 0 | 0 | 1 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

### Circuit Steps

1. Use one NAND gate to invert `A`.
2. Use another NAND gate to invert `B`.
3. Connect both inverted signals to a third NAND gate.
4. The final output is `A OR B`.

<img width="717" height="359" alt="image" src="https://github.com/user-attachments/assets/f70c17bd-d841-4972-a13f-63aa5b641091" />


### Output Table

| A | B | Y = A OR B |
|---|---|------------|
| 0 | 0 | 0 |                       
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

### Conclusion

The OR operation was produced using three NAND gates.

---

## Experiment 3: AND Gate Using NOR Gates

### Objective

To implement an AND gate using only NOR gates.

### Theory

First, invert both inputs:

$$
\overline{A} = A \downarrow A
$$

$$
\overline{B} = B \downarrow B
$$

Then connect them to another NOR gate:

$$
Y = \overline{\overline{A}+\overline{B}} = A \cdot B
$$

### Circuit Steps

1. Connect `A` to both inputs of the first NOR gate.
2. Connect `B` to both inputs of the second NOR gate.
3. Connect both outputs to the last NOR gate.

 

<img width="741" height="297" alt="image" src="https://github.com/user-attachments/assets/a3a31725-44aa-42cb-98b0-9b18500943c7" />

### Output Table

| A | B | Y = A AND B |
|---|---|-------------|
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |



### Conclusion

An AND gate was constructed with three NOR gates.

---

## Experiment 4: AND Gate Using NAND Gates

### Objective

To implement an AND gate using only NAND gates.

### Theory

The first NAND gate gives:

$$
X = \overline{A \cdot B}
$$

The second NAND gate inverts `X`:

$$
Y = X \text{ NAND } X = A \cdot B
$$

### Circuit Steps

1. Connect `A` and `B` to the first NAND gate.
2. Connect its output to both inputs of the second NAND gate.
3. Take the second gate output as the AND result.

 

<img width="721" height="245" alt="image" src="https://github.com/user-attachments/assets/33450939-995c-4a78-bb9a-031e1b0b4ffa" />


### Output Table

| A | B | Y = A AND B |
|---|---|-------------|
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

### Conclusion

An AND gate was implemented using two NAND gates.

---

## Experiment 5: NOT Gate Using NOR Gates

### Objective

To implement a NOT gate using a NOR gate.

### Theory

When both NOR inputs receive the same signal:

$$
Y = A \downarrow A = \overline{A}
$$

### Circuit Steps

1. Connect input `A` to both NOR inputs.
2. Take the NOR output as `Y`.

<img width="399" height="174" alt="image" src="https://github.com/user-attachments/assets/46411db9-b319-49df-ba33-ecf4ece409a9" />


### Output Table

| A | Y = NOT A |
|---|-----------|
| 0 | 1 |
| 1 | 0 |

 

### Conclusion

A NOR gate works as a NOT gate when its two inputs are connected together.

---

## Experiment 6: NOT Gate Using NAND Gates

### Objective

To implement a NOT gate using a NAND gate.

### Theory

When both NAND inputs receive the same signal:

$$
Y = A \text{ NAND } A = \overline{A}
$$

### Circuit Steps

1. Connect input `A` to both NAND inputs.
2. Observe the output.

<img width="389" height="168" alt="image" src="https://github.com/user-attachments/assets/fdc3c6fc-6c4a-4056-b54e-7170ad9014fd" />

### Output Table

| A | Y = NOT A |
|---|-----------|
| 0 | 1 |
| 1 | 0 |

### Conclusion

A NAND gate can be used as a NOT gate.

---

## Experiment 7: Full Adder

### Objective

To design and test a one-bit full adder.

### Theory

A full adder is a combinational logic circuit that adds three binary inputs:

- `A` — first input bit
- `B` — second input bit
- `Cin` — carry input

The circuit produces two outputs:

- `Sum` — sum output
- `Cout` — carry output

**Logic Expressions**

```
Sum = (A ⊕ B) ⊕ Cin
Cout = (A · B) + [Cin · (A ⊕ B)]
```

### Circuit Steps

1. Connect inputs `A` and `B` to the first XOR gate to generate `A ⊕ B`.
2. Connect the output of the first XOR gate and `Cin` to the second XOR gate to obtain the **Sum** output.
3. Connect `A` and `B` to an AND gate to generate the first carry term.
4. Connect `(A ⊕ B)` and `Cin` to another AND gate to generate the second carry term.
5. Connect the outputs of both AND gates to an OR gate to obtain the **Carry (Cout)** output.
6. Apply all possible input combinations and verify the Sum and Carry outputs with the truth table.


### Truth Table

| A | B | Cin | Sum | Cout |
|---|---|-----|-----|------|
| 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 1 | 0 |
| 0 | 1 | 0 | 1 | 0 |
| 0 | 1 | 1 | 0 | 1 |
| 1 | 0 | 0 | 1 | 0 |
| 1 | 0 | 1 | 0 | 1 |
| 1 | 1 | 0 | 0 | 1 |
| 1 | 1 | 1 | 1 | 1 |

<img width="870" height="443" alt="image" src="https://github.com/user-attachments/assets/3e4a90ff-d651-47a6-9545-cb925640933a" />


### Conclusion

The full adder gave correct sum and carry outputs for all tested inputs.

---

## Experiment 8: Binary to BCD Converter

### Objective

To convert a four-bit binary number into Binary-Coded Decimal (BCD).

### Theory

BCD represents each decimal digit separately using four binary bits.

| Decimal Number | Binary Input | BCD Output |
|---:|:---:|:---:|
| 5 | `0101` | `0101` |
| 9 | `1001` | `1001` |
| 10 | `1010` | `0001 0000` |
| 15 | `1111` | `0001 0101` |

For values from `0` to `9`, one BCD digit is enough. Values from `10` to `15` need two BCD digits.

### Circuit Steps

1. Connect the four binary input lines to the converter circuit.
2. Connect the BCD outputs to the display or output indicators.
3. Change the binary input value and observe the decimal result.

 

<img width="774" height="516" alt="image" src="https://github.com/user-attachments/assets/78f336fd-ad16-4b66-a812-b46360ba0123" />


### Example Results

| Binary Input | Decimal Value | BCD Output |
|:---:|---:|:---:|
| `0000` | 0 | `0000` |
| `0011` | 3 | `0011` |
| `1001` | 9 | `1001` |
| `1010` | 10 | `0001 0000` |
| `1111` | 15 | `0001 0101` |


### Conclusion

The circuit converted binary values into BCD form. Such converters are commonly used with calculators and digital displays.

---


