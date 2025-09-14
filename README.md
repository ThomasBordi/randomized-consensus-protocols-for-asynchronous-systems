# Randomized Consensus Protocols for Asynchronous Systems

**Author:** Thomas Bordino  
**Institution:** Columbia University

## Abstract

This paper introduces EABA (Efficient Asynchronous Byzantine Agreement), a committee-based protocol achieving optimal Byzantine resilience (t < n/3) with sub-quadratic message complexity O(n log n) under standard cryptographic assumptions.

## Key Innovation

**Committee-Based Architecture:** First protocol to break the fundamental trade-off between optimal resilience and communication efficiency in asynchronous Byzantine consensus.

### What's New

1. **VRF Committee Selection:** Verifiable Random Functions create unpredictable committee assignments preventing adversarial manipulation

2. **Hierarchical Consensus:** Local Byzantine agreement in O(log n)-sized committees + global threshold signature aggregation reduces communication from O(n²) to O(n log n)

3. **Theoretical Breakthrough:** Proves fundamental time-communication trade-off - any O(1) time protocol requires Ω(n log n) messages

### Algorithm

1. VRF-based assignment to m = O(n/log n) committees
2. Each committee runs local Byzantine agreement
3. Committees generate threshold signatures
4. Global decision with ≥⌈m/2⌉ + tc committee approvals


## Comparison

**Previous Work:**
- HMVBA: Limited to t < n/5 resilience
- Reducer: t < n/4, O(n²) messages
- FIN-MVBA: Optimal resilience but O(n³) cubic complexity

**EABA:**
- Optimal t < n/3 resilience
- Sub-quadratic O(n log n) messages  
- Standard crypto assumptions
- O(1) expected time

## Results

**Complexity:** O(n log n) messages, O(1) time, O(n log n·λ + n·ℓ) bits

**Lower Bounds:** Proves no protocol can exceed t < n/3 resilience and constant-time requires Ω(n log n) messages

**Applications:** Enables 1000+ validator blockchains, quantum-resistant DeFi, smart grid coordination

## Impact

First asynchronous Byzantine consensus achieving optimal resilience with sub-quadratic complexity under standard assumptions. Establishes new foundations for scalable fault-tolerant systems.
