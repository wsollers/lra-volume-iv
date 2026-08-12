# Learning Note 002: Metric Basic Consequences Proof Drill

Status: handwritten proof drill for M3.

Target:

- TeX label: `thm:metric-basic-consequences`
- Lean declaration: `MetricDefinition.MetricBasicConsequences`
- Proof file: `proofs/metrics/prf-metric-basic-consequences.tex`

The TeX proof file intentionally remains a TODO stub until the handwritten proof
gate is owned.

## Statement

Let \((X,d)\) be a metric space.  For all \(x,y,z\in X\),
\[
\begin{gathered}
  d(x,x)=0, \qquad d(x,y)\geq 0, \qquad
  d(x,y)=0 \Longleftrightarrow x=y,\\
  d(x,y)=d(y,x), \qquad
  d(x,z)\leq d(x,y)+d(y,z).
\end{gathered}
\]

## What Is Being Proved

This is mostly an unpacking theorem.  It turns the metric-space definition into
facts that can be cited one line at a time.

Four clauses are direct from the metric axioms:

- nonnegativity: \(d(x,y)\geq 0\);
- zero-distance characterization: \(d(x,y)=0\Longleftrightarrow x=y\);
- symmetry: \(d(x,y)=d(y,x)\);
- triangle inequality: \(d(x,z)\leq d(x,y)+d(y,z)\).

The only derived clause is:

\[
  d(x,x)=0.
\]

That follows by applying the zero-distance characterization to the pair
\((x,x)\).  Since \(x=x\) is true, the reverse direction of
\[
  d(x,x)=0 \Longleftrightarrow x=x
\]
gives \(d(x,x)=0\).

## Handwritten Proof Skeleton

1. Let \(x,y,z\in X\) be arbitrary.
2. Since \(d\) is a metric, quote the metric axioms.
3. From positive definiteness, record:
   \[
     d(x,y)\geq 0
     \quad\text{and}\quad
     d(x,y)=0\Longleftrightarrow x=y.
   \]
4. Apply the zero-distance characterization with \(y=x\):
   \[
     d(x,x)=0\Longleftrightarrow x=x.
   \]
   Since \(x=x\), conclude \(d(x,x)=0\).
5. From symmetry, record:
   \[
     d(x,y)=d(y,x).
   \]
6. From the triangle inequality, record:
   \[
     d(x,z)\leq d(x,y)+d(y,z).
   \]
7. Combine the five collected facts.

## Lean Reading

The Lean proof is the same structure as the handwritten proof, compressed into
record projections:

```lean
theorem MetricBasicConsequences {X : Type u} (metric : MetricDefinition X) :
    (∀ x : X, metric.distance x x = 0) ∧
      (∀ x y : X, 0 ≤ metric.distance x y) ∧
      (∀ x y : X, metric.distance x y = 0 ↔ x = y) ∧
      (∀ x y : X, metric.distance x y = metric.distance y x) ∧
      (∀ x y z : X, metric.distance x z ≤ metric.distance x y + metric.distance y z)
```

The proof term packages:

- `DistanceSelf metric`;
- `DistanceNonnegative metric`;
- `DistanceEqZeroIff metric`;
- `DistanceSymmetric metric`;
- `TriangleInequality metric`.

The lesson is that the mathematical proof and the Lean proof are both just
structured unpacking.  The Lean proof makes the projection nature explicit.

## Drill Questions

Before filling the LaTeX proof body, answer these without looking:

- Which clauses are literally part of the metric definition?
- Which clause must be derived?
- Which direction of \(d(x,x)=0\Longleftrightarrow x=x\) is used?
- Why is this theorem still useful if most of it repeats the definition?
- How will this theorem be used inside the rearranged triangle inequality?

## Promotion Gate

Populate `prf-metric-basic-consequences.tex` only after a handwritten proof has
been produced or reviewed.  The final proof should be short: this is an
unpacking theorem, not a creative estimate.
