# Learning Note 003: Rearranged Triangle Inequality Proof Drill

Status: handwritten proof drill for M4.

Target:

- TeX label: `thm:metric-rearranged-triangle-inequality`
- Closest Lean declaration:
  `RearrangementOfTriangleInequalityFromMetricDefinition`
- Mathlib-interface Lean declaration:
  `rearrangement_of_triangle_inequality`
- Proof file:
  `proofs/metric-spaces/prf-metric-rearranged-triangle-inequality.tex`

The TeX statement uses textbook notation \(d(a,b)\), so the closest Lean
crosswalk is the custom-record theorem with `metric.distance`.  The Mathlib
`dist` version remains useful downstream, but it is not the closest formal
shape of the printed theorem.

## Statement

Let \((X,d)\) be a metric space.  For all \(a,b,c\in X\),
\[
  \bigl|d(a,b)-d(b,c)\bigr|\leq d(a,c).
\]

## What Is Being Proved

The theorem says that the two distances from the same base point \(b\) cannot
differ by more than the distance between the other two endpoints \(a\) and
\(c\).

This is the first real metric estimate in the restart.  Unlike M3, it is not
just unpacking an axiom.  It uses the triangle inequality twice, symmetry twice,
and a real-number absolute-value fact.

## Proof Skeleton

Let
\[
  t=d(a,b)-d(b,c).
\]

To prove \(|t|\leq d(a,c)\), prove the two inequalities
\[
  t\leq d(a,c)
  \qquad\text{and}\qquad
  -t\leq d(a,c).
\]

First triangle path: \(a\to c\to b\).

\[
  d(a,b)\leq d(a,c)+d(c,b).
\]

By symmetry, \(d(c,b)=d(b,c)\), hence
\[
  d(a,b)\leq d(a,c)+d(b,c).
\]

Subtract \(d(b,c)\):
\[
  d(a,b)-d(b,c)\leq d(a,c).
\]

This is \(t\leq d(a,c)\).

Second triangle path: \(b\to a\to c\).

\[
  d(b,c)\leq d(b,a)+d(a,c).
\]

By symmetry, \(d(b,a)=d(a,b)\), hence
\[
  d(b,c)\leq d(a,b)+d(a,c).
\]

Subtract \(d(a,b)\):
\[
  d(b,c)-d(a,b)\leq d(a,c).
\]

This is \(-t\leq d(a,c)\).

The real-number fact now applies:

\[
  t\leq r \text{ and } -t\leq r
  \quad\Longrightarrow\quad
  |t|\leq r.
\]

With \(r=d(a,c)\), the desired estimate follows.

## Lean Reading

The custom-record Lean theorem is:

```lean
theorem RearrangementOfTriangleInequalityFromMetricDefinition
    {X : Type u}
    (metric : MetricDefinition X)
    (a b c : X) :
    |metric.distance a b - metric.distance b c| ≤ metric.distance a c
```

Lean proves it by reusing the more general-looking custom theorem:

```lean
MetricDefinition.ReverseTriangleInequality metric a c b
```

That theorem has shape:

```lean
|metric.distance x z - metric.distance y z| ≤ metric.distance x y
```

Substitute \(x=a\), \(y=c\), and \(z=b\).  This gives
\[
  |d(a,b)-d(c,b)|\leq d(a,c).
\]

Then symmetry rewrites \(d(c,b)\) to \(d(b,c)\).

## Drill Questions

Before treating the proof as owned, answer these cold:

- Which two triangle paths are used?
- Where exactly is symmetry used?
- Why does one triangle inequality application not suffice?
- What is the real-number fact about \(|t|\) being used?
- How does the Lean proof compress the two-sided handwritten argument?
- Why is the custom-record Lean theorem a better TeX crosswalk than the
  Mathlib `dist` theorem?

## Promotion Gate

The active proof file already contains a full two-layer proof.  Before relying
on it as owned restart material, reproduce the proof by hand from the skeleton
above and compare each line against the TeX proof.
