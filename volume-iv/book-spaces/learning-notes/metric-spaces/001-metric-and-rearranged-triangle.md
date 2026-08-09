# Learning Note 001: Metric and Rearranged Triangle Inequality

Status: first metric-space proof gate.

## Targets

| Gate | Label or Lean name | Artifact status |
| --- | --- | --- |
| M1 | `def:metric-on-set` | Active TeX definition; Lean `MetricDefinition`. |
| M2 | `def:metric-space` | Active TeX definition; Lean `MetricSpaceDefinition`. |
| M3 | `thm:metric-basic-consequences` | Active TeX theorem and proof stub; Lean `MetricDefinition.MetricBasicConsequences`. |
| M4 | `thm:metric-rearranged-triangle-inequality` | Active TeX theorem and proof file; Lean theorem exists. |

## What Must Be Understood

A metric is not just a formula for distance.  It is a function together with
axioms.  Every proof in the first metric block should be readable as controlled
unpacking of those axioms.

The basic proof moves are:

- use positive definiteness to get `d(x,x)=0` and `d(x,y)=0 iff x=y`;
- use symmetry to reverse the order of the two inputs;
- use the triangle inequality to compare a direct distance with a two-leg path;
- use elementary real inequalities to rearrange the result.

## Lean Alignment

The textbook-level metric record lives in:

- `LRA.VolumeIV.MetricSpaces.Compatibility.Metric`
- declaration: `MetricDefinition`

The textbook-level metric-space package lives in:

- `LRA.VolumeIV.MetricSpaces.Compatibility.MetricSpace`
- declaration: `MetricSpaceDefinition`

The immediate metric consequences and rearranged triangle theorem live in:

- `LRA.VolumeIV.MetricSpaces.Foundations.InitialTheorems`

Important declarations:

- `MetricDefinition.MetricBasicConsequences`
- `MetricDefinition.DistanceSelf`
- `MetricDefinition.DistanceNonnegative`
- `MetricDefinition.DistanceEqZeroIff`
- `MetricDefinition.DistanceSymmetric`
- `MetricDefinition.TriangleInequality`
- `MetricDefinition.ReverseTriangleInequality`
- `RearrangementOfTriangleInequalityFromMetricDefinition`
- `rearrangement_of_triangle_inequality`

There are two useful Lean versions of the rearranged triangle inequality:

1. `RearrangementOfTriangleInequalityFromMetricDefinition` uses the custom
   textbook metric record.
2. `rearrangement_of_triangle_inequality` uses Mathlib's `[MetricSpace X]`
   interface and `dist`.

The TeX theorem is written in textbook notation \(d(a,b)\), so its
`\LeanFormalizes` crosswalk points to the custom-record Lean theorem.  The
Mathlib theorem is still the more reusable downstream interface.

## Handwritten Proof Skeleton

To prove
\[
  |d(a,b)-d(b,c)| \le d(a,c),
\]
prove two one-sided inequalities.

First use the triangle inequality on the path from \(a\) to \(b\) through
\(c\):
\[
  d(a,b) \le d(a,c)+d(c,b).
\]
By symmetry, \(d(c,b)=d(b,c)\), so
\[
  d(a,b)-d(b,c) \le d(a,c).
\]

Second use the triangle inequality on the path from \(b\) to \(c\) through
\(a\):
\[
  d(b,c) \le d(b,a)+d(a,c).
\]
By symmetry, \(d(b,a)=d(a,b)\), so
\[
  d(b,c)-d(a,b) \le d(a,c).
\]

This second inequality is
\[
  -(d(a,b)-d(b,c)) \le d(a,c).
\]

Together these say that a real number and its negative are both bounded above
by \(d(a,c)\), which is exactly the absolute-value estimate.

## Gate Check

Before moving to standard metric examples, be able to answer:

- Which exact metric axiom proves each line?
- Where is symmetry used?
- Why are two triangle-inequality applications needed?
- Which real-number fact converts the two one-sided estimates into an
  absolute-value inequality?
- How does the textbook statement differ from the Mathlib `dist` statement?
