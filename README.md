# Multi-Class SVM Classifier — Support Vector Machines

## Overview
Designed and implemented a multi-class Support Vector Machine classifier using the **Binary Decision Tree** method. Given a 30-sample, 2D, 3-class dataset, the task was to identify support vectors, design optimal separating hyperplanes by hand, and verify classification correctness across all samples.

## Problem setup
- **Dataset:** 30 two-dimensional samples across 3 classes
- **Classes:** Class 1 (upper-middle), Class 2 (lower-left), Class 3 (lower-right)
- **Multi-class method:** Binary Decision Tree (R1 = 2)

## Classifier design

### SVM 1 — Class 1 vs {Class 2, Class 3}
Separating direction: x₂ axis only (Class 1 has consistently high x₂ values)

| Parameter | Value |
|-----------|-------|
| Weight vector w | [0, 1]ᵀ |
| Bias b | −8 |
| Decision boundary | x₂ = 8 |
| Margin width | 2 units |
| Support vectors (+1) | x6=[11,9], x8=[14,9] |
| Support vectors (−1) | x27=[17,7] |

**Decision function:** sign(x₂ − 8)  
**Verification:** All 30 points correctly classified ✅

### SVM 2 — Class 2 vs Class 3
Separating direction: x₁ axis only

| Parameter | Value |
|-----------|-------|
| Weight vector w | [−2/7, 0]ᵀ |
| Bias b | +3 |
| Decision boundary | x₁ = 10.5 |
| Margin width | 7 units |
| Support vectors (+1) | x20=[7,2] |
| Support vectors (−1) | x21=[14,1], x22=[14,3] |

**Decision function:** sign(−2/7 · x₁ + 3)  
**Verification:** All 20 points (Class 2 + Class 3) correctly classified ✅

## Test set classification
Applied the Binary Decision Tree to 10 test samples (averaged from training classes).  
- t1–t5: classified as **Class 2** (averaged x₁ < 10.5)
- t6–t10: classified as **Class 3** (averaged x₁ > 10.5)
- None classified as Class 1 — expected, since averaging reduces x₂ below the boundary of 8.

## Tech stack
`Python` `Matplotlib` `NumPy`

---
