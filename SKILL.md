---
name: technical-verification
description: "Technical Verification - Proportionate verification of mathematics, STEM, engineering, scientific analysis, numerical computation, simulations, models, and code-dependent technical work."
version: 3.0.0
author: tkatsampanis
platforms: [linux, macos, windows]
metadata:
  hermes:
    tags: [technical, verification, stem, mathematics, science, engineering, numerical, simulation, modeling, code]
---

# Technical Verification

## Purpose

Provide an additional verification layer for mathematics, STEM, engineering, scientific analysis, numerical computation, simulations, technical calculations, mathematical models, and code-dependent technical work.

This skill is used when the user's answer materially depends on technical correctness.

Correctness may depend on:

- mathematical assumptions
- equations
- numerical values
- units and dimensions
- boundary or initial conditions
- physical laws
- model assumptions
- applicability regimes
- experimental conditions
- numerical methods
- algorithms
- implementation details
- uncertainty
- or externally sourced technical data

It complements the general research skill.

Do not perform unnecessary technical analysis.

The goal is:

> **Verify the technical elements that could materially make the answer wrong.**

When a technical task involves multiple calculations, sources, assumptions, simulations, or verification stages, use the Planning with Files system to maintain the technical verification state.

---

## 1. Identify the Technical Problem

Before calculating, deriving, simulating, implementing, or evaluating a technical claim, determine:

1. What exactly must be established?
2. What quantities, variables, parameters, or conditions are known?
3. What quantities or conclusions are unknown?
4. What equations, laws, models, algorithms, or standards may apply?
5. What assumptions are being made?
6. What information is missing?
7. What conditions define the validity of the result?
8. What would constitute sufficient evidence for the requested conclusion?

Do not begin substantial technical work before the problem is sufficiently defined.

For non-trivial tasks, convert the important unknowns and verification obligations into explicit questions in the technical verification state.

Examples:

- What quantity must be calculated?
- Which governing model applies?
- Which inputs require verification?
- Which assumptions require validation?
- What conditions limit applicability?
- What could invalidate the conclusion?
- What independent check should be performed?

Do not create questions that are irrelevant to the user's actual problem.

---

## 2. Verification vs. Validation

Distinguish between **verification** and **validation**.

### Verification

Verification asks:

> Did we derive, calculate, implement, or evaluate the stated method correctly?

Examples include:

- checking algebra
- checking numerical calculations
- checking code implementation
- checking units
- checking numerical convergence
- checking that an algorithm implements the stated equations

### Validation

Validation asks:

> Is the selected model, equation, correlation, simulation, or approximation appropriate for representing the real phenomenon under the stated conditions?

Examples include:

- checking model assumptions
- checking empirical correlation ranges
- checking physical regimes
- checking whether a constitutive law applies
- checking whether experimental conditions match the intended application

A result can be successfully verified while the underlying model is physically inappropriate.

For example, a numerical solver can correctly solve the wrong equations.

When real-world accuracy matters, verify both:

1. whether the method was executed correctly, and
2. whether the method is appropriate for the problem.

Do not treat successful code execution, numerical convergence, or algebraic correctness as proof of physical validity.

---

## 3. Verify Inputs and Conditions

For important numerical or technical inputs, check as appropriate:

- units
- dimensions
- definitions
- magnitude
- reference conditions
- temperature
- pressure
- composition
- material properties
- geometry
- operating conditions
- initial conditions
- boundary conditions
- coordinate conventions
- sign conventions
- applicable ranges
- source
- date
- software or library version
- measurement conditions

Determine whether the conditions attached to an input actually match the user's problem.

Distinguish clearly between:

- user-provided values
- measured values
- externally sourced values
- calculated values
- empirical correlations
- inferred values
- assumptions

Do not blindly trust a numerical value merely because it appears in a source.

Do not silently substitute a convenient default for missing technical information.

If a missing value materially affects the conclusion:

- ask the user,
- provide a conditional result,
- or use a clearly stated assumption when reasonable.

Record important externally sourced inputs and their conditions in the verification state when the task is substantial.

---

## 4. Units and Dimensions

Track units throughout calculations and derivations.

Check dimensional consistency before finalizing an expression or result.

Convert units explicitly when necessary.

Do not silently mix:

