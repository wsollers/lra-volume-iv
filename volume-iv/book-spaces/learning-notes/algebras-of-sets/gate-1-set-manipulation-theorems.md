# Gate 1 Theorem Statements: Elementwise Set Manipulation

Status: theorem-statement specification for handwritten and Lean proof stubs.

Scope: this file lists the rigorous theorem targets for the first mastery gate
of the `Algebras of Sets` chapter.  It is not active chapter content.

Conventions:

- `X` is a fixed ambient type or set.
- `A`, `B`, and `C` are subsets of `X`.
- `empty` denotes the empty subset of `X`.
- `univ` or `X` denotes the full ambient subset.
- `A^c` denotes complement relative to `X`.
- `A \ B` denotes set difference.
- `A triangle B` denotes symmetric difference.
- For a function `f : X -> Y` and a subset `S subset Y`, `preimage f S`
  denotes `{x in X : f x in S}`.
- Indexed finite versions may be formalized with finite sets, `Fin n`, or
  finite index types, depending on the target Lean conventions.

## 1. Extensionality and Subset Criteria

### set_ext_iff

Exists: Y (current Lean: `LRA.VolumeI.Set.LRASet.Extensionality`; one-way extensionality declaration, not a named iff theorem.)

For all subsets `A B subset X`,

```text
A = B iff forall x in X, x in A iff x in B.
```

### subset_antisymm_eq

Exists: N (no current `LRA/VolumeI/Set` subset antisymmetry theorem found.)

For all subsets `A B subset X`,

```text
if A subset B and B subset A, then A = B.
```

### subset_iff_union_eq_right

Exists: N (no current theorem equating subset with union absorption found.)

For all subsets `A B subset X`,

```text
A subset B iff A union B = B.
```

### subset_iff_inter_eq_left

Exists: N (no current theorem equating subset with intersection absorption found.)

For all subsets `A B subset X`,

```text
A subset B iff A intersection B = A.
```

## 2. Identity and Domination Laws

### union_empty

Exists: Y (current Lean: `LRA.VolumeI.Set.Operations.Laws.UnionEmpty`.)

For every subset `A subset X`,

```text
A union empty = A.
```

### empty_union

Exists: Y (current Lean: `LRA.VolumeI.Set.Operations.Laws.EmptyUnion`.)

For every subset `A subset X`,

```text
empty union A = A.
```

### inter_univ

Exists: Y (current Lean: `LRA.VolumeI.Set.Operations.Laws.IntersectionUniversal`.)

For every subset `A subset X`,

```text
A intersection X = A.
```

### univ_inter

Exists: Y (current Lean: `LRA.VolumeI.Set.Operations.Laws.UniversalIntersection`.)

For every subset `A subset X`,

```text
X intersection A = A.
```

### union_univ

Exists: Y (current Lean: `LRA.VolumeI.Set.Operations.Laws.UnionUniversal`.)

For every subset `A subset X`,

```text
A union X = X.
```

### univ_union

Exists: Y (current Lean: `LRA.VolumeI.Set.Operations.Laws.UniversalUnion`.)

For every subset `A subset X`,

```text
X union A = X.
```

### inter_empty

Exists: Y (current Lean: `LRA.VolumeI.Set.Operations.Laws.IntersectionEmpty`.)

For every subset `A subset X`,

```text
A intersection empty = empty.
```

### empty_inter

Exists: Y (current Lean: `LRA.VolumeI.Set.Operations.Laws.EmptyIntersection`.)

For every subset `A subset X`,

```text
empty intersection A = empty.
```

## 3. Idempotent, Commutative, and Associative Laws

### union_idempotent

Exists: Y (current Lean: `LRA.VolumeI.Set.Operations.Laws.UnionIdempotent`.)

For every subset `A subset X`,

```text
A union A = A.
```

### inter_idempotent

Exists: Y (current Lean: `LRA.VolumeI.Set.Operations.Laws.IntersectionIdempotent`.)

For every subset `A subset X`,

```text
A intersection A = A.
```

### union_comm

Exists: Y (current Lean: `LRA.VolumeI.Set.Operations.Laws.UnionCommutative`.)

For all subsets `A B subset X`,

```text
A union B = B union A.
```

### inter_comm

Exists: Y (current Lean: `LRA.VolumeI.Set.Operations.Laws.IntersectionCommutative`.)

For all subsets `A B subset X`,

```text
A intersection B = B intersection A.
```

### union_assoc

Exists: Y (current Lean: `LRA.VolumeI.Set.Operations.Laws.UnionAssociative`.)

For all subsets `A B C subset X`,

