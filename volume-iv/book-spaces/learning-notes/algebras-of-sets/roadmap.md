# Algebras of Sets Chapter Roadmap

Status: planning note for the parked `Algebras of Sets` chapter.

Purpose: make the chapter a tactical mathematical toolkit for moving from
basic set manipulation into metric spaces, topology, measure theory,
multivariable analysis, probability, and functional analysis.  The central
path is: one or two sets, finite families, countable families, families of
subsets selected by predicates, closure rules, generated systems, finite set
algebras, sigma-algebras, and the Borel sigma-algebra on Euclidean spaces.

The active chapter is currently gated.  Promotion should require both
handwritten proof evidence and Lean proof evidence for the core theorem groups
below.

## Guiding Principle

The first goal is not to memorize definitions of algebras and sigma-algebras.
The first goal is to manipulate subsets cold.

Every later structure in this chapter is a family of subsets selected from an
ambient power set, often by a predicate or structural rule: open sets, closed
sets, balls, intervals, rectangles, measurable sets, null sets, compact sets,
bounded sets, and so on.  The same operations recur in many subjects:

- union and intersection;
- complement relative to an ambient set;
- set difference and symmetric difference;
- finite, countable, and arbitrary unions/intersections;
- subset inclusion and order reversal under complement;
- preimages under functions;
- generated closed systems.

The chapter should therefore assume the Volume I set-manipulation toolkit,
recall those facts only at the point of use, and begin its own active work with
families of subsets, set systems, closure rules, generated systems, algebras,
sigma-algebras, and Euclidean Borel generation.

## Motivation: Preserve the Pieces

The chapter exists because later subjects constantly move one level above
ordinary subsets.  A single subset `A subset X` records which points of `X`
are selected.  A family `F subset \mathcal P(X)` records which subsets of `X`
are selected.  Those are different kinds of data.

This distinction matters because replacing a family by its union usually
throws away the structure.  If `F` is a collection of intervals, balls, boxes,
or open sets, then `union F` is only one subset of the ambient space.  It no
longer remembers the individual pieces, whether the pieces were intervals,
whether the collection was countable, whether it was a basis, whether it was a
cover, or whether it was stable under an operation.

The type-level bookkeeping should become automatic:

- `x in A`;
- `A subset X`;
- `A in F`;
- `F subset \mathcal P(X)`;
- `F in \mathcal P(\mathcal P(X))`;
- `union F subset X`;
- `intersection F subset X`, when the intersection is taken over a family.

Once those levels are clear, the recurring questions become concrete:

- Is the family finite or countable?
- Does the family cover the ambient space?
- Is it closed under finite unions, countable unions, intersections, or
  complements?
- What is the smallest closed system containing it?
- What does a function preserve by preimage?

This is the tactical bridge to bases and covers in topology, generated
sigma-algebras in measure theory, rational boxes in `R^n`, and measurable
sets in multivariable analysis.

## Mastery Gates

Each gate should be proved by hand and in Lean before the corresponding active
content is promoted.

### Gate 0: Prerequisite Set Manipulation

This gate is a prerequisite checklist, not a printed opening section of the
Volume IV chapter.  The theorem statements live in
`gate-1-set-manipulation-theorems.md` so they can be proved and memorialized in
Volume I and Lean.  Volume IV should cite or recall these facts locally when
they are used to build higher structures.

The chapter should not open with a long list of set identities.  That would
duplicate Volume I and obscure the tactical point of this chapter.

Required techniques:

- know how to use extensionality and membership proofs;
- use Boolean operations on subsets fluently;
- use De Morgan laws and difference identities when proving closure results;
- use image, preimage, and preimage-composition laws when transporting set
  systems.

Local recall policy:

- Use a short `remark*` when a prior identity drives a construction.
- Prefer local recall at the point of use over an upfront theorem wall.
- Do not create new extracted theorem artifacts in Volume IV for facts whose
  canonical proof lives in Volume I.
- Use hyperlinks to Volume I statement labels once those labels exist.

External proof gate:

- handwritten proofs or proof stubs in Volume I;
- Lean proofs or deliberate `sorry` stubs;
- dependencies recorded so Volume IV can cite these tools without reproving
  raw set identities.

### Gate 1: Families of Subsets

This is the first substantive Volume IV gate.  It separates the idea of a
family from the stronger idea of closure.  A family is just a selected
collection of subsets of an ambient set.  It may be finite, countable,
arbitrary, indexed, or defined by a predicate such as `is open`, `is closed`,
`is bounded`, `is measurable`, or `is a ball`.