- SI and non-SI units
- absolute and gauge pressure
- mass and molar quantities
- Celsius and Kelvin
- different time bases
- different concentration definitions
- different reference states
- incompatible coordinate or sign conventions

Dimensional consistency is necessary but not sufficient for correctness.

An incorrect equation can still be dimensionally consistent.

Treat unresolved dimensional inconsistency as a verification failure.

---

## 5. Equations, Models, and Valid Regimes

Do not blindly copy equations, formulas, correlations, or model structures.

Before using an equation or model, establish as appropriate:

- what each variable means
- assumptions behind the equation
- applicable regime
- boundary conditions
- initial conditions
- reference state
- required inputs
- validity range
- limitations
- expected approximation error

Use the simplest valid model that answers the user's question.

Do not introduce unnecessary model complexity merely because a more sophisticated method exists.

If multiple plausible models produce materially different results:

1. identify why they differ,
2. determine which assumptions apply,
3. determine whether the user's conditions fall within each model's valid regime,
4. explain the material difference.

For empirical correlations, verify that the user's conditions fall within the correlation's validated or accepted range.

Do not extrapolate a correlation silently.

If extrapolation is unavoidable, label it explicitly and communicate the resulting uncertainty.

---

## 6. Computational Execution

When an executable computation environment is available, prefer it for non-trivial numerical work rather than performing extended arithmetic entirely inside generated text.

Use executable computation when appropriate for:

- multi-step numerical calculations
- unit conversions involving multiple operations
- matrix and vector operations
- numerical root-finding
- numerical integration
- numerical differentiation
- iterative equations
- simulations
- parameter sweeps
- sensitivity analysis
- uncertainty propagation
- complex symbolic algebra
- large or repetitive calculations

Use appropriate tools such as Python, NumPy, SciPy, SymPy, or equivalent computational environments when available.

For symbolic derivations, use symbolic computation when it materially reduces algebraic or transcription errors.

For numerical simulations, verify:

- equations
- parameters
- units
- initial conditions
- boundary conditions
- numerical method
- tolerances
- convergence criteria
- interpretation of outputs

Do not treat successful code execution as proof that the formulation is correct.

Verify the model, equations, parameters, assumptions, and interpretation independently.

For simple arithmetic or trivial calculations, direct calculation is sufficient. Do not invoke computation unnecessarily.

**Every computational run should answer a defined technical question or verify a specific result.**

Do not run code merely to generate more output.

---

## 7. Mathematical Derivations and Proofs

For mathematical derivations or proofs:

- define variables
- define domains
- state assumptions
- state required conditions
- preserve boundary and initial conditions
- verify intermediate transformations
- check algebra
- check dimensions where applicable
- verify the final expression against the starting equations

For proofs, verify the logical validity of each critical inference.

Do not skip important reasoning when the user explicitly asks for a derivation or proof.

Do not present an unverified copied derivation as independently established.

For non-trivial derivations, track major proof or derivation obligations individually rather than checking only the final expression.

Pay particular attention to:

- division by quantities that could be zero
- square roots
- logarithms
- inverse functions
- changes of variables
- discontinuities
- singularities
- convergence assumptions
- interchange of limits, sums, derivatives, and integrals
- hidden domain restrictions

A formally correct manipulation can become invalid if its mathematical conditions are ignored.

---

## 8. Invariants and Conservation Laws

Where applicable, verify fundamental invariants and conservation relationships.

Examples include:

- mass or species balance
- energy balance
- momentum balance
- charge conservation
- stoichiometric balance
- elemental balance
- symmetry constraints
- normalization constraints
- probability conservation
- dimensional and sign constraints
- known mathematical invariants

A general balance may be expressed as:

> **Accumulation = In − Out + Generation − Consumption**

Use the conservation or invariant appropriate to the system.

Do not force a conservation check onto a problem where it is irrelevant.

If an applicable invariant is violated beyond numerical tolerance or the stated model approximation:

1. stop,
2. investigate the cause,
3. determine whether the violation is numerical, modeling-related, or conceptual,
4. do not present the result as fully verified until the issue is resolved or explicitly characterized.

An invariant check is an independent consistency test, not proof that the entire model is correct.

---

## 9. Engineering and Physical-System Analysis

For engineering or physical-system calculations, consider relevant:

