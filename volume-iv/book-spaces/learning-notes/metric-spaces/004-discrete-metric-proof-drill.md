# Learning Note 004: Discrete Metric Proof Drill

Status: proof drill and Lean crosswalk for M7-M8.

Targets:

- M7 TeX label: `def:discrete-metric`
- M8 TeX label: `prop:discrete-metric-space`
- Lean distance declaration: `MetricDefinition.DiscreteDistance`
- Lean metric theorem: `MetricDefinition.DiscreteDistanceIsMetric`
- Proof file: `proofs/metrics/prf-discrete-metric-space.tex`

## Statement

For every nonempty set \(X\), the discrete distance
\[
  d_{\mathrm{disc}}(x,y)=
  \begin{cases}
    0, & x=y,\\
    1, & x\neq y
  \end{cases}
\]
is a metric on \(X\).

The nonempty assumption is pedagogically harmless but not essential: the metric
axioms are universally quantified, so they are vacuous on the empty set.  Lean
states the construction for any type with decidable equality.

## What Must Be Checked

To prove the discrete distance is a metric, check each metric axiom.

Nonnegativity:

- if \(x=y\), then \(d_{\mathrm{disc}}(x,y)=0\);
- if \(x\neq y\), then \(d_{\mathrm{disc}}(x,y)=1\);
- both \(0\) and \(1\) are nonnegative.

Zero-distance characterization:

- if \(x=y\), the distance is \(0\);
- if the distance is \(0\), the \(x\neq y\) case is impossible because then the
  distance would be \(1\).

Symmetry:

- equality is symmetric;
- inequality is symmetric;
- therefore the two-case definition gives the same value for \(d(x,y)\) and
  \(d(y,x)\).

Triangle inequality:

- if \(x=z\), then \(d(x,z)=0\), so the inequality is immediate;
- if \(x\neq z\), then \(d(x,z)=1\);
- in that case, at least one of \(x\neq y\) or \(y\neq z\) must hold;
- hence at least one term on the right is \(1\), so
  \[
    1 \leq d(x,y)+d(y,z).
  \]

## Lean Reading

Lean splits the construction into small facts:

- `DiscreteDistance`;
- `DiscreteDistanceEqZeroIff`;
- `DiscreteDistanceNonnegative`;
- `DiscreteDistanceSymmetric`;
- `DiscreteDistanceTriangle`;
- `DiscreteMetricDefinition`;
- `DiscreteDistanceIsMetric`.

The theorem `DiscreteDistanceIsMetric` says there is a `MetricDefinition` whose
distance field is exactly `DiscreteDistance`.

## Drill Questions

Before filling the proof body, answer:

- Why is the empty-set case not a real obstacle?
- In the triangle inequality, why can \(x\neq z\) not coexist with both
  \(x=y\) and \(y=z\)?
- Which metric axiom is easiest for the discrete metric?
- Which metric axiom is the only one that needs a real case split?
- How does the Lean proof encode "the function is a metric" using a
  `MetricDefinition` record?

## Promotion Gate

The proof file remains a TODO stub until a handwritten proof has been produced
or reviewed.  This proof should be owned as the first full metric axiom-check
example.