```text
(A union B) union C = A union (B union C).
```

### inter_assoc

Exists: Y (current Lean: `LRA.VolumeI.Set.Operations.Laws.IntersectionAssociative`.)

For all subsets `A B C subset X`,

```text
(A intersection B) intersection C = A intersection (B intersection C).
```

## 4. Distributive Laws

### inter_union_distrib_left

Exists: N (no current LRA Lean theorem declaration found.)

For all subsets `A B C subset X`,

```text
A intersection (B union C) =
  (A intersection B) union (A intersection C).
```

### union_inter_distrib_left

Exists: N (no current LRA Lean theorem declaration found.)

For all subsets `A B C subset X`,

```text
A union (B intersection C) =
  (A union B) intersection (A union C).
```

### inter_union_distrib_right

Exists: N (no current LRA Lean theorem declaration found.)

For all subsets `A B C subset X`,

```text
(A union B) intersection C =
  (A intersection C) union (B intersection C).
```

### union_inter_distrib_right

Exists: N (no current LRA Lean theorem declaration found.)

For all subsets `A B C subset X`,

```text
(A intersection B) union C =
  (A union C) intersection (B union C).
```

## 5. Complement Laws

### union_compl

Exists: N (no current LRA Lean theorem declaration found.)

For every subset `A subset X`,

```text
A union A^c = X.
```

### compl_union_eq_univ

Exists: N (no current LRA Lean theorem declaration found.)

For every subset `A subset X`,

```text
A^c union A = X.
```

### inter_compl

Exists: N (no current LRA Lean theorem declaration found.)

For every subset `A subset X`,

```text
A intersection A^c = empty.
```

### compl_inter_eq_empty

Exists: N (no current LRA Lean theorem declaration found.)

For every subset `A subset X`,

```text
A^c intersection A = empty.
```

### compl_compl

Exists: Y (current Lean: `LRA.VolumeI.Set.Operations.Laws.DoubleComplement`.)

For every subset `A subset X`,

```text
(A^c)^c = A.
```

### compl_empty

Exists: Y (current Lean: `LRA.VolumeI.Set.Operations.Laws.ComplementEmpty`.)

```text
empty^c = X.
```

### compl_univ

Exists: Y (current Lean: `LRA.VolumeI.Set.Operations.Laws.ComplementUniversal`.)

```text
X^c = empty.
```

## 6. De Morgan Laws

### demorgan_compl_union

Exists: Y (current Lean: `LRA.VolumeI.Set.Operations.Laws.DeMorganUnion`.)

For all subsets `A B subset X`,

```text
(A union B)^c = A^c intersection B^c.
```

### demorgan_compl_inter

Exists: Y (current Lean: `LRA.VolumeI.Set.Operations.Laws.DeMorganIntersection`.)

For all subsets `A B subset X`,

```text
(A intersection B)^c = A^c union B^c.
```

### compl_finite_union

Exists: Y (current Lean: `LRA.VolumeI.Set.Operations.Laws.ComplementIndexedUnion`, stated for an indexed family rather than specifically finite indexes.)

For every finite indexed family `(A_i)_{i in I}` of subsets of `X`,

```text
(union over i in I of A_i)^c =
  intersection over i in I of A_i^c.
```

### compl_finite_inter

Exists: Y (current Lean: `LRA.VolumeI.Set.Operations.Laws.ComplementIndexedIntersection`, stated for an indexed family rather than specifically finite indexes.)

For every finite indexed family `(A_i)_{i in I}` of subsets of `X`,

```text
(intersection over i in I of A_i)^c =
  union over i in I of A_i^c.
```

## 7. Difference Laws

### diff_eq_inter_compl

Exists: Y (current Lean: `LRA.VolumeI.Set.Operations.Laws.DifferenceAsIntersectionComplement`.)

For all subsets `A B subset X`,

```text
A \ B = A intersection B^c.
```

### diff_empty

Exists: Y (current Lean: `LRA.VolumeI.Set.Operations.Laws.DifferenceEmpty`.)

For every subset `A subset X`,

```text
A \ empty = A.
```

### empty_diff

Exists: Y (current Lean: `LRA.VolumeI.Set.Operations.Laws.EmptyDifference`.)

For every subset `A subset X`,

```text
empty \ A = empty.
```

### diff_self

Exists: Y (current Lean: `LRA.VolumeI.Set.Operations.Laws.DifferenceSelf`.)

For every subset `A subset X`,

```text
A \ A = empty.
```

### diff_union

Exists: N (no current LRA Lean theorem declaration found.)