Required techniques:

- move from one or two named sets to finite indexed families;
- move from finite indexed families to countable sequences of sets;
- distinguish a family of subsets from a member of that family;
- distinguish an indexed family `(A_i)_{i in I}` from its range
  `{A_i : i in I}`;
- express predicate-defined families inside `\mathcal P(X)`;
- compare families by inclusion.

Required theorems:

1. Families inside the power set.
   - A family of subsets of `X` is a subset of `\mathcal P(X)`.
   - The empty family and full power set are both families of subsets.
   - Operations on members of a family always land in `\mathcal P(X)`, even
     when they do not land back in the family.
   - If `P(A)` is a predicate on subsets of `X`, then
     `{A subset X : P(A)}` is a family of subsets of `X`.
   - If `F subset G subset \mathcal P(X)`, then every member of `F` is a
     member of `G`.

2. One or two sets as the base case.
   - Pair families `{A, B}`.
   - Two-set unions and intersections.
   - Two-set complements, differences, and symmetric differences.
   - Two-set containment comparisons.

3. Finite families.
   - Finite indexed families `(A_i)_{i in I}` with `I` finite.
   - Finite unions and finite intersections.
   - Empty finite union and empty finite intersection conventions.
   - Finite De Morgan laws are recalled locally from Volume I when needed.
   - Finite monotonicity of unions and intersections.
   - Finite subfamilies and refinement of finite partitions.

4. Countable families.
   - Countable indexed families and sequences `(A_n)_{n in N}`.
   - Countable unions and countable intersections.
   - Countable De Morgan laws are recalled locally from Volume I when needed.
   - Countable monotonicity of unions and intersections.
   - Increasing and decreasing sequences of sets.
   - `limsup A_n` and `liminf A_n` as countable unions/intersections.

5. Predicate-defined tactical families.
   - Open subsets of a metric or topological space.
   - Closed subsets.
   - Balls and rational balls.
   - Intervals, rectangles, boxes, and rational boxes.
   - Bounded subsets.
   - Compact subsets, once topology is available.
   - Measurable subsets, once sigma-algebras are available.
   - Null sets, once measures are available.

Promotion gate:

- handwritten exercises translating predicate-defined descriptions into
  subset-family notation;
- Lean proofs for finite and countable family identities where feasible;
- examples distinguishing a family from an element of the family.

### Gate 2: Order, Posets, and Lattices of Sets

This gate explains why set manipulation is also order manipulation.

Required techniques:

- read `A subset B` as an order relation;
- identify least and greatest elements;
- prove monotonicity and antitonicity;
- prove universal properties of union and intersection;
- move between elementwise proofs and order-theoretic proofs.

Required theorems:

1. Poset structure.
   - `(\mathcal P(X), subset)` is a poset.
   - Reflexivity: `A subset A`.
   - Antisymmetry: if `A subset B` and `B subset A`, then `A = B`.
   - Transitivity: if `A subset B` and `B subset C`, then `A subset C`.
   - `empty` is the least element.
   - `X` is the greatest element.

2. Monotonicity of union and intersection.
   - If `A subset B`, then `A union C subset B union C`.
   - If `A subset B`, then `C union A subset C union B`.
   - If `A subset B`, then `A intersection C subset B intersection C`.
   - If `A subset B`, then `C intersection A subset C intersection B`.
   - If `A_i subset B_i` for every index `i`, then
     `union_i A_i subset union_i B_i`.
   - If `A_i subset B_i` for every index `i`, then
     `intersection_i A_i subset intersection_i B_i`.

3. Complement reverses order.
   - If `A subset B`, then `B^c subset A^c`.
   - `A subset B` iff `B^c subset A^c`.
   - Complement is an order-reversing involution.

4. Difference monotonicity.
   - If `A subset B`, then `A \ C subset B \ C`.
   - If `A subset B`, then `C \ B subset C \ A`.
   - Difference is monotone in the first argument.
   - Difference is antitone in the second argument.

5. Meet and join.
   - `A intersection B` is the greatest lower bound of `A` and `B`.
   - `A union B` is the least upper bound of `A` and `B`.
   - In `\mathcal P(X)`, meet is intersection and join is union.

6. Finite lattice laws.
   - Absorption: `A intersection (A union B) = A`.
   - Absorption: `A union (A intersection B) = A`.
   - Distributivity of meet over join.
   - Distributivity of join over meet.

