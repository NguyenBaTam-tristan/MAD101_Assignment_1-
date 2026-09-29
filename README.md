# Discrete Math in Python: Sets, Primes, and Logic

Python solutions to **Assignment 1 of the MAD101 course**. The assignment covers set operations, prime numbers, and propositional logic, each solved with short, readable Python code.

**Authors:** Nguyễn Bá Tâm, Trần Ngọc Tùng, Lưu Đình Huy

## Table of Contents

- [Repository Contents](#repository-contents)
- [Question 1: Sets and Prime Numbers](#question-1-sets-and-prime-numbers)
- [Question 3: Logical Equivalence](#question-3-logical-equivalence)
- [Getting Started](#getting-started)
- [Notes](#notes)

## Repository Contents

```
├── .gitignore
├── MAD101_Assignment_1_Question_1   # Sets and prime numbers
├── MAD101_Assignment_1_Question_3   # Truth tables and logical equivalence
└── README.md
```

## Question 1: Sets and Prime Numbers

**Definitions**

- **A** is the set of natural numbers `n` such that `n² + 2n` is divisible by 15.
- **B** is the set of all integers from 0 to 10,000.
- **C** is the set of numbers `n = p × q`, where `p` and `q` are two *distinct* primes.

### 1.1 Find |B \ A|

Count how many numbers in B are not in A.

1. Build A by looping from 0 to 10,000 and keeping every `n` where `(n*n + 2*n) % 15 == 0`.
2. Define B as `range(0, 10001)`.
3. Compute the set difference B \ A by keeping the numbers in B that are not in A.
4. Count the elements.

### 1.2 Find the 100th element of A ∩ B in descending order

1. Since A is built from numbers in B, A ∩ B is simply A.
2. Sort A in descending order with `sorted(..., reverse=True)`.
3. Take the 100th element, which is index `99` in Python.

### 1.3 Build C and find its 100th element

1. Write an `is_prime(x)` function.
2. Generate all primes below 5,000. This is enough because `p × q ≤ 10,000`, so both primes are at most 5,000.
3. For each `n` from 6 to 10,000, check whether it can be written as `p × q` with `p ≠ q`, both prime.
4. Collect the results into the list C.
5. Take the 100th element in ascending order.

### 1.4 Find |B ∩ C|

Since every element of C is at most 10,000, keep the elements of C that are also in B and count them.

## Question 3: Logical Equivalence

**Goal:** Check when the two propositions `(p ∨ q) → r` and `(p ⊕ r) ∧ q` have the same truth value, where `⊕` is XOR.

**Step 1: Simplify the implication.**
`(p ∨ q) → r` is equivalent to `¬(p ∨ q) ∨ r`.

**Step 2: Translate to Python.**

```python
not (p or q) or r      # (p ∨ q) → r
(p ^ r) and q          # (p ⊕ r) ∧ q
```

**Step 3: Build the truth table in code.**
Loop over all 8 combinations of `p`, `q`, and `r` (`True` and `False`), evaluate both expressions, and print the cases where they match.

**Why it matters:** Looping over every combination is a fast, reliable way to test whether two propositions are logically equivalent, without building the truth table by hand.

## Getting Started

### Prerequisites

- Python 3.x

### Run the solutions

```bash
git clone https://github.com/NguyenBaTam-tristan/MAD101_Assignment_1-.git
cd MAD101_Assignment_1-
```

The solution files have no `.py` extension, so run them by passing the file name to Python:

```bash
python MAD101_Assignment_1_Question_1
python MAD101_Assignment_1_Question_3
```

## Notes

- There is no Question 2 in this repository.
- The original write-up was in Vietnamese and included screenshots of the code and its output. This README summarizes the approach for each question in English.
