# Technical Verification Skill

## Overview
This Hermes Agent skill provides an additional verification layer for mathematics, STEM, engineering, scientific analysis, simulations, and code-dependent technical work. It ensures proportionate — not exhaustive — technical correctness verification.

## Purpose
- Provide structured technical verification for calculations, models, and implementations
- Ensure dimensional consistency, unit tracking, and model validity
- Maintain explicit verification state using the Planning with Files system
- Track assumptions, evidence, contradictions, and completion conditions
- Optimize for accuracy, relevance, evidence quality, and efficiency (not merely maximum analysis)

## Core Features

### 1. Technical Verification Framework (18+ Sections)
- Proportionate verification depth (simple → complex)
- Sanity checks and uncertainty communication
- Conflict resolution between technical results
- Completion when required questions are answered sufficiently — not when every detail is examined

### 2. Calculation & Model Validation
- Step-by-step calculation protocol (10+ steps from governing relationship through sanity check)
- Equation/model selection with assumptions and limitations
- Units and dimensions tracking throughout (Section 4)
- Empirical correlation range validation

### 3. Technical Research & Literature
- Source quality preferences (original research → standards → docs)
- Methodology and equation verification
- Dataset and limitation awareness
- Citation trail analysis

### 4. Code & Implementation Verification
- Input/output checking
- Assumptions and units validation
- Data types and boundary conditions
- Version compatibility and API behavior

### 5. State Management (Section 19)
- **Technical Verification State** — Markdown table for tracking:
  - Governing model, inputs, assumptions, evidence
  - Status definitions (Open/Established/Verified/Assumed/Uncertain/Contradicted/Blocked/Not Needed)
  - Tracking required questions, remaining actions, completion conditions

## Quick Start

### When to Use This Skill
Your answer materially depends on technical correctness if it involves:
- Equations and mathematical models
- Numerical calculations or simulations
- Units, dimensions, and conversions
- Assumptions and boundary conditions
- Code-dependent technical work

### Basic Usage
```bash
# Import via Hermes Agent
# The skill provides 21+ sections for proportionate verification
```

### Verification Depth Selection
| Question Complexity | Required Verification |
|---|---|
| Simple formula query | Authoritative definition may suffice |
| Calculation required | Verify inputs, units, equation, and calculation |
| Complex engineering analysis | Substantially deeper verification of assumptions, conditions, models |

## Section Summary

### Sections 1-5: Foundation
1. Identify the Technical Problem
2. Verification vs. Validation  
3. Verify Inputs and Conditions
4. Units and Dimensions
5. Equations, Models, and Valid Regimes

### Sections 6-10: Analysis
6. Computational Execution
7. Mathematical Derivations and Proofs
8. Invariants and Conservation Laws
9. Engineering and Physical-System Analysis
10. Scientific and Experimental Claims

### Sections 11-15: Evidence & Uncertainty
11. Technical Literature and External Evidence
12. Code and Technical Implementation
13. Active Sanity, Boundary, and Limiting Checks
14. Conflicting Technical Results
15. Uncertainty, Sensitivity, and False Precision

### Sections 16-21: Escalation & Completion
16. Missing Information
17. Adversarial Failure Analysis
18. Proportionate Verification Depth [state table]
19. Technical Verification State [markdown table + 8 statuses]
20. Research and Verification Escalation
21. Final Technical Check

## Version History

- **3.0.0** — Initial release with full technical verification framework including Section 19 state management, Section 5 units-and-dimensions enhancement, and proportionate verification depth guidance

## License
MIT
