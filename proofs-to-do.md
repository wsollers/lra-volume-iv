# Volume IV - Mathematical Spaces Proofs To Do

Proof-writing order is dependency-first among active TODO proof labels, with the generated knowledge graph order used as the stable tie-breaker.
Use `✅` to record completion after the canonical proof file has both proof bodies populated and validated.

Open proofs to do: 61
Completed in this tracker: 0

1. () `thm:ordered-field-translation-invariant` — **Order Is Translation Invariant**
   > **Statement.**
   > In an ordered field, if
   > \[
   > a<b,
   > \]
   > then for every $c$,
   > \[
   > a+c<b+c.
   > \]

2. () `thm:ordered-field-positive-multiplication-preserves-order` — **Order Is Preserved by Positive Multiplication**
   > **Statement.**
   > In an ordered field, if
   > \[
   > a<b
   > \quad\text{and}\quad
   > c>0,
   > \]
   > then
   > \[
   > ac<bc.
   > \]

3. () `thm:ordered-field-negative-multiplication-reverses-order` — **Order Is Reversed by Negative Multiplication**
   > **Statement.**
   > In an ordered field, if
   > \[
   > a<b
   > \quad\text{and}\quad
   > c<0,
   > \]
   > then
   > \[
   > bc<ac.
   > \]

4. () `thm:ordered-field-positive-reciprocals` — **Positive Elements Have Positive Reciprocals**
   > **Statement.**
   > In an ordered field, if
   > \[
   > a>0,
   > \]
   > then
   > \[
   > a^{-1}>0.
   > \]

5. () `thm:ordered-field-negative-reciprocals` — **Negative Elements Have Negative Reciprocals**
   > **Statement.**
   > In an ordered field, if
   > \[
   > a<0,
   > \]
   > then
   > \[
   > a^{-1}<0.
   > \]

6. () `thm:ordered-field-squares-nonnegative` — **Squares Are Nonnegative**
   > **Statement.**
   > In an ordered field, for every $x$,
   > \[
   > x^2\ge 0.
   > \]

7. () `thm:ordered-field-one-positive` — **One Is Positive**
   > **Statement.**
   > In an ordered field,
   > \[
   > 1>0.
   > \]

8. () `thm:ordered-field-no-square-root-negative-one` — **No Ordered Field Has Square Root of Negative One**
   > **Statement.**
   > In an ordered field, there is no $x$ such that
   > \[
   > x^2=-1.
   > \]

9. () `lem:ordered-field-product-sign-laws` — **Product Sign Laws in an Ordered Field**
   > **Statement.**
   > In an ordered field, the usual product sign laws hold:
   > \[
   > (+)(+)=(+),\qquad (-)(-)=(+),\qquad (+)(-)=(-),\qquad (-)(+) = (-).
   > \]

10. () `lem:ordered-field-division-order-laws` — **Division Order Laws in an Ordered Field**
   > **Statement.**
   > In an ordered field, division by a positive element preserves order and
   > division by a negative element reverses order.

11. () `lem:metric-key-local-ball` — **Key Local Ball Lemma**
   > **Statement.**
   > Let \((X,d)\) be a metric space. If \(y\in B_d(x;r)\), then
   > \[
   >  B_d(y;r-d(x,y))\subseteq B_d(x;r).
   > \]

12. () `thm:metric-ball-nesting` — **Ball Nesting**
   > **Statement.**
   > Let \((X,d)\) be a metric space, let \(x\in X\), and let \(0<r\leq s\).
   > Then
   > \[
   >  B_d(x;r)\subseteq B_d(x;s).
   > \]
   > If \(r<s\), then also
   > \[
   >  \overline{B}_d(x;r)\subseteq B_d(x;s).
   > \]

13. () `thm:metric-ball-containment-by-center-distance` — **Ball Containment by Center Distance**
   > **Statement.**
   > Let \((X,d)\) be a metric space, let \(x,y\in X\), and let \(r,s>0\).
   >
   > If
   > \[
   >  d(x,y)+r\leq s,
   > \]
   > then
   > \[
   >  B_d(x;r)\subseteq B_d(y;s).
   > \]
   > If
   > \[
   >  d(x,y)+r<s,
   > \]
   > then
   > \[
   >  \overline{B}_d(x;r)\subseteq B_d(y;s).
   > \]

