# Group Testing: Finding a Few Infected Among Many

> *Can we identify a small number of infected individuals in a massive population using far fewer tests than testing everyone individually?*

Group testing is a fascinating intersection of information theory, randomized algorithms, and combinatorial optimization.

Instead of testing individuals one by one, group testing pools multiple samples together in a single test:

- **Negative test** → everyone in the pool is healthy  
- **Positive test** → at least one individual in the pool is infected  

When infections are rare, a single test can provide information about many individuals at once.

This repository contains my seminar project exploring the modern theory of **non-adaptive group testing**, including:

- Information-theoretic recovery limits
- Bernoulli vs balanced test designs
- Algorithmic recovery thresholds
- The *algorithmic gap*
- Spatially coupled designs
- Sparse recovery and threshold phenomena

---

## Why This Problem Matters

Group testing appears in many real-world applications:

- COVID pooled testing
- DNA sequencing
- Network fault detection
- Large-scale screening systems
- Sparse signal recovery
- Distributed systems and data processing

The central challenge is:

> **How can we design tests so that a small hidden signal can still be recovered efficiently?**

---

## The Basic Idea

Instead of:

```text
1 person  -> 1 test
```

we test **groups**:

```text
10 people -> 1 pooled test
```

If the pooled test is negative, all 10 people are immediately cleared.

This creates a powerful tradeoff between:
- number of tests
- sparsity of infections
- recovery guarantees
- computational complexity

---

## Key Concepts Covered

### Non-Adaptive Group Testing

All tests are designed in advance and executed in parallel.

This is especially useful for:
- large-scale systems
- high-throughput testing
- distributed environments
- time-sensitive applications

---

### Information-Theoretic Thresholds

The report studies the minimum number of tests theoretically required for exact recovery under sparse scaling:

```math
k = \Theta(n^\theta)
```

and analyzes:
- counting bounds
- recovery thresholds
- capacity limits
- entropy-based interpretations

---

### Bernoulli vs Balanced Designs

Two major random test constructions are compared:

#### Bernoulli Design
- fully random participation
- simple and analyzable
- suffers from imbalance

#### Near-Constant Column Weight Design
- more balanced participation
- improved isolation properties
- better recovery thresholds

One of the central observations is that **structured balance improves recoverability**.

---

### The Algorithmic Gap

A major theme of the project is the distinction between:

- what is theoretically recoverable
- what efficient algorithms can actually recover

In some regimes:

- enough information exists globally,
- but efficient polynomial-time algorithms still fail.

This separation is known as the **algorithmic gap**.

---

### Spatially Coupled Designs

Recent structured constructions show that the algorithmic gap is not necessarily intrinsic.

By changing the geometry of the test design:
- information propagates progressively,
- local ambiguity disappears,
- and efficient algorithms approach information-theoretic limits.

A particularly elegant insight from the seminar:

> *Sometimes the bottleneck is not the algorithm — it is the structure of the data itself.*

---

## Results & Key Insights

### Information-Theoretic Thresholds

The project compares the recovery thresholds of:

- Bernoulli test designs
- Near-constant column weight (balanced) designs

One key result is that balanced designs remain information-theoretically optimal over a larger sparsity regime than Bernoulli designs.

---

### Algorithmic Thresholds

Efficient algorithms such as:

- COMP
- DD (Definite Defectives)
- SCOMP

are analyzed and compared against information-theoretic limits.

The report shows that:
- information-theoretic recovery may already be possible,
- while polynomial-time algorithms still fail.

This creates the algorithmic gap.

---

### Structural Resolution of the Gap

The seminar also explores **spatially coupled test designs**, where:

- local recovery propagates globally,
- ambiguity disappears progressively,
- and efficient algorithms approach optimal recovery thresholds.

---

## Repository Structure

```text
group-testing-seminar/
│
├── README.md
├── report/
│   └── SargunpreetKaur_GroupTesting_Seminar.pdf
│
├── slides/
│   └── Seminar_GroupTesting_Presentation.pdf
│
├── figures/
│   └── images_used_in_readme
│
└── references/
```

---

## Suggested Visuals

You can add screenshots from the presentation here.

### Group Testing Intuition

- pooled testing example
- healthy vs infected pools
- sparse population visualization

### Threshold Phenomena

- information-theoretic threshold plot
- algorithmic threshold plot
- algorithmic gap visualization

### Spatial Coupling

- coupled pool structure
- progressive recovery diagram

---

## Academic Context

This seminar project was developed as part of the seminar:

**“Randomized Algorithms for Distributed Systems”**  
at Hamburg University of Technology (TUHH)  
during Winter Semester 2025/26.

---

## Seminar Report

📄 **Report:**  
`report/SargunpreetKaur_GroupTesting_Seminar.pdf`

📊 **Presentation Slides:**  
`slides/Seminar_GroupTesting_Presentation.pdf`

---

## Topics & Keywords

- Group Testing
- Sparse Recovery
- Information Theory
- Randomized Algorithms
- Non-Adaptive Algorithms
- Threshold Phenomena
- Computational Complexity
- Spatial Coupling
- Distributed Systems

---

## References

The seminar is primarily based on modern results from:

- Matthew Aldridge et al. — *Group Testing: An Information Theory Perspective*
- Coja-Oghlan et al. — *Information-Theoretic and Algorithmic Thresholds for Group Testing*
- Scarlett & Cevher — *Phase Transitions in Group Testing*
- Cover & Thomas — *Elements of Information Theory*

---

## Author

**Sargunpreet Kaur**  
M.Sc. Data Science  
Hamburg University of Technology (TUHH)
