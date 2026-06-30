# Volume IV - Mathematical Spaces Proofs To Do

Proof-writing order is dependency-first among active TODO proof labels, with the generated knowledge graph order used as the stable tie-breaker.
Use `✅` to record completion after the canonical proof file has both proof bodies populated and validated.

Open proofs to do: 29
Completed in this tracker: 0

1. () `lem:self-additive-inverse` — **Self Additive Inverse**
   > **Statement.**
   > In any Boolean ring $R$,
   > \[
   > p + p = 0 \qquad \text{for all } p \in R.
   > \]

2. () `lem:self-negation` — **Self Negation**
   > **Statement.**
   > In any Boolean ring $R$,
   > \[
   > -p = p \qquad \text{for all } p \in R.
   > \]

3. () `lem:metrics-are-pseudo-metrics` — **Metrics are Pseudo-Metrics**
   > **Statement.**
   > Every metric on a nonempty set \(X\) is a pseudo-metric on \(X\).
   > The converse is false: there exist pseudo-metrics that are not metrics.

4. () `thm:metric-closed-sets-contain-limit-points` — **Closed Sets Contain Their Limit Points**
   > **Statement.**
   > Let \(X\) be a metric space and let \(E\subseteq X\).  Then \(E\) is closed if
   > and only if \(E'\subseteq E\).

5. () `thm:metric-limit-point-sequential-characterization` — **Sequential Characterization of Limit Points**
   > **Statement.**
   > Let \((X,d)\) be a metric space, let \(E\subseteq X\), and let \(x\in X\).
   > Then \(x\in E'\) if and only if there exists a sequence of distinct terms in
   > \(E\) that converges to \(x\).

6. () `cor:metric-limit-point-neighborhood-characterization` — **Neighborhood Characterization of Limit Points**
   > **Statement.**
   > Let \((X,d)\) be a metric space, let \(E\subseteq X\), and let \(x\in X\).
   > Then \(x\in E'\) if and only if every neighborhood of \(x\) contains
   > infinitely many points of \(E\).

7. () `prop:metric-derived-set-closed` — **The Derived Set is Closed**
   > **Statement.**
   > The set of limit points of any set is closed.

8. () `thm:norm-induces-metric` — **A Norm Induces a Metric**
   > **Statement.**
   > Let \(V\) be a real vector space and let \(\|\cdot\|\) be a norm on \(V\).
   > Define
   > \[
   >   d_{\|\cdot\|}(x,y):=\|x-y\|.
   > \]
   > Then \(d_{\|\cdot\|}\) is a metric on \(V\).

9. () `prop:discrete-metric-space` — **The Discrete Distance is a Metric**
   > **Statement.**
   > For every nonempty set \(X\), the discrete distance
   > \(d_{\mathrm{disc}}\) is a metric on \(X\).

10. () `prop:real-line-euclidean-distance-metric` — **The Real-Line Euclidean Distance is a Metric**
   > **Statement.**
   > The function \(d_{\mathbb{R}}(x,y)=|x-y|\) is a metric on \(\mathbb{R}\).

11. () `thm:cauchy-schwarz-inequality` — **Cauchy--Schwarz Inequality**
   > **Statement.**
   > For every \(x,y\in\mathbb{R}^n\),
   > \[
   >   |x\cdot y|\leq |x|\,|y|.
   > \]
   > Equality holds if and only if \(x\) and \(y\) are linearly dependent.

12. () `cor:minkowski-inequality-rn` — **Minkowski's Inequality**
   > **Statement.**
   > For every \(x,y\in\mathbb{R}^n\),
   > \[
   >   |x+y|\leq |x|+|y|.
   > \]

13. () `prop:euclidean-distance-rn-metric` — **The Euclidean Distance on \(\mathbb{R}^n\) is a Metric**
   > **Statement.**
   > The function \(d_2\) is a metric on \(\mathbb{R}^n\).

14. () `cor:euclidean-metric` — **Euclidean Metric**
   > **Statement.**
   > For \(x,y\in\mathbb{R}^n\), define
   > \[
   >   d_2(x,y)=\sqrt{\sum_{i=1}^{n}|x_i-y_i|^2}.
   > \]
   > Then \((\mathbb{R}^n,d_2)\) is a metric space.

15. () `prop:taxicab-metric-rn` — **Taxicab Metric**
   > **Statement.**
   > The function \(d_1\) is a metric on \(\mathbb{R}^n\).

16. () `thm:lp-metric-rn` — **\(d_p\) is a Metric**
   > **Statement.**
   > For every \(1\leq p<\infty\), the function \(d_p\) is a metric on
   > \(\mathbb{R}^n\).

17. () `prop:complex-plane-metric-space` — **The Complex Plane is a Metric Space**
   > **Statement.**
   > The pair \((\mathbb{C},d_{\mathbb{C}})\) is a metric space.

18. () `prop:bounded-real-sequence-space-sup-metric` — **The Supremum Distance on Bounded Sequences is a Metric**
   > **Statement.**
   > The function \(d_\infty\) is a metric on \(\ell^\infty(\mathbb{R})\).

19. () `thm:metric-open-set-closure-properties` — **Metric Open Set Closure Properties**
   > **Statement.**
   > Let \(X\) be a metric space.  Then the empty set \(\varnothing\) and the space
   > \(X\) are open sets, an arbitrary union of open subsets of \(X\) is open, and
   > any finite intersection of open subsets of \(X\) is open.

20. () `thm:metric-open-balls-are-open` — **Open Balls are Open**
   > **Statement.**
   > Open balls in metric spaces are open sets.

21. () `thm:metric-interior-largest-open-subset` — **Interior is the Largest Open Subset**
   > **Statement.**
   > Let \(E\) be a subset of a metric space \(X\).  Then \(E^\circ\) is the
   > largest open subset of \(X\) contained in \(E\).

22. () `thm:metric-neighborhood-criterion-sequential-convergence` — **Metric Neighborhood Criterion for Sequential Convergence**
   > **Statement.**
   > Let \((X,d)\) be a metric space, let \(\{x_n\}\) be a sequence in \(X\), and
   > let \(x\in X\).  Then \(x_n\to x\) if and only if every neighborhood of \(x\)
   > contains all but finitely many terms of \(\{x_n\}\).

23. () `thm:metric-convergent-sequences-unique-limits` — **Metric Convergent Sequences Have Unique Limits**
   > **Statement.**
   > In metric spaces, convergent sequences have unique limits.

24. () `thm:metric-cauchy-sequence-convergent-subsequence` — **Metric Cauchy Sequence with Convergent Subsequence**
   > **Statement.**
   > Let \(\{x_n\}\) be a Cauchy sequence in a metric space \((X,d)\), let
   > \(x\in X\), and let \(\{x_{n_k}\}\) be a subsequence of \(\{x_n\}\) such that
   > \(\lim_{k\to\infty}x_{n_k}=x\).  Then \(x_n\to x\).

25. () `thm:metric-euclidean-coordinatewise-sequences` — **Coordinatewise Sequences in \(\mathbb{R}^m\)**
   > **Statement.**
   > Let \(\{x_n\}\) be a sequence in \(\mathbb{R}^m\), and let
   > \(x_0\in\mathbb{R}^m\).  Write
   > \[
   >   x_n=\bigl(x_n^{(1)},\ldots,x_n^{(m)}\bigr)
   >   \qquad\text{for all } n\in\mathbb{N}\cup\{0\}.
   > \]
   > Then \(x_n\to x_0\) if and only if \(x_n^{(j)}\to x_0^{(j)}\) for every
   > \(j=1,\ldots,m\), and \(\{x_n\}\) is Cauchy if and only if
   > \(\{x_n^{(j)}\}\) is Cauchy for every \(j=1,\ldots,m\).

26. () `thm:metric-euclidean-cauchy-sequences-converge` — **Euclidean Cauchy Sequences Converge**
   > **Statement.**
   > Every Cauchy sequence in \(\mathbb{R}^m\) is convergent in \(\mathbb{R}^m\).

27. () `thm:metric-euclidean-bolzano-weierstrass` — **Bolzano--Weierstrass in \(\mathbb{R}^m\)**
   > **Statement.**
   > Every bounded sequence in \(\mathbb{R}^m\) contains a subsequence that
   > converges in \(\mathbb{R}^m\).

28. () `thm:metric-bolzano-weierstrass-bounded-infinite-subsets` — **Bolzano--Weierstrass for Bounded Infinite Subsets**
   > **Statement.**
   > Every bounded infinite subset of \(\mathbb{R}^m\) has a limit point in
   > \(\mathbb{R}^m\).

29. () `thm:sigma-intersection` — **Intersection of \(\sigma\)-Algebras is a \(\sigma\)-Algebra**
   > **Statement.**
   > Let $\{\mathcal{M}_\alpha\}_{\alpha \in I}$ be any family of $\sigma$-algebras
   > on $X$ (indexed by any set $I$). Then
   > \[
   > \mathcal{M} \;:=\; \bigcap_{\alpha \in I} \mathcal{M}_\alpha
   > \]
   > is a $\sigma$-algebra on $X$.