7. Complete lattice facts.
   - For any family `E subset \mathcal P(X)`, `union E` is `sup E`.
   - For any family `E subset \mathcal P(X)`, `intersection E` is `inf E`.
   - `\mathcal P(X)` is a complete lattice.

8. Boolean lattice facts.
   - `\mathcal P(X)` is bounded.
   - `\mathcal P(X)` is distributive.
   - `\mathcal P(X)` is complemented.
   - `\mathcal P(X)` is atomic.
   - The atoms are singleton sets `{x}` for `x in X`.
   - Every subset of `X` is the union of its singleton atoms.

Promotion gate:

- handwritten proofs of the poset and lattice facts;
- Lean proofs of the monotonicity and antitonicity facts;
- one proof translating a set identity into a lattice statement and back.

### Gate 3: Closure Rules and Generated Systems

This gate turns families of subsets into structures by requiring stability
under selected operations.  Closure is a property of a family, not part of the
bare meaning of family.

Required techniques:

- distinguish an operation being defined from a family being closed under it;
- prove closure by taking arbitrary admitted inputs;
- recognize closure under one or two sets, finite families, countable
  families, and arbitrary families;
- use intersections of all admissible closed systems to define generated
  systems;
- prove minimality by containment in every admissible closed system.

Required theorems:

1. Closure conditions.
   - Closed under pairwise unions.
   - Closed under pairwise intersections.
   - Closed under complements.
   - Closed under differences.
   - Closed under symmetric differences.
   - Closed under finite unions.
   - Closed under finite intersections.
   - Closed under countable unions.
   - Closed under countable intersections.
   - Closed under arbitrary unions/intersections when needed.

2. From pairwise to finite closure.
   - Pairwise union closure plus induction gives finite union closure.
   - Pairwise intersection closure plus induction gives finite intersection
     closure.
   - Complement plus finite union closure gives finite intersection closure.
   - Complement plus finite intersection closure gives finite union closure.

3. Generated systems.
   - The intersection of any collection of systems satisfying a fixed closure
     rule again satisfies that closure rule, when the rule is intersection
     stable.
   - The generated closed system containing a seed family exists as the
     intersection of all closed systems containing the seed.
   - The generated system contains the seed.
   - The generated system satisfies the required closure rules.
   - The generated system is contained in every closed system containing the
     seed.
   - Two generated systems are equal if each seed family is contained in the
     system generated by the other.

Promotion gate:

- handwritten proof of existence by intersection of all admissible systems;
- Lean proof for at least one generated closure construction;
- several generator-change proofs.

### Gate 4: Finite Algebras of Sets

This gate introduces algebras of sets as finite Boolean closure structures.

Required techniques:

- prove equivalent definitions;
- derive closure under missing operations;
- use finite induction over unions and intersections;
- work with atoms and finite partitions.

Required theorems:

1. Equivalent definitions.
   - A set algebra on `X` is a family `A subset \mathcal P(X)` containing `X`,
     closed under complements, and closed under finite unions.
   - Equivalently: contains `empty`, closed under complements, and closed
     under finite unions.
   - Equivalently: contains `X`, closed under complements, and closed under
     finite intersections.
   - Equivalently: closed under finite Boolean combinations.

2. Closure consequences.
   - Every algebra of sets contains `empty`.
   - Every algebra of sets is closed under finite intersections.
   - Every algebra of sets is closed under set difference.
   - Every algebra of sets is closed under symmetric difference.
   - Every algebra of sets is closed under finite disjoint unions.
   - Every algebra of sets is closed under finite indexed unions.
   - Every algebra of sets is closed under finite indexed intersections.

3. Generated finite algebras.
   - The algebra generated by a family exists as the intersection of all
     algebras containing it.
   - For finitely many generators `A_1, ..., A_n`, the atoms are intersections
     of choices `A_i` or `A_i^c`.
   - The nonempty atoms form a finite partition of `X`.
   - Every member of the generated algebra is a union of atoms.
   - The algebra generated by `n` sets has at most `2^(2^n)` members.
   - If the generated partition has exactly `m` nonempty atoms, the generated
     algebra has exactly `2^m` members.

4. Finite algebra structure.
   - Atoms of a finite algebra partition `X`.
   - Every member of a finite algebra is a union of atoms.
   - Every finite algebra is generated by its atoms.
   - Every finite algebra of sets is a sigma-algebra, because every countable
     union of members reduces to a finite union.