- conservation laws
- constitutive relations
- material properties
- geometry
- operating conditions
- initial conditions
- boundary conditions
- empirical correlations
- applicable regimes
- design constraints
- stability conditions
- safety constraints
- numerical limitations

Explicitly distinguish between:

- design inputs
- measured values
- sourced properties
- empirical correlations
- model assumptions
- inferred quantities

Check whether empirical relationships are being used within their validated range.

If a parameter depends strongly on temperature, pressure, composition, frequency, operating point, or another condition, account for that dependence when it materially affects the result.

Do not assume that a physically familiar approximation remains valid outside its intended regime.

---

## 10. Scientific and Experimental Claims

For scientific claims, distinguish between:

- measured result
- calculated result
- model prediction
- simulation result
- empirical correlation
- assumption
- interpretation
- hypothesis

Check, where relevant:

- experimental conditions
- sample or population
- measurement method
- uncertainty
- controls
- calibration
- reproducibility
- statistical limitations
- relevant confounders
- applicability to the user's case

Do not present a model prediction as an experimentally established fact.

Do not present a simulation result as direct measurement.

Do not generalize beyond the population, conditions, or evidence supported by the source.

If a claim depends on a paper or dataset, identify the exact evidence needed rather than treating the existence of the paper or dataset as verification.

---

## 11. Technical Literature and External Evidence

When using technical papers, standards, documentation, datasets, or other technical sources, prefer:

1. original research
2. official standards
3. authoritative technical documentation
4. institutional sources
5. reputable secondary analysis

Use abstracts and metadata to establish relevance when sufficient.

Retrieve deeper material when the answer depends on:

- methodology
- equations
- experimental setup
- implementation
- datasets
- numerical results
- limitations
- uncertainty
- validation conditions

Do not read or download every paper merely because it appears in search results.

For each important technical claim, determine whether the source provides:

- direct evidence
- supporting context
- a citation trail
- an assertion without sufficient supporting detail

Do not treat multiple secondary sources as independent corroboration when they reproduce the same underlying evidence.

If several sources rely on the same original paper, dataset, benchmark, standard, press release, or underlying measurement, treat the underlying evidence as one evidentiary basis rather than counting the secondary sources independently.

---

## 12. Code and Technical Implementation

When technical correctness depends on code, inspect:

- inputs
- outputs
- assumptions
- units
- data types
- numerical precision
- boundary conditions
- algorithmic behavior
- state management
- error handling
- numerical stability
- convergence
- version compatibility
- API behavior
- dependency behavior

Do not assume code is correct merely because it executes.

Do not assume a test passing proves the implementation is generally correct.

When debugging or validating code:

1. state the specific hypothesis being tested,
2. design the smallest useful test,
3. execute it,
4. inspect the result,
5. determine what the result establishes,
6. identify what remains untested.

Do not run tests merely to generate more output.

Each additional test should answer a defined technical question.

If implementation depends on a library, API, framework, compiler, runtime, or software version, verify the relevant documentation when freshness or version differences matter.

---

## 13. Active Sanity, Boundary, and Limiting Checks

After obtaining a technical result, perform an appropriate active sanity check.

Do not merely state that the result “looks plausible.”

Check as appropriate:

- magnitude
- units
- signs and directions
- known constraints
- limiting cases
- boundary conditions
- asymptotic behavior
- order of magnitude
- known analytical solutions
- conservation relationships
- expected qualitative behavior

When meaningful, actively evaluate at least one relevant boundary condition, limiting case, or independent consistency condition.

Examples include:

- zero input
- zero forcing
- a variable approaching zero
- a variable becoming large
- steady-state behavior as time increases
- symmetry conditions
- known equilibrium states
- known analytical solutions

Perform an order-of-magnitude or Fermi-style check when it can expose scale errors.

If a test appears to fail, determine whether:

1. the result is incorrect,
2. the model has left its domain of validity,
3. the approximation is expected to break down,
4. the numerical method is inadequate,
5. or the tested limit is not physically or mathematically meaningful.

Do not automatically reject a result merely because a test approaches a condition outside the model's stated domain.

A sanity check is not proof, but a failed sanity check is a reason to investigate.

---

## 14. Conflicting Technical Results

If reliable sources, calculations, simulations, or implementations disagree:

Do not average them automatically.

Determine whether the difference comes from:

- different definitions
- different models
- different assumptions
- different temperatures
- different pressures
- different datasets
- different software versions
- different numerical methods
- different measurement methods
- different boundary conditions
- different initial conditions
- different applicability ranges
- different reference states

Determine which conditions apply to the user's problem.

If the conflict can be resolved, resolve it using the relevant evidence.

If it cannot be resolved, report the uncertainty explicitly.

Record material technical conflicts in the verification state and identify what evidence would resolve them, if resolution is possible.

---

## 15. Uncertainty, Sensitivity, and False Precision

Communicate meaningful uncertainty.

Potential sources include:

- measurement uncertainty
- uncertain inputs
- model limitations
- empirical correlations
- numerical approximation
- insufficient data
- conflicting literature
- unknown operating conditions
- parameter uncertainty
- implementation uncertainty

Distinguish between:

- numerical precision
- input uncertainty
- model uncertainty
- scientific confidence

A result may be numerically precise while scientifically uncertain.

Do not report excessive digits from uncertain inputs or empirical models.

For example, do not present six decimal places from an empirical correlation with a large uncertainty band unless there is a specific reason to retain that precision internally.

### Sensitivity and dependency analysis

When uncertainty in an input could materially affect the conclusion:

- identify the most influential inputs
- determine whether reasonable changes in important inputs materially change the result
- use analytical sensitivity, local perturbation, parameter sweeps, or executable computation when appropriate
- identify assumptions that dominate the result
- distinguish changes in numerical value from changes in the qualitative conclusion or model regime

Do not perform exhaustive sensitivity analysis when the result is demonstrably insensitive to the relevant inputs.

If a conclusion is highly sensitive to an uncertain parameter or assumption, state that explicitly.

---

## 16. Missing Information

If a technically important input is missing:

Do not invent it.

Choose among:

- ask the user,
- make a clearly stated reasonable assumption,
- provide a conditional result,
- or explain why the result cannot currently be established.

Before asking the user, determine whether the missing information materially changes the requested answer.

Do not interrupt the user for information that is irrelevant to the result.

When using an assumption:

- identify it clearly,
- explain why it is reasonable when necessary,
- indicate whether changing it could alter the conclusion.

Clearly distinguish assumptions from supplied facts.

---

## 17. Adversarial Failure Analysis

For consequential or non-trivial technical results, actively consider how the conclusion could be wrong.

Ask:

- What assumption is most likely to fail?
- Which input is most uncertain?
- Which parameter is the result most sensitive to?
- Which boundary condition could invalidate the model?
- Could a sign or convention error produce a plausible-looking result?
- Could a unit or reference-state error produce a plausible-looking result?
- Could numerical convergence hide an incorrect formulation?
- What simple test could falsify the conclusion?
- What alternative model would materially change the result?
- What evidence would make the conclusion invalid?

Use the smallest useful adversarial test.

Do not manufacture hypothetical failure modes that have no relevance to the problem.

The purpose is to expose plausible technical failure, not to create endless doubt.

---

## 18. Proportionate Verification Depth

Use verification proportional to:

- the consequences of being wrong,
- the complexity of the technical claim,
- the uncertainty of the inputs,
- the number of interacting assumptions,
- the user's requested depth,
- and whether the result affects a real-world decision.

### Simple question

Example:

> “What is the formula for Reynolds number?”

A standard authoritative definition may be sufficient.

### Direct calculation

Example:

> “Calculate Reynolds number for this pipe.”

Verify:

- required inputs
- units
- governing equation
- calculation
- magnitude
- applicable regime

### Complex technical analysis

Example:

> “Determine whether this process design is valid.”

Perform substantially deeper verification of:

- assumptions
- operating conditions
- governing models
- applicable regimes
- constraints
- calculations
- implementation
- uncertainty
- relevant technical evidence

Do not perform a full technical audit when the question does not require one.

Do not perform additional analysis merely because more analysis is possible.

---

## 19. Technical Verification State

For substantial technical tasks, maintain explicit verification state using the Planning with Files system.

Track the actual questions and claims that must be resolved.

Use a compact state table such as:

| Question / Claim | Status | Evidence / Calculation | Assumptions | Next Action |
| :--- | :--- | :--- | :--- | :--- |
| Governing model | Established | Regime analysis / source | Stated operating range | None |
| Input property | Open | Missing property value | Reference temperature known | Verify source |
| Boundary condition | Assumed | Stated physical assumption | Rigid boundary | Validate |
| Numerical result | Open | Pending calculation | Inputs verified | Execute calculation |

Useful statuses include:

- **Open** — required claim remains unresolved
- **Established** — strong evidence directly supports the claim
- **Verified** — confirmed through an independent check, calculation, test, or other appropriate verification
- **Assumed** — temporarily assumed rather than established
- **Uncertain** — meaningful uncertainty remains despite available evidence
- **Contradicted** — credible evidence conflicts with the claim
- **Blocked** — required information cannot currently be established
- **Not Needed** — the question does not apply to the current task

For substantial tasks, track at least:

- required technical questions
- important inputs
- assumptions
- governing models
- evidence
- calculations
- simulations when relevant
- contradictions
- uncertainties
- validation requirements
- remaining actions
- completion conditions

After each meaningful calculation, retrieval, simulation, test, or validation step:

1. update the relevant state,
2. record newly established evidence,
3. record changed assumptions,
4. record contradictions,
5. record important uncertainties,
6. identify remaining required questions,
7. determine whether another action is actually necessary.

Do not continue technical analysis once all required verification questions have been sufficiently resolved.

The planning state is working state, not a substitute for the final answer.

---

## 20. Research and Verification Escalation

When technical verification cannot be completed because evidence is missing, identify exactly what is missing before escalating.

Use the lightest reliable method first:

1. existing conversation context
2. user-provided material
3. known authoritative documentation
4. focused source retrieval
5. targeted technical literature
6. executable calculation or targeted analysis
7. deeper technical analysis
8. independent reconciliation when necessary

Escalate only when the current evidence is insufficient for the required conclusion.

Do not escalate merely because a deeper source or more sophisticated method exists.

Every additional retrieval, calculation, simulation, or test should have a defined purpose.

---

## 21. Final Technical Check

Before reporting the final result, verify:

1. Did I correctly define the technical problem?
2. Did I identify the relevant governing equations, laws, or models?
3. Are the inputs appropriate?
4. Are units and reference states consistent?
5. Are assumptions explicit?
6. Is the selected model valid for the stated conditions?
7. Was the calculation, derivation, simulation, or implementation performed correctly?
8. Did I use computational tools where they materially reduce numerical or algebraic error?
9. Did relevant conservation laws or invariants hold?
10. Did the result pass an appropriate sanity, boundary, or limiting-case check?
11. Is the result within the model's applicable range?
12. Did I distinguish facts, assumptions, calculations, simulations, predictions, and interpretations?
13. Did I avoid unsupported precision?
14. Could uncertainty or sensitivity materially change the conclusion?
15. Were important contradictions resolved or clearly reported?
16. Are remaining uncertainties explicitly stated?
17. Did every additional retrieval, calculation, test, or simulation have a defined purpose?
18. Are all required technical verification questions sufficiently resolved?
19. Has the verification state reached its completion conditions?
20. Is additional technical work actually necessary?

If these checks are satisfied, stop.

Do not perform additional technical work merely because more analysis is possible.

---

## Core Rule

> **Technical rigor means verifying the things that can make the answer wrong.**

Do not add complexity for its own sake.

Use the minimum technical analysis necessary to establish a reliable result.

> **DEFINE → PLAN → CHECK INPUTS → CHECK UNITS → SELECT MODEL → COMPUTE/ANALYZE → CHECK INVARIANTS → TEST LIMITS → CHALLENGE THE RESULT → VERIFY → REPORT**

For substantial technical work:

> **Do not merely collect calculations, sources, or simulation outputs. Maintain explicit questions, evidence, assumptions, model validity, contradictions, uncertainty, and completion conditions.**

A technical investigation is complete when:

- the required technical questions are sufficiently answered,
- the selected methods are appropriate,
- important calculations or implementations are verified,
- applicable invariants and consistency checks pass,
- material uncertainties are communicated,
- important contradictions are resolved or reported,
- and no essential evidence gap remains.

> **Completion does not mean every potentially interesting technical detail has been examined.**