14. () `thm:metric-intersecting-balls-center-distance-bound` — **Intersecting Balls Imply Center-Distance Bound**
   > **Statement.**
   > Let \((X,d)\) be a metric space, let \(x,y\in X\), and let \(r,s>0\). If
   > \[
   >  B_d(x;r)\cap B_d(y;s)\neq\varnothing,
   > \]
   > then
   > \[
   >  d(x,y)<r+s.
   > \]

15. () `thm:metric-closed-balls-contain-open-balls` — **Closed Balls Contain Open Balls**
   > **Statement.**
   > Let \((X,d)\) be a metric space. For every \(x\in X\) and every \(r>0\),
   > \[
   >  B_d(x;r)\subseteq \overline{B}_d(x;r).
   > \]

16. () `thm:metric-distance-to-union` — **Distance to a Union**
   > **Statement.**
   > Let \((X,d)\) be a metric space, let \(x\in X\), and let \(A,B\subseteq X\)
   > be nonempty. Then
   > \[
   >  d(x,A\cup B)=\min\{d(x,A),d(x,B)\}.
   > \]

17. () `thm:metric-distance-to-intersection-bound` — **Distance to an Intersection Bound**
   > **Statement.**
   > Let \((X,d)\) be a metric space, let \(x\in X\), and let
   > \(A,B\subseteq X\) have nonempty intersection. Then
   > \[
   >  d(x,A\cap B)\geq \max\{d(x,A),d(x,B)\}.
   > \]

18. () `thm:metric-equivalent-boundedness-criterion` — **Equivalent Boundedness Criterion**
   > **Statement.**
   > Let \((X,d)\) be a metric space and let \(A\subseteq X\). Then \(A\) is
   > bounded if and only if there exist \(x\in X\) and \(R>0\) such that
   > \[
   >  d(x,a)<R
   > \]
   > for every \(a\in A\).

19. () `thm:metric-bounded-center-independence` — **Center Independence**
   > **Statement.**
   > Let \((X,d)\) be a metric space. If \(A\subseteq X\) and there exist
   > \(x\in X\) and \(R>0\) such that \(d(x,a)\leq R\) for every \(a\in A\), then
   > for every \(y\in X\),
   > \[
   >  d(y,a)\leq R+d(x,y)
   > \]
   > for every \(a\in A\). Thus boundedness does not depend on the chosen center.

20. () `thm:metric-subsets-bounded-sets-bounded` — **Subsets of Bounded Sets Are Bounded**
   > **Statement.**
   > Let \((X,d)\) be a metric space. If \(A\subseteq B\subseteq X\) and \(B\) is
   > bounded, then \(A\) is bounded.

21. () `thm:metric-finite-sets-bounded` — **Finite Sets Are Bounded**
   > **Statement.**
   > Every finite subset of a metric space is bounded.

22. () `thm:metric-finite-unions-bounded-sets-bounded` — **Finite Unions of Bounded Sets Are Bounded**
   > **Statement.**
   > Let \((X,d)\) be a metric space, let \(n\in\mathbb{N}\), and let
   > \(A_1,\ldots,A_n\subseteq X\). If \(A_1,\ldots,A_n\) are bounded, then
   > \[
   >  \bigcup_{k=1}^n A_k
   > \]
   > is bounded.

23. () `thm:metric-boundedness-via-diameter` — **Boundedness via Diameter**
   > **Statement.**
   > Let \((X,d)\) be a metric space and let \(A\subseteq X\) be nonempty. Then
   > \(A\) is bounded if and only if there exists \(C>0\) such that
   > \[
   >  d(a,b)\leq C
   > \]
   > for all \(a,b\in A\).

24. () `thm:metric-closure-bounded-set-bounded` — **Closure of a Bounded Set Is Bounded**
   > **Statement.**
   > Let \((X,d)\) be a metric space. If \(A\subseteq X\) is bounded, then
   > \(\operatorname{cl}(A)\) is bounded.

25. () `thm:metric-compact-sets-bounded` — **Compact Sets Are Bounded**
   > **Statement.**
   > Every compact subset of a metric space is bounded.

26. () `thm:metric-totally-bounded-sets-bounded` — **Totally Bounded Sets Are Bounded**
   > **Statement.**
   > Every totally bounded subset of a metric space is bounded.