For all subsets `A B C subset X`,

```text
A \ (B union C) = (A \ B) intersection (A \ C).
```

### diff_inter

Exists: N (no current LRA Lean theorem declaration found.)

For all subsets `A B C subset X`,

```text
A \ (B intersection C) = (A \ B) union (A \ C).
```

### union_diff_distrib

Exists: N (no current LRA Lean theorem declaration found.)

For all subsets `A B C subset X`,

```text
(A union B) \ C = (A \ C) union (B \ C).
```

### inter_diff_distrib

Exists: N (no current LRA Lean theorem declaration found.)

For all subsets `A B C subset X`,

```text
(A intersection B) \ C = (A \ C) intersection (B \ C).
```

### diff_subset_left

Exists: N (no current LRA Lean theorem declaration found.)

For all subsets `A B subset X`,

```text
A \ B subset A.
```

### diff_disjoint_right

Exists: N (no current LRA Lean theorem declaration found.)

For all subsets `A B subset X`,

```text
(A \ B) intersection B = empty.
```

## 8. Symmetric Difference Laws

### symm_diff_def

Exists: N (no current LRA Lean theorem declaration found.)

For all subsets `A B subset X`,

```text
A triangle B = (A \ B) union (B \ A).
```

### symm_diff_eq_union_diff_inter

Exists: N (no current LRA Lean theorem declaration found.)

For all subsets `A B subset X`,

```text
A triangle B = (A union B) \ (A intersection B).
```

### symm_diff_comm

Exists: N (no current LRA Lean theorem declaration found.)

For all subsets `A B subset X`,

```text
A triangle B = B triangle A.
```

### symm_diff_empty

Exists: N (no current LRA Lean theorem declaration found.)

For every subset `A subset X`,

```text
A triangle empty = A.
```

### empty_symm_diff

Exists: N (no current LRA Lean theorem declaration found.)

For every subset `A subset X`,

```text
empty triangle A = A.
```

### symm_diff_self

Exists: N (no current LRA Lean theorem declaration found.)

For every subset `A subset X`,

```text
A triangle A = empty.
```

### symm_diff_assoc

Exists: N (no current LRA Lean theorem declaration found.)

For all subsets `A B C subset X`,

```text
(A triangle B) triangle C = A triangle (B triangle C).
```

### symm_diff_eq_empty_iff

Exists: N (no current LRA Lean theorem declaration found.)

For all subsets `A B subset X`,

```text
A triangle B = empty iff A = B.
```

### symm_diff_subset_union

Exists: N (no current LRA Lean theorem declaration found.)

For all subsets `A B subset X`,

```text
A triangle B subset A union B.
```

## 9. Preimage Laws

Let `f : X -> Y`.

### preimage_univ

Exists: N (no current LRA Lean theorem declaration found.)

```text
preimage f Y = X.
```

### preimage_empty

Exists: N (no current LRA Lean theorem declaration found.)

```text
preimage f empty = empty.
```

### preimage_union

Exists: N (no current LRA Lean theorem declaration found.)

For all subsets `B C subset Y`,

```text
preimage f (B union C) =
  (preimage f B) union (preimage f C).
```

### preimage_inter

Exists: N (no current LRA Lean theorem declaration found.)

For all subsets `B C subset Y`,

```text
preimage f (B intersection C) =
  (preimage f B) intersection (preimage f C).
```

### preimage_compl

Exists: N (no current LRA Lean theorem declaration found.)

For every subset `B subset Y`,

```text
preimage f (B^c) = (preimage f B)^c.
```

The complement on the left is relative to `Y`; the complement on the right is
relative to `X`.

### preimage_diff

Exists: N (no current LRA Lean theorem declaration found.)

For all subsets `B C subset Y`,

```text
preimage f (B \ C) =
  (preimage f B) \ (preimage f C).
```

### preimage_symm_diff

Exists: N (no current LRA Lean theorem declaration found.)

For all subsets `B C subset Y`,

```text
preimage f (B triangle C) =
  (preimage f B) triangle (preimage f C).
```

### preimage_finite_union

Exists: N (no current LRA Lean theorem declaration found.)

For every finite indexed family `(B_i)_{i in I}` of subsets of `Y`,

```text
preimage f (union over i in I of B_i) =
  union over i in I of preimage f B_i.
```

### preimage_finite_inter

Exists: N (no current LRA Lean theorem declaration found.)

For every finite indexed family `(B_i)_{i in I}` of subsets of `Y`,

```text
preimage f (intersection over i in I of B_i) =
  intersection over i in I of preimage f B_i.
```