5. Boolean-ring viewpoint.
   - With addition `A triangle B` and multiplication `A intersection B`, an
     algebra of sets is a Boolean ring.
   - `A^2 = A`.
   - `A union B = A triangle B triangle (A intersection B)`.
   - `A^c = X triangle A`.

Promotion gate:

- handwritten proofs of the equivalent definitions;
- handwritten proof of the atom partition theorem;
- Lean proof that a finite algebra is a sigma-algebra where feasible;
- Lean proof of the Boolean-ring identities where feasible.

### Gate 5: Sigma-Algebras and Countable Closure

This gate should come after finite algebras and before Borel generation.

Required theorems:

- Definition of a sigma-algebra on `X`.
- Every sigma-algebra is an algebra of sets.
- A sigma-algebra is closed under countable intersections.
- A sigma-algebra is closed under countable differences where appropriate.
- A sigma-algebra is closed under limsup and liminf of sequences of sets.
- The intersection of any collection of sigma-algebras on `X` is a
  sigma-algebra.
- The generated sigma-algebra `sigma(E)` exists.
- `sigma(E) subset M` iff `E subset M`, for every sigma-algebra `M`.
- Generation is monotone: if `E subset F`, then `sigma(E) subset sigma(F)`.
- Generation is idempotent: `sigma(sigma(E)) = sigma(E)`.

Promotion gate:

- handwritten proof of the generated sigma-algebra universal property;
- Lean proof of monotonicity and idempotence of generation where feasible;
- one proof using the universal property to compare generated sigma-algebras.

### Gate 6: Euclidean Borel Toolkit

This gate should give enough Borel structure for topology and measure theory,
especially on `R` and `R^n`.  It should not become a descriptive set theory or
cardinality chapter.

Required theorems:

- For a topological space `(X, tau)`, the Borel sigma-algebra is `sigma(tau)`.
- For `R`, the following families generate the same Borel sigma-algebra:
  open sets, open intervals, closed intervals, half-open intervals, open rays,
  closed rays, and rational-endpoint intervals.
- For `R^n`, the following families generate the same Borel sigma-algebra:
  open sets, open balls, closed balls, open rectangles, closed rectangles,
  half-open rectangles, and rational boxes.
- `B(R^n)` agrees with the product sigma-algebra
  `B(R) tensor ... tensor B(R)`.
- Every open subset of `R^n` is a countable union of rational boxes.
- Every closed subset of `R^n` is Borel.
- `F_sigma` and `G_delta` subsets of `R^n` are Borel.
- Countable subsets of `R^n` are Borel.
- Singletons in `R^n` are Borel.
- If `f : X -> Y` is continuous between topological spaces, then preimages of
  Borel sets are Borel.
- Continuous real-valued and vector-valued functions on Euclidean domains are
  Borel measurable.
- Coordinate projections `pi_i : R^n -> R` are Borel measurable.
- A map `f : X -> R^n` is Borel measurable iff each coordinate function is
  Borel measurable.
- Finite-dimensional linear maps `R^n -> R^m` are Borel measurable.
- Norms and distances on `R^n` are Borel measurable.

Useful examples:

- intervals and rays in `R`;
- boxes and balls in `R^n`;
- open, closed, `F_sigma`, and `G_delta` sets;
- inverse images such as `{x : f(x) < a}`, `{x : f(x) <= a}`, and
  `{x : f(x) in U}`;
- simple examples of non-open Borel sets, such as closed sets, countable sets,
  and half-open rectangles.

Deferred material:

- full transfinite Borel hierarchy;
- non-collapse of the Borel hierarchy;
- Polish-space descriptive set theory;
- Stone representation and complete Boolean algebra theory.
- cardinality of the Borel sigma-algebra;
- nonmeasurable sets except as a later motivational warning in measure theory.

## Proposed Chapter Order

1. Short prerequisite remark pointing to the Volume I set-manipulation toolkit.
2. Families of subsets.
3. One-set, two-set, finite-family, and countable-family language.
4. Predicate-defined families of subsets.
5. Subset inclusion as order.
6. Union and intersection as join and meet.
7. Complement as order reversal.
8. Power set as a Boolean lattice.
9. Closure questions for families.
10. Generated systems by intersection of admissible systems.
11. Finite algebras of sets.
12. Atoms and finite partitions.
13. Boolean-ring viewpoint.
14. Sigma-algebras and countable closure.
15. Borel sigma-algebras on `R` and `R^n`.
16. Summary and forward use.

## Comparison with Parked Chapter Material

The parked material already has a strong scaffold:

- `from-sets-to-systems-of-sets`;
- `operations-on-families-of-sets`;
- `closure-under-operations`;
- `generated-systems-of-sets`;
- `semirings-and-rings-of-sets`;
- `algebras-of-sets`;
- `sigma-algebras`;
- `boolean-viewpoint`;
- `transport-of-set-systems`;
- `borel-generation`;
- `working-with-set-systems`;
- `summary-and-forward-use`.

That scaffold matches the broad direction of this roadmap.  The main gaps are
not high-level topic gaps.  They are theorem-gate and ordering gaps.

### Gap 1: Raw set manipulation belongs in Volume I, not as a long Volume IV opening

The parked chapter starts at families and operations on families.  It assumes
basic identities from earlier material.  That is acceptable if the prerequisite
toolkit is explicit and the identities are recalled locally when they are used.
The chapter should not print a long list of 79 set identities up front.

Needed addition:

- a short prerequisite remark pointing to Volume I;
- an explicit progression from one or two sets, to finite families, to
  countable families;
- local recalls of union, intersection, complement, difference, symmetric
  difference, image, preimage, and composition facts at the point of use;
- no new extracted theorem artifacts in Volume IV for facts already owned by
  Volume I.

### Gap 1.5: Families and closure should be separated

The parked material tends to move quickly from families to closure questions.
For this chapter, those should be distinct conceptual layers.

Needed addition:

- a family-only section treating subsets of `\mathcal P(X)`;
- indexed families versus ranges of indexed families;
- finite families and countable families before closure rules;
- predicate-defined families such as open sets, closed sets, balls, intervals,
  boxes, bounded sets, compact sets, measurable sets, and null sets;
- a separate closure section that asks which operations preserve membership in
  a chosen family.

### Gap 2: Poset and lattice structure is not explicit enough

The parked material treats `\mathcal P(X)` as the ambient universe, but it does
not foreground `(\mathcal P(X), subset)` as a poset, lattice, complete lattice,
and Boolean lattice.

Needed addition:

- a section before closure systems called something like `Order and Lattice
  Structure of the Power Set`;
- monotonicity of union and intersection;
- antitonicity of complement;
- monotonicity and antitonicity of difference;
- meet/join universal properties;
- complete lattice facts for arbitrary unions/intersections.

### Gap 3: Finite algebra atom theory is not visible in the outline

The parked material has `algebras-of-sets`, `generated-algebras`, and Boolean
viewpoint files, but the outline does not visibly isolate atoms, finite
partitions, and the counting theorem for finite generated algebras.

Needed addition:

- atom definition for finite algebras;
- nonempty atoms form a partition;
- every algebra element is a union of atoms;
- finite generated algebra has at most `2^(2^n)` members;
- exact size `2^m` when there are `m` nonempty atoms.

### Gap 4: The proof gate is not encoded in the parked chapter

The active notes index says content is parked until Lean/formal promotion, but
there is no chapter-local list of required handwritten and Lean proof targets.

Needed addition:

- keep this roadmap as the chapter-local gate checklist;
- optionally add a future `proof-gates.yaml` or similar machine-readable
  checklist once the theorem labels exist.

### Gap 5: Borel material should be Euclidean and practical

The parked `borel-generation` section is appropriately scoped as generation
from distinguished families.  It should be strengthened in the Euclidean
direction and bounded away from cardinality and descriptive set theory.

Needed boundary:

- include Borel sigma-algebras as generated sigma-algebras on `R` and `R^n`;
- include standard generator equivalences for intervals, rays, rectangles,
  boxes, balls, and rational boxes;
- include enough product-sigma-algebra facts for `B(R^n)`;
- include Borel measurability of continuous maps, coordinate projections,
  norms, and distances;
- include `F_sigma` and `G_delta` as first examples;
- defer the transfinite Borel hierarchy and non-collapse theorem.
- defer cardinality questions.

## Immediate Next Work

1. Decide whether to add new parked TeX sections for the separated
   family/closure gates and the order/lattice gate.
2. If yes, create parked routers for:
   - `families-of-subsets`;
   - `order-and-lattice-structure`;
   - `closure-rules`;
   - possibly `atoms-and-finite-partitions`.
3. Keep `gate-1-set-manipulation-theorems.md` as the Volume I/Lean proof
   checklist and prerequisite inventory.
4. Populate theorem/proof target labels only after checking the canonical
   artifact standards and Lean naming conventions.
5. Do not promote active chapter content until the handwritten and Lean gates
   have evidence.