27. () `lem:metrics-are-pseudo-metrics` — **Metrics are Pseudo-Metrics**
   > **Statement.**
   > Every metric on a nonempty set \(X\) is a pseudo-metric on \(X\).
   > The converse is false: there exist pseudo-metrics that are not metrics.

28. () `thm:metric-closed-sets-contain-limit-points` — **Closed Sets Contain Their Limit Points**
   > **Statement.**
   > Let \(X\) be a metric space and let \(E\subseteq X\). Then \(E\) is closed if
   > and only if \(E'\subseteq E\).

29. () `thm:metric-limit-point-sequential-characterization` — **Sequential Characterization of Limit Points**
   > **Statement.**
   > Let \((X,d)\) be a metric space, let \(E\subseteq X\), and let \(x\in X\).
   > Then \(x\in E'\) if and only if there exists a sequence of distinct terms in
   > \(E\) that converges to \(x\).

30. () `cor:metric-limit-point-neighborhood-characterization` — **Neighborhood Characterization of Limit Points**
   > **Statement.**
   > Let \((X,d)\) be a metric space, let \(E\subseteq X\), and let \(x\in X\).
   > Then \(x\in E'\) if and only if every neighborhood of \(x\) contains
   > infinitely many points of \(E\).

31. () `thm:cauchy-schwarz-inequality` — **Cauchy--Schwarz Inequality**
   > **Statement.**
   > For every \(x,y\in\mathbb{R}^n\),
   > \[
   >  |x\cdot y|\leq |x|\,|y|.
   > \]
   > Equality holds if and only if \(x\) and \(y\) are linearly dependent.

32. () `cor:minkowski-inequality-rn` — **Minkowski's Inequality**
   > **Statement.**
   > For every \(x,y\in\mathbb{R}^n\),
   > \[
   >  |x+y|\leq |x|+|y|.
   > \]

33. () `cor:euclidean-metric` — **Euclidean Metric**
   > **Statement.**
   > For every \(x,y\in\mathbb{R}^n\), define
   > \[
   >  d_2(x,y):=\sqrt{|x_1-y_1|^2+\cdots+|x_n-y_n|^2}.
   > \]
   > Then \((\mathbb{R}^n,d_2)\) is a metric space.

34. () `thm:metric-euclidean-bolzano-weierstrass` — **Bolzano--Weierstrass in \(\mathbb{R}^m\)**
   > **Statement.**
   > Every bounded sequence in \(\mathbb{R}^m\) contains a subsequence that
   > converges in \(\mathbb{R}^m\).

35. () `thm:metric-bolzano-weierstrass-bounded-infinite-subsets` — **Bolzano--Weierstrass for Bounded Infinite Subsets**
   > **Statement.**
   > Every bounded infinite subset of \(\mathbb{R}^m\) has a limit point in
   > \(\mathbb{R}^m\).

36. () `prop:metric-derived-set-closed` — **The Derived Set is Closed**
   > **Statement.**
   > The set of limit points of any set is closed.

37. () `thm:norm-induces-metric` — **A Norm Induces a Metric**
   > **Statement.**
   > Let \(V\) be a real vector space and let \(\|\cdot\|\) be a norm on \(V\).
   > Define
   > \[
   >  d_{\|\cdot\|}:V\times V\to\mathbb{R}_{\geq 0},
   >  \qquad
   >  d_{\|\cdot\|}(x,y):=\|x-y\|.
   > \]
   > Then \(d_{\|\cdot\|}\) is a metric on \(V\).

38. () `prop:discrete-metric-space` — **The Discrete Distance is a Metric**
   > **Statement.**
   > For every nonempty set \(X\), the discrete distance
   > \(d_{\mathrm{disc}}\) is a metric on \(X\).

39. () `prop:real-line-euclidean-distance-metric` — **The Real-Line Euclidean Distance is a Metric**
   > **Statement.**
   > The function \(d_{\mathbb{R}}(x,y)=|x-y|\) is a metric on \(\mathbb{R}\).

40. () `prop:euclidean-distance-rn-metric` — **The Euclidean Distance on \(\mathbb{R}^n\) is a Metric**
   > **Statement.**
   > The function \(d_2\) is a metric on \(\mathbb{R}^n\).

41. () `prop:taxicab-metric-rn` — **Taxicab Metric**
   > **Statement.**
   > The function \(d_1\) is a metric on \(\mathbb{R}^n\).

42. () `thm:lp-metric-rn` — **\(d_p\) is a Metric**
   > **Statement.**
   > For every \(1\leq p<\infty\), the function \(d_p\) is a metric on
   > \(\mathbb{R}^n\).

43. () `prop:complex-plane-metric-space` — **The Complex Plane is a Metric Space**
   > **Statement.**
   > The pair \((\mathbb{C},d_{\mathbb{C}})\) is a metric space.

44. () `prop:bounded-real-sequence-space-sup-metric` — **The Supremum Distance on Bounded Sequences is a Metric**
   > **Statement.**
   > The function \(d_\infty\) is a metric on \(\ell^\infty(\mathbb{R})\).

45. () `thm:metric-point-functions-identify-points` — **Point Functions Identify Points**
   > **Statement.**
   > Let \((X,d)\) be a metric space. The map
   > \[
   >  X\to\delta(X),
   >  \qquad
   >  z\mapsto\delta_z
   > \]
   > is a bijection.

46. () `thm:metric-point-function-inequalities` — **Point Function Inequalities**
   > **Statement.**
   > Let \((X,d)\) be a nonempty metric space and let \(z\in X\). Then, for all
   > \(a,b\in X\),
   > \[
   >  \delta_z(b)-\delta_z(a)\leq d(a,b)\leq \delta_z(b)+\delta_z(a),
   > \]
   > and
   > \[
   >  \delta_z(z)=0.
   > \]

47. () `thm:metric-pointlike-zero-point-function` — **Pointlike Functions with a Zero Are Point Functions**
   > **Statement.**
   > Let \((X,d)\) be a metric space and let \(u:X\to\mathbb{R}_{\geq 0}\). Then
   > \(u\in\delta(X)\) if and only if \(u\) is pointlike on \(X\) and
   > \[
   >  0\in u(X).
   > \]
   > In that case, there is a unique \(w\in X\) such that \(u(w)=0\), and
   > \[
   >  u=\delta_w.
   > \]

48. () `thm:metric-open-balls-are-open` — **Open Balls are Open**
   > **Statement.**
   > Let \((X,d)\) be a metric space. For every \(x\in X\) and every \(r>0\),
   > the open ball \(B_d(x;r)\) is open in \((X,d)\).

49. () `thm:metric-open-set-closure-properties` — **Metric Open Set Closure Properties**
   > **Statement.**
   > Let \(X\) be a metric space. Then:
   > - the empty set \(\varnothing\) and the space \(X\) are open sets;
   > - an arbitrary union of open subsets of \(X\) is open;
   > - any finite intersection of open subsets of \(X\) is open.

50. () `thm:metric-complement-closed-ball-open` — **Complement of a Closed Ball Is Open**
   > **Statement.**
   > Let \((X,d)\) be a metric space. For every \(x\in X\) and every \(r\geq 0\),
   > \[
   >  X\setminus \overline{B}_d(x;r)
   >  =
   >  \{\,y\in X:d(x,y)>r\,\}
   > \]
   > is open.

51. () `thm:metric-closed-balls-are-closed` — **Closed Balls Are Closed**
   > **Statement.**
   > Let \((X,d)\) be a metric space. For every \(x\in X\) and every \(r\geq 0\),
   > the closed ball
   > \[
   >  \overline{B}_d(x;r)=\{\,y\in X:d(x,y)\leq r\,\}
   > \]
   > is closed.

52. () `thm:metric-closure-open-ball-contained-closed-ball` — **Closure of an Open Ball Is Contained in the Closed Ball**
   > **Statement.**
   > Let \((X,d)\) be a metric space. For every \(x\in X\) and every \(r>0\),
   > \[
   >  \operatorname{cl}\bigl(B_d(x;r)\bigr)\subseteq \overline{B}_d(x;r).
   > \]

53. () `thm:metric-interior-largest-open-subset` — **Interior is the Largest Open Subset**
   > **Statement.**
   > Let \(E\) be a subset of a metric space \(X\). Then \(E^\circ\) is the
   > largest open subset of \(X\) contained in \(E\). In other words:
   > - \(E^\circ\subseteq E\);
   > - \(E^\circ\) is open;
   > - \(E^\circ\supseteq O\), for every open set \(O\subseteq E\).

54. () `thm:metric-neighborhood-criterion-sequential-convergence` — **Metric Neighborhood Criterion for Sequential Convergence**
   > **Statement.**
   > Let \((X,d)\) be a metric space, let \(\{x_n\}\) be a sequence in \(X\), and
   > let \(x\in X\). Then
   > \[
   >  x_n\to x
   > \]
   > if and only if every neighborhood of \(x\) contains all but finitely many terms
   > of \(\{x_n\}\).

55. () `thm:metric-convergent-sequences-unique-limits` — **Metric Convergent Sequences Have Unique Limits**
   > **Statement.**
   > In metric spaces, convergent sequences have unique limits.

56. () `thm:metric-cauchy-sequence-convergent-subsequence` — **Metric Cauchy Sequence with Convergent Subsequence**
   > **Statement.**
   > Let \(\{x_n\}\) be a Cauchy sequence in a metric space \((X,d)\), let
   > \(x\in X\), and let \(\{x_{n_k}\}\) be a subsequence of \(\{x_n\}\) such that
   > \[
   >  \lim_{k\to\infty}x_{n_k}=x.
   > \]
   > Then \(x_n\to x\).

57. () `thm:metric-euclidean-coordinatewise-sequences` — **Coordinatewise Sequences in \(\mathbb{R}^m\)**
   > **Statement.**
   > Let \(\{x_n\}\) be a sequence in \(\mathbb{R}^m\), and let
   > \(x_0\in\mathbb{R}^m\). Write
   > \[
   >  x_n=\bigl(x_n^{(1)},\ldots,x_n^{(m)}\bigr)
   >  \qquad\text{for all } n\in\mathbb{N}\cup\{0\}.
   > \]
   > Then:
   > - \(x_n\to x_0\) if and only if
   >  \(x_n^{(j)}\to x_0^{(j)}\) for every \(j=1,\ldots,m\).
   > - \(\{x_n\}\) is Cauchy if and only if
   >  \(\{x_n^{(j)}\}\) is Cauchy for every \(j=1,\ldots,m\).

58. () `thm:metric-euclidean-cauchy-sequences-converge` — **Euclidean Cauchy Sequences Converge**
   > **Statement.**
   > Every Cauchy sequence in \(\mathbb{R}^m\) is convergent in \(\mathbb{R}^m\).

59. () `prop:topological-basis-pointwise-characterization` — **Pointwise Characterization of a Basis**
   > **Statement.**
   > Let \((X,\tau)\) be a topological space, and let
   > \(\mathcal{B}\subseteq\tau\). Then \(\mathcal{B}\) is a basis for \(\tau\)
   > if and only if for every open set \(O\in\tau\) and every \(x\in O\), there is
   > \(B\in\mathcal{B}\) such that
   > \[
   >  x\in B\subseteq O.
   > \]
   > Consequently, a subset \(A\subseteq X\) is open if and only if for each
   > \(x\in A\), there is \(B\in\mathcal{B}\) such that
   > \[
   >  x\in B\subseteq A.
   > \]

60. () `thm:closed-set-characterization-topologies` — **Closed-Set Characterization of Topologies**
   > **Statement.**
   > Let \(X\) be a set, and let \(\mathcal{C}\) be a collection of subsets of
   > \(X\). Suppose that:
   > - \(\emptyset\in\mathcal{C}\) and \(X\in\mathcal{C}\);
   > - the intersection of any family of elements of \(\mathcal{C}\) belongs
   >  to \(\mathcal{C}\);
   > - the union of any two elements of \(\mathcal{C}\) belongs to
   >  \(\mathcal{C}\).
   > Then there is a unique topology \(\tau\) on \(X\) whose family of closed sets
   > is exactly \(\mathcal{C}\).

61. () `thm:sigma-intersection` — **Intersection of $\sigma$-algebras is a $\sigma$-algebra**
   > **Statement.**
   > Let $\{\mathcal{M}_\alpha\}_{\alpha \in I}$ be any family of $\sigma$-algebras
   > on $X$ (indexed by any set $I$). Then
   > \[
   > \mathcal{M} \;:=\; \bigcap_{\alpha \in I} \mathcal{M}_\alpha
   > \]
   > is a $\sigma$-algebra on $X$.
