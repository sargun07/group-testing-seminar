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

## Visual Overview

The following figures are adapted from the seminar presentation and illustrate
the main ideas behind modern non-adaptive group testing.

---

### Group Testing Intuition

<p align="center">
  <img src="figures/population_sparse.heic" width="45%"/>
  &nbsp;&nbsp;&nbsp;
  <img src="figures/positive_negative_pool.heic" width="45%"/>
</p>

The intuition behind group testing is that, in large populations,
only a very small fraction of individuals are infected.

Instead of testing everyone individually, samples are pooled together:

- **Negative test** → everyone in the pool is healthy
- **Positive test** → at least one individual in the pool is infected

When infections are rare, a single pooled test can provide information
about many individuals simultaneously.

---

### Information-Theoretic & Algorithmic Thresholds

<p align="center">
  <img src="figures/algorithmic_gap.heic" width="700"/>
</p>

Comparison of recovery thresholds under:
- Bernoulli designs
- Near-constant column weight designs
- Counting bounds

The plot highlights the phase transition behavior as sparsity changes.

---

### Spatially Coupled Designs

<p align="center">
  <img src="figures/spatial_coupling.heic" width="700"/>
</p>

Spatially coupled constructions modify the geometry of the test design,
allowing information to propagate progressively and improving algorithmic recovery.

---

## Academic Context

This seminar project was developed as part of the seminar:

**“Randomized Algorithms for Distributed Systems”**  
at Hamburg University of Technology (TUHH)  
during Winter Semester 2025/26.

---

## Seminar Report

📄 **Report:**  
[Seminar Report](report/SargunpreetKaur_GroupTesting_Seminar.pdf)

📊 **Presentation Slides:**  
[Presentation Slides](slides/Seminar_GroupTesting_Presentation.pdf)

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

## References

The seminar is primarily based on modern results from:

- [Group Testing: An Information Theory Perspective](https://www.nowpublishers.com/article/Details/CIT-111) — Matthew Aldridge, Oliver Johnson, and Jonathan Scarlett

- [Information-Theoretic and Algorithmic Thresholds for Group Testing](https://ieeexplore.ieee.org/document/9186805) — Amin Coja-Oghlan, Oliver Gebhard, Max Hahn-Klimroth, and Philipp Loick

- [Phase Transitions in Group Testing](https://epubs.siam.org/doi/10.1137/1.9781611974331.ch3) — Jonathan Scarlett and Volkan Cevher

- [Elements of Information Theory](https://onlinelibrary.wiley.com/doi/book/10.1002/047174882X) — Thomas M. Cover and Joy A. Thomas

---

## Author

**Sargunpreet Kaur**  
M.Sc. Data Science  
Hamburg University of Technology (TUHH)

## License

This project is licensed under the
[CC BY 4.0 License](https://creativecommons.org/licenses/by/4.0/).