## 10. Preimages and Composition

This section includes only the composition facts needed for transporting set
systems.  General function theory belongs elsewhere.

Let `f : X -> Y`, `g : Y -> Z`, `A subset X`, `B C subset Y`, and
`D subset Z`.

### preimage_id

Exists: N (no current LRA Lean theorem declaration found.)

For every subset `A subset X`,

```text
preimage id A = A.
```

### preimage_comp

Exists: N (no current LRA Lean theorem declaration found.)

For every subset `D subset Z`,

```text
preimage (g composed_with f) D =
  preimage f (preimage g D).
```

Equivalently, for every `x in X`,

```text
x in preimage (g composed_with f) D
iff
x in preimage f (preimage g D).
```

### preimage_is_subset_univ

Exists: N (no current LRA Lean theorem declaration found.)

For every subset `B subset Y`,

```text
preimage f B subset X.
```

### preimage_mono

Exists: N (no current LRA Lean theorem declaration found.)

For all subsets `B C subset Y`,

```text
if B subset C, then preimage f B subset preimage f C.
```

### preimage_congr_function

Exists: N (no current LRA Lean theorem declaration found.)

For all functions `f g : X -> Y` and every subset `B subset Y`,

```text
if f = g, then preimage f B = preimage g B.
```

### preimage_congr_set

Exists: N (no current LRA Lean theorem declaration found.)

For every function `f : X -> Y` and all subsets `B C subset Y`,

```text
if B = C, then preimage f B = preimage f C.
```

### preimage_comp_mono

Exists: N (no current LRA Lean theorem declaration found.)

For all subsets `D E subset Z`,

```text
if D subset E, then
  preimage (g composed_with f) D subset preimage (g composed_with f) E.
```

## 11. Image and Preimage Interaction

These are included as tactical comparison facts.  They should not turn this
gate into a general image calculus.

Let `f : X -> Y`, `A B subset X`, and `C subset Y`.

### subset_preimage_image

Exists: N (no current LRA Lean theorem declaration found.)

For every subset `A subset X`,

```text
A subset preimage f (image f A).
```

### image_preimage_subset

Exists: N (no current LRA Lean theorem declaration found.)

For every subset `C subset Y`,

```text
image f (preimage f C) subset C.
```

### image_union

Exists: N (no current LRA Lean theorem declaration found.)

For all subsets `A B subset X`,

```text
image f (A union B) = image f A union image f B.
```

### image_inter_subset

Exists: N (no current LRA Lean theorem declaration found.)

For all subsets `A B subset X`,

```text
image f (A intersection B) subset image f A intersection image f B.
```

### image_preimage_eq_inter_range

Exists: N (no current LRA Lean theorem declaration found.)

For every subset `C subset Y`,

```text
image f (preimage f C) = C intersection range f.
```

### image_preimage_eq_of_subset_range

Exists: N (no current LRA Lean theorem declaration found.)

For every subset `C subset Y`,

```text
if C subset range f, then image f (preimage f C) = C.
```

### preimage_image_eq_of_injective

Exists: N (no current LRA Lean theorem declaration found.)

For every subset `A subset X`,

```text
if f is injective, then preimage f (image f A) = A.
```

## 12. Mixed Manipulation Targets

These are not new laws.  They are proof-drill targets that require several
Gate 1 identities in sequence.

### mixed_diff_union_compl

Exists: N (no current LRA Lean theorem declaration found.)

For all subsets `A B C subset X`,

```text
(A \ B) union (A \ C) = A \ (B intersection C).
```

### mixed_diff_inter_compl

Exists: N (no current LRA Lean theorem declaration found.)

For all subsets `A B C subset X`,

```text
(A \ B) intersection (A \ C) = A \ (B union C).
```

### mixed_preimage_diff_union

Exists: N (no current LRA Lean theorem declaration found.)

For every function `f : X -> Y` and all subsets `B C D subset Y`,

```text
preimage f (B \ (C union D)) =
  (preimage f B \ preimage f C) intersection
  (preimage f B \ preimage f D).
```

### mixed_symm_diff_empty_eq

Exists: N (no current LRA Lean theorem declaration found.)

For all subsets `A B subset X`,

```text
A triangle B = empty iff A subset B and B subset A.
```

## Completion Criterion

Gate 1 is complete when:

- every theorem statement above has a handwritten proof or a deliberate
  handwritten proof stub;
- every theorem statement above has a Lean proof or a deliberate Lean `sorry`
  stub;
- dependencies are recorded so later finite-algebra and sigma-algebra proofs
  can cite these results instead of reproving raw set identities.
