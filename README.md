# An Endpoint Gradient Bound for the Centered Ball Maximal Operator

The endpoint Sobolev regularity question of Hajłasz and Onninen, in its centered Euclidean-ball formulation, asks for the following estimate.

> [!NOTE]
> **Conjecture (Centered-ball endpoint gradient bound).**
>
> For every integer $d\ge 2$, there exists a finite constant $C_d>0$ such that, for every real-valued $f\in W^{1,1}(\mathbb R^d)$, the centered Hardy-Littlewood maximal function
>
> $$
> Mf(x)=\sup_{r>0}\frac{1}{|B(x,r)|}\int_{B(x,r)}|f(y)|\,dy
> $$
>
> belongs to $W^{1,1}_{\mathrm{loc}}(\mathbb R^d)$ and satisfies
>
> $$
> \int_{\mathbb R^d}|\nabla Mf(x)|\,dx
> \le C_d\int_{\mathbb R^d}|\nabla f(x)|\,dx.
> $$

All balls and vector norms are Euclidean. The constant may depend on the dimension, but is independent of the input function. No radiality or compact-support assumption is imposed on $f$. Global $L^1$ integrability of $Mf$ itself is not part of the assertion.

Reference: P. Hajłasz and J. Onninen, *On boundedness of maximal functions in Sobolev spaces*, Ann. Acad. Sci. Fenn. Math. **29** (2004), 167-176, [Question 1, p. 169](https://sites.pitt.edu/~hajlasz/OriginalPublications/HajlaszO-OnBoundedness-AnnAcadSciFennMath-29-1994-167-176.pdf#page=3).

This repository presents a proposed proof of this conjecture for submission to **Formal Conjectures**. A proof sketch follows; the [PDF manuscript](PDF/centered-ball-maximal-endpoint.pdf) contains the detailed proof.

## Proof sketch

### 1. Reduce to a signed finite-band estimate

For a real-valued smooth compactly supported function $g$, write

$$
A_rg(x)=\frac{1}{|B(x,r)|}\int_{B(x,r)}g(y)\,dy,
\qquad
S_{a,b}g(x)=\sup_{a\le r\le b}A_rg(x).
$$

The intermediate target is

$$
\int_{\mathbb R^d}|\nabla S_{a,2^ma}g|
\le C_d\int_{\mathbb R^d}|\nabla g|,
\qquad a>0,\quad m\ge 0.
$$

The constant must be independent of the number of scales $m$. Retaining signed averages permits the local subtraction of a mean in the final regularity argument.

### 2. Use a real matrix correction to obtain local cancellation

For $a\ne0$, define

$$
T_a(b)=\frac{(a\cdot b)I+ab^{\mathsf T}-ba^{\mathsf T}}{|a|^2}.
$$

This satisfies $T_a(a)=I$ and $\|T_a(b)\|_{\mathrm{op}}=|b|/|a|$. If $h=\nabla g\,dy$ and

$$
H_K=\int K(y)(y-x)\otimes dh(y),
$$

then

$$
\int K(y)T_a(y-x)\,dh(y)
=\frac{(H_K^{\mathsf T}-H_K)a+a\operatorname{tr}H_K}{|a|^2}.
$$

Thus symmetry and zero trace of $H_K$ give cancellation. Balanced radial mixtures near a maximizing radius are designed to satisfy these moment conditions. A shell-concentration lemma and small-cap correction then enter the proposed local directional and size estimates. The local error cost discounts a zero-mass piece of size $s$ and mass $m$ by $s^{1/100}m$.

### 3. Sum refinement defects and control changes of direction

Positive refinement of a tensor-product hat partition decomposes the gradient measure into directional residuals and localized zero-mass errors. The scalar cancellation defects telescope, and their discounted costs sum to at most a dimension-dependent multiple of

$$
V=\int_{\mathbb R^d}|\nabla g|.
$$

A dimension-dependent simplex frame and finite set of directions replace the planar direction construction. A finite-state probability law organizes successive scales into runs with a common direction. The proposed packing estimate controls switching probabilities and spatial derivatives of that law using the same budget $C_dV$.

Two points are essential: the spatial supremum on each cell must be bounded before summing, and costs from histories before a particle's birth must also be included. The manuscript addresses both explicitly; pointwise packing alone would not justify the assembly.

### 4. Assemble the bands by cancelling completed histories

Each label history partitions the radius scales into constant-direction runs. At differentiability points, the gradient of a finite-band envelope agrees with the gradient of any attaining average, because that average touches the envelope from below.

After averaging over label histories, the directional terms are handled by weighted integration by parts. For each derivative of a transition probability, the potential of the completed prefix is subtracted **before taking absolute values**. The identity that each probability row sums to one cancels that prefix. The remaining differences are controlled by small-radius value oscillations.

Combining the local estimates, the telescoping error budget, and the packing bound is intended to give the signed finite-band estimate with a constant independent of the number of scales.

### 5. Pass to Sobolev inputs and eliminate singular variation

Smooth approximation first extends the signed estimate to $W^{1,1}$ inputs on each fixed band. For $g=|f|$, the envelopes $S_{2^{-N},2^N}g$ increase to $Mf$ and converge locally in $L^1$. Lower semicontinuity gives a finite distributional gradient measure with the desired total-variation bound.

**A bounded-variation limit alone does not give the required Sobolev conclusion.** The proposed final step localizes near a compact null set, subtracts local means using a cutoff, and applies the signed estimate together with Poincaré's inequality. Large radii are controlled by a Lipschitz bound. Shrinking the neighborhood and then the radius cutoff is intended to show that the gradient measure vanishes on every null set. Its Radon-Nikodym density would then be the required integrable weak gradient.

## Detailed manuscript

- [PDF manuscript](PDF/centered-ball-maximal-endpoint.pdf)

Public draft 1, 8 October 2026.
