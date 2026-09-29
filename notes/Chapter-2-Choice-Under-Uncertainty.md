# Chapter 2 — Choice Under Uncertainty

*PPHA 44100 Advanced Microeconomics, Zhaosong Ruan (Harris), 65-slide lecture notes*

## Simple and Compound Lotteries

Let $X$ be the set of all possible consequences. A lottery is a probability measure on $X$. A **simple lottery** $p((p_i);(x_i))$ is a lottery with countable support, where each $p_i$ is the probability that consequence $x_i$ is realized. A lottery that gives consequence $x$ with probability 1 is **degenerate at $x$**, denoted $\delta_x$. The set of all simple lotteries on $X$ is denoted $\mathcal{L}(X)$.

Let $\mathrm{supp}(p)$ be the support of lottery $p$. For two simple lotteries $p$ and $q$ and any number $\alpha \in [0,1]$, a **compound lottery** $\alpha p \oplus (1-\alpha)q$ is defined as follows: for any $z \in \mathrm{supp}\,p \cup \mathrm{supp}\,q$, the compound lottery gives $z$ with probability $\alpha p_z + (1-\alpha) q_z$.

---

## Axioms on Preferences over Lotteries

The decision maker (DM) now has preferences $\succsim$ on $\mathcal{L}(X)$. As in Chapter 1, representing these preferences with a utility function requires $\succsim$ to be complete, transitive, and continuous — plus a fourth axiom specific to lotteries.

**Continuity (mixture form):** $\succsim$ on $\mathcal{L}(X)$ is continuous if for any $p \succ q \succ r$, there exists an $\alpha \in [0,1]$ such that $q \sim \alpha p \oplus (1-\alpha) r$.

**Independence axiom:** $\succsim$ satisfies independence if
$$p \succsim q \iff \text{for all } \alpha \in [0,1] \text{ and all } r \in \mathcal{L}(X),\ \alpha p \oplus (1-\alpha) r \succsim \alpha q \oplus (1-\alpha) r$$

Intuition: if two lotteries agree with some probability, then the preference between them only depends on what happens when they disagree.

**Lemma 2.1:** Suppose $\succsim$ on $\mathcal{L}(X)$ satisfies independence, and $\delta_x \succ \delta_y$. Then for any $1 \geq \alpha > \beta \geq 0$,
$$\alpha \delta_x \oplus (1-\alpha) \delta_y \succ \beta \delta_x \oplus (1-\beta) \delta_y$$

---

## The Allais Paradox (Is Independence Plausible?)

Consider two choices. First: $L_1$ gives $3000$ with probability 1; $L_2$ gives $4000$ with probability 0.8 and $0$ with probability 0.2. Second: $L_3$ gives $3000$ with probability 0.25 and $0$ with probability 0.75; $L_4$ gives $4000$ with probability 0.2 and $0$ with probability 0.8.

Note that $L_3 = 0.25 L_1 \oplus 0.75 \delta_0$ and $L_4 = 0.25 L_2 \oplus 0.75 \delta_0$. So by the independence axiom, $L_1 \succsim L_2 \iff L_3 \succsim L_4$. Many people choose $L_1 \succ L_2$ but $L_4 \succ L_3$, violating independence — this is the Allais paradox.

---

## The von Neumann–Morgenstern Theorem

**Theorem 2.1 (VNM utility theorem):** Suppose $\succsim$ on $\mathcal{L}(X)$ satisfies completeness, transitivity, continuity, and independence. Then there exists a function $u : X \to \mathbb{R}$ such that
$$p \succsim q \iff \sum_x p_x u(x) \geq \sum_x q_x u(x)$$
The function $u$ is called a **Bernoulli utility function**. Conversely, the preferences of a DM acting to maximize the expectation of a function $u$ satisfy completeness, transitivity, continuity, and independence.

**Theorem 2.2 (uniqueness up to positive affine transformation):** Suppose $u$ and $v$ are two Bernoulli utility functions whose expected values represent the same preferences $\succsim$. Then there are numbers $a > 0$ and $b$ such that
$$v(x) = a u(x) + b \quad \text{for all } x \in X$$

---

## Difficulties and Extensions

Caring about consequences differently depending on other random factors that determine outcomes. Example: it rains with probability 50%. Compare (a) you receive an umbrella exactly when it rains, and (b) you receive an umbrella exactly when it does not rain. Resolution: redefine consequences, or introduce state-dependency.

Subjective probability (Ellsberg paradox): draw a ball from one of two urns. The first has 50 red and 50 black balls; the second has 100 balls with an unknown mix. You win if you draw red — which urn? You win if you draw black — which urn? People who pick urn 1 in both cases contradict any single subjective probability assignment.

---

## Risk Aversion

For any lottery $p$, its expected value is $\mathbb{E}p = \sum_x x p_x$. A DM is:

- **Risk averse** if for any lottery $p$, $\delta_{\mathbb{E}p} \succsim p$
- **Risk neutral** if for any lottery $p$, $\delta_{\mathbb{E}p} \sim p$
- **Risk loving** if for any lottery $p$, $p \succsim \delta_{\mathbb{E}p}$

**Jensen's inequality:** Let $u$ be a concave function on $\mathbb{R}$, and $p$ a lottery with finite expected value $\mathbb{E}p$. Then
$$u(\mathbb{E}p) \geq \sum_x u(x) p_x$$
So risk aversion corresponds to concavity of the Bernoulli utility function.

---

## Example: Insurance Demand

A consumer has initial income $Y$. With probability $\pi$ she suffers a loss $L$. An insurance company offers insurance at price $P$: if she pays $\alpha P$ with $\alpha \in [0,1]$, the company pays $\alpha L$ in the event of the loss. She maximizes the expectation of a strictly increasing and concave Bernoulli utility function $u$:
$$\max_\alpha\ (1-\pi) u(Y - \alpha P) + \pi u(Y - \alpha P - L + \alpha L)$$

First-order condition:
$$-(1-\pi) P u'(Y - \alpha P) + \pi (L - P) u'(Y - \alpha P - (1-\alpha)L) = 0$$

**Actuarially fair insurance:** the expected payout equals the premium, $\pi L = P$. Then the FOC simplifies to $u'(Y - \alpha P) = u'(Y - \alpha P - (1-\alpha)L)$, and strict concavity of $u$ implies $\alpha = 1$ (full insurance).

If the insurance is actuarially unfair, i.e. $P > \pi L$, the FOC at $\alpha = 1$ becomes
$$-(1-\pi) P u'(Y - P) + \pi (L - P) u'(Y - P) = (\pi L - P) u'(Y - P) < 0$$
so the optimal $\alpha < 1$.

**Proposition 2.1:** Suppose the consumer is strictly risk averse with a differentiable Bernoulli utility function. Then she buys full insurance if and only if it is actuarially fair.

Why partial insurance when $P > \pi L$: at full insurance the consumer has fixed income $Y - P$. Reducing coverage by a tiny fraction $\beta$ gives income $Y - P + \beta P$ without loss and $Y - P + \beta P - \beta L$ with loss; expected income is $\mathbb{E}I = Y - P + \beta P - \pi \beta L > Y - P$. For small $\beta$, $u$ is almost linear on $[Y - P + \beta P - \beta L,\ Y - P + \beta P]$, so $\mathbb{E}u(I) \approx u(\mathbb{E}I) > u(Y - P)$ — it pays to cut coverage at least a little.

---

## Certainty Equivalent, Risk Premium, and Arrow–Pratt

**Definition:** Let $p$ be a lottery. If $x$ is a sure consequence such that $\delta_x \sim p$, then $x$ is the **certainty equivalent** of $p$, denoted $C(p)$. The **risk premium** of $p$ is
$$R(p) = \mathbb{E}p - C(p)$$

**Theorem 2.3:** Suppose preferences are represented by the expectation of a continuous, strictly increasing Bernoulli utility function. Then every lottery has exactly one certainty equivalent.

**Approximation of the risk premium:** By definition $u(\mathbb{E}p - R(p)) = \sum_x u(x) p_x$. For small risks, Taylor-expand both sides around $\mathbb{E}p$:
$$u(\mathbb{E}p - R(p)) \approx u(\mathbb{E}p) - u'(\mathbb{E}p) R(p)$$
$$u(x) \approx u(\mathbb{E}p) + u'(\mathbb{E}p)(x - \mathbb{E}p) + \tfrac{1}{2} u''(\mathbb{E}p)(x - \mathbb{E}p)^2$$

Taking expectations of the second line (the first-order term vanishes):
$$\sum_x u(x) p_x \approx u(\mathbb{E}p) + \tfrac{1}{2} u''(\mathbb{E}p) \sum_x (x - \mathbb{E}p)^2 p_x = u(\mathbb{E}p) + \tfrac{1}{2} u''(\mathbb{E}p) \mathrm{var}(p)$$

Equating the two sides and solving:
$$R(p) \approx -\frac{u''(\mathbb{E}p)}{u'(\mathbb{E}p)} \cdot \frac{\mathrm{var}(p)}{2}$$

The quantity $\lambda(x) = -\dfrac{u''(x)}{u'(x)}$ is the **Arrow–Pratt coefficient of absolute risk aversion** at $x$.

---

## Comparing Risk Aversion

**Proposition 2.2:** Suppose $u$ and $v$ are strictly increasing and continuously differentiable. The following are equivalent:

1. $u$ is at least as risk averse as $v$;
2. $C_u(p) \leq C_v(p)$ for every lottery $p$;
3. There is an increasing and concave function $h$ such that $u = h \circ v$;
4. $\lambda_u(x) \geq \lambda_v(x)$ for all $x$.

**Proof sketch, $1 \iff 2$:** negate both. If $u$ is not always as risk averse as $v$, there exist a lottery $p$ and a sure consequence $x$ with $p \succsim_u x$ but $x \succ_v p$. Then
$$\mathbb{E}u(p) \geq u(x) \ \text{but}\ \mathbb{E}v(p) < v(x) \iff u(C_u(p)) \geq u(x) \ \text{but}\ v(C_v(p)) < v(x) \iff C_u(p) \geq x > C_v(p)$$
which negates 2.

**Proof sketch, $2 \iff 3$:** Since $v$ is strictly increasing it has an inverse $v^{-1}$; let $h = u \circ v^{-1}$. Then
$$C_v(p) \geq C_u(p) \iff u(C_v(p)) \geq u(C_u(p)) \iff h \circ v(C_v(p)) \geq \mathbb{E}u(p) \iff h(\mathbb{E}v(p)) \geq \mathbb{E}h(v(p))$$
using $u(C_u(p)) = \mathbb{E}u(p)$ and $v(C_v(p)) = \mathbb{E}v(p)$. By Jensen's inequality, the last line holds for all $p$ if and only if $h$ is concave.

**Proof sketch, $3 \iff 4$:** Differentiate $u(x) = h(v(x))$ to get $u'(x) = h'(v(x)) v'(x)$; log-differentiate again:
$$\frac{u''(x)}{u'(x)} = \frac{h''(v(x))}{h'(v(x))} + \frac{v''(x)}{v'(x)} \implies \lambda_u(x) - \lambda_v(x) = -\frac{h''(v(x))}{h'(v(x))}$$
Hence $\lambda_u(x) \geq \lambda_v(x)$ for all $x$ if and only if $h'' \leq 0$, i.e. $h$ is concave.

---

## Example: Portfolio Choice

A DM with wealth $W > 0$ chooses between a risk-free security with guaranteed return $r > 1$ and a risky security with return $\theta$ distributed according to probability measure $\pi$. She maximizes the expectation of a Bernoulli utility $u$ over final wealth, with $u' > 0$ and $u'' < 0$, investing $\alpha \geq 0$ in the risky asset.

Final wealth is
$$Y = \theta \alpha + r(W - \alpha) = \alpha(\theta - r) + rW$$

The DM's problem and FOC:
$$\max_{\alpha \geq 0}\ \sum_{\theta \in \mathrm{supp}\,\pi} u(\alpha(\theta - r) + rW) \pi_\theta, \qquad \text{FOC: } \sum_{\theta \in \mathrm{supp}\,\pi} (\theta - r) u'(\alpha(\theta - r) + rW) \pi_\theta \leq 0$$

**Special cases:**

- If $\theta > r$ for all $\theta \in \mathrm{supp}\,\pi$: no solution; the DM wants arbitrarily large $\alpha$.
- If the DM is risk neutral, $u'$ is constant and the FOC reduces to $\mathbb{E}\theta - r \leq 0$: $\alpha^* = 0$ if $\mathbb{E}\theta < r$; any $\alpha$ is optimal if $\mathbb{E}\theta = r$; no solution if $\mathbb{E}\theta > r$.
- If $u$ is strictly concave and $\min \mathrm{supp}\,\pi < r < \max \mathrm{supp}\,\pi$, and a solution exists: concavity makes the SOC negative and the solution unique; its character depends on $\mathbb{E}\theta$ vs. $r$.

**If $\mathbb{E}\theta \leq r$:** for any $\theta > \underline{\theta} = \min \mathrm{supp}\,\pi$, concavity gives $u'(\alpha(\theta - r) + rW) < u'(\alpha(\underline{\theta} - r) + rW) = k$, so the FOC satisfies
$$\sum_{\theta} (\theta - r) u'(\alpha(\theta - r) + rW) \pi_\theta < \sum_{\theta} (\theta - r) k \pi_\theta = k(\mathbb{E}\theta - r) \leq 0$$
Hence $\alpha^* = 0$: the risky asset is never held if it offers no additional expected return over the risk-free asset.

**If $\mathbb{E}\theta > r$:** at $\alpha^* = 0$ the FOC equals $u'(rW)(\mathbb{E}\theta - r) > 0$, so $\alpha^* = 0$ cannot be optimal. It is always optimal to accept at least a little risk for additional expected return.

---

## Comparative Statics: More Risk-Averse Agents Invest Less

Assume $\mathbb{E}\theta > r$, so $\alpha^* > 0$. Two DMs have utility functions $u$ and $v$, with $u$ strictly more risk averse than $v$; write $u = h \circ v$ with $h$ increasing and strictly concave. The FOC for $u$ can be rewritten via $u' = (h' \circ v) v'$:
$$\sum_{\theta} (\theta - r) h'(v(\alpha(\theta - r) + rW)) v'(\alpha(\theta - r) + rW) \pi_\theta = 0$$

Intuition: the FOC for $u$ attaches more weight (larger $h'$) to terms where $\theta - r < 0$, so $\alpha_u^* < \alpha_v^*$.

Formally, split the FOC of $v$ at $\alpha_v^*$ into a negative and a positive part:
$$\sum_{\theta < r} (\theta - r) v'(\alpha(\theta - r) + rW) \pi_\theta + \sum_{\theta > r} (\theta - r) v'(\alpha(\theta - r) + rW) \pi_\theta = 0$$

Let $\tilde{\theta} = \max\{\theta \mid \theta < r\}$ and $\hat{\theta} = \min\{\theta \mid \theta > r\}$. Since $h$ is concave, $h'$ is decreasing, so $h'(v(\cdot))$ is largest at the lowest wealth, i.e. at $\tilde{\theta}$ among $\theta < r$ and at $\hat{\theta}$ among $\theta > r$. Hence:
$$\sum_{\theta < r} (\theta - r) h'(v(\cdot)) v'(\cdot) \pi_\theta \leq h'(v(\alpha(\tilde{\theta} - r) + rW)) \sum_{\theta < r} (\theta - r) v'(\cdot) \pi_\theta$$
$$\sum_{\theta > r} (\theta - r) h'(v(\cdot)) v'(\cdot) \pi_\theta \leq h'(v(\alpha(\hat{\theta} - r) + rW)) \sum_{\theta > r} (\theta - r) v'(\cdot) \pi_\theta$$

(Both inequalities go through because the summands' signs match the direction of the $h'$ bounds.) Concavity of $h$ also gives $h'(v(\alpha(\tilde{\theta} - r) + rW)) > h'(v(\alpha(\hat{\theta} - r) + rW))$. Therefore, whenever the FOC of $v$ equals 0,
$$h'(v(\cdot\mid\tilde{\theta})) \sum_{\theta < r} (\theta - r) v'(\cdot) \pi_\theta + h'(v(\cdot\mid\hat{\theta})) \sum_{\theta > r} (\theta - r) v'(\cdot) \pi_\theta < 0$$
so the FOC of $u$ at $\alpha_v^*$ is strictly negative, and $\alpha_u^* < \alpha_v^*$.

---

## First-Order Stochastic Dominance

Consider lotteries that are continuous random variables with a density on $[0, \bar{x}]$.

**Definition:** Lottery $F$ **first-order stochastically dominates (FOSD)** lottery $G$ if every DM with an increasing Bernoulli utility function prefers $F$ to $G$: for all increasing $u$,
$$\int_0^{\bar{x}} u(x) f(x) dx \geq \int_0^{\bar{x}} u(x) g(x) dx$$

**Theorem 2.4:** $F$ FOSD $G$ if and only if $F(x) \leq G(x)$ for all $x$.

**Proof (sufficiency, via integration by parts):** Assume $u$ is continuous and twice differentiable except possibly at finitely many points. Then
$$\int_0^{\bar{x}} u(x)(f(x) - g(x)) dx = \Big[ u(x)(F(x) - G(x)) \Big]_0^{\bar{x}} - \int_0^{\bar{x}} u'(x)(F(x) - G(x)) dx = \int_0^{\bar{x}} u'(x)(G(x) - F(x)) dx$$
The boundary term vanishes because $F(0) = G(0) = 0$ and $F(\bar{x}) = G(\bar{x}) = 1$. The remaining integral is weakly positive if $u'(x) \geq 0$ and $F(x) \leq G(x)$.

**Proof (necessity):** If $F(x_0) > G(x_0)$ for some $x_0$, continuity gives $F > G$ on some interval $(x_0 - \epsilon, x_0 + \epsilon)$. Construct the increasing utility
$$u(x) = \begin{cases} 0 & x \leq x_0 - \epsilon \\ \frac{x - (x_0 - \epsilon)}{2\epsilon} & x_0 - \epsilon < x < x_0 + \epsilon \\ 1 & x \geq x_0 + \epsilon \end{cases} \quad\text{with } u'(x) = \begin{cases} 0 & x < x_0 - \epsilon \\ \frac{1}{2\epsilon} & x_0 - \epsilon < x < x_0 + \epsilon \\ 0 & x > x_0 + \epsilon \end{cases}$$
(except at the two kinks). Then
$$\int_0^{\bar{x}} u'(x)(G(x) - F(x)) dx = \frac{1}{2\epsilon} \int_{x_0 - \epsilon}^{x_0 + \epsilon} (G(x) - F(x)) dx < 0$$
so this increasing DM strictly prefers $G$ — contradicting FOSD. If discontinuous $u$ is allowed, the step utility $u(x) = 0$ for $x \leq x_0$, $u(x) = 1$ for $x > x_0$ gives $\int u f = 1 - F(x_0) < 1 - G(x_0) = \int u g$ directly.

**Intuition:** For any fixed $x^*$, $F(x^*)$ is the probability that $F$ draws $x \leq x^*$. $F(x) > G(x)$ means $F$ is more likely to draw relatively small $x$, hence relatively small $u(x)$. The proof replicates this intuition on $(x_0 - \epsilon, x_0 + \epsilon)$ while making sure the distributions outside the interval do not interfere: by continuity, $F(x_0 - \epsilon) \geq G(x_0 - \epsilon)$ (F weakly more likely to give $u = 0$) and $1 - F(x_0 + \epsilon) \leq 1 - G(x_0 + \epsilon)$ (F weakly less likely to give $u = 1$).

**Examples:** Normal distributions with different means; uniform distributions with different maxima (the one with the higher support point FOSD the other).

---

## Mean-Preserving Spreads and Second-Order Stochastic Dominance

**Definition:** A random variable $Y$ is a **mean-preserving spread (MPS)** of another random variable $X$ if there exists a random variable $Z$ such that
$$Y = X + Z \quad \text{and} \quad \mathbb{E}(Z \mid X) = 0$$

**Theorem 2.5:** Suppose $X$ has distribution $F$ and $Y$ has distribution $G$, with $\mathbb{E}(X) = \mathbb{E}(Y)$. The following are equivalent:

1. $\int_0^{\bar{x}} u(x) f(x) dx \geq \int_0^{\bar{x}} u(x) g(x) dx$ for all concave $u$;
2. $\int_0^{x} F(s) ds \leq \int_0^{x} G(s) ds$ for all $x \in [0, \bar{x}]$;
3. $Y$ is a mean-preserving spread of $X$.

Remarks: sometimes SOSD is defined by statement 2 alone; others require statement 2 plus equal means. Statement 2 by itself implies $\mathbb{E}(X) \geq \mathbb{E}(Y)$.

**Proof sketch, $1 \iff 2$:** Integrate by parts twice. First, as in Theorem 2.4,
$$\int_0^{\bar{x}} u(x)(f(x) - g(x)) dx = \int_0^{\bar{x}} u'(x)(G(x) - F(x)) dx = \Big[ u'(x) \int_0^{x} (G(s) - F(s)) ds \Big]_0^{\bar{x}} - \int_0^{\bar{x}} u''(x) \int_0^{x} (G(s) - F(s)) ds \, dx$$

Using $\mathbb{E}(X) = \bar{x} - \int_0^{\bar{x}} F(x) dx$ (and similarly for $Y$), equal means imply $\int_0^{\bar{x}} F = \int_0^{\bar{x}} G$, so the boundary term vanishes at both $x = \bar{x}$ and $x = 0$. What remains is
$$\int_0^{\bar{x}} u(x)(f(x) - g(x)) dx = \int_0^{\bar{x}} u''(x) \int_0^{x} (F(s) - G(s)) ds \, dx \geq 0 \quad \text{if } u'' \leq 0 \text{ and } \int_0^{x} F \leq \int_0^{x} G \ \forall x$$

**Necessity:** If $\int_0^{x_0} F > \int_0^{x_0} G$ for some $x_0$, continuity gives the strict inequality on some $(x_0 - \epsilon, x_0 + \epsilon)$. Construct the concave utility
$$u(x) = \begin{cases} x & x \leq x_0 - \epsilon \\ -\frac{1}{4\epsilon} x^2 + \frac{x_0 + \epsilon}{2\epsilon} x - \frac{(x_0 - \epsilon)^2}{4\epsilon} & x_0 - \epsilon < x < x_0 + \epsilon \\ x_0 & x > x_0 + \epsilon \end{cases}$$
which has continuous derivative
$$u'(x) = \begin{cases} 1 & x \leq x_0 - \epsilon \\ \frac{x_0 + \epsilon - x}{2\epsilon} & x_0 - \epsilon < x < x_0 + \epsilon \\ 0 & x > x_0 + \epsilon \end{cases} \quad\text{and } u''(x) = \begin{cases} 0 & x \leq x_0 - \epsilon \\ -\frac{1}{2\epsilon} & x_0 - \epsilon < x < x_0 + \epsilon \\ 0 & x > x_0 + \epsilon \end{cases}$$
(except at the two kinks). Then
$$\int_0^{\bar{x}} u(x)(f(x) - g(x)) dx = -\frac{1}{2\epsilon} \int_{x_0 - \epsilon}^{x_0 + \epsilon} \int_0^{x} (F(s) - G(s)) ds \, dx < 0$$
contradicting statement 1. Note $u'$ has the same shape as the $u$ used to prove Theorem 2.4. If a discontinuous $u'$ is allowed, the kinked utility $u(x) = x$ for $x \leq x_0$, $u(x) = x_0$ for $x > x_0$ (concave, with $u' = 1$ below and $0$ above $x_0$) gives $\int u f - \int u g = \int_0^{x_0} (G(x) - F(x)) dx < 0$ directly.

**Examples:** Normal distributions with different standard deviations; uniform distributions with different maxima and minima (same mean, wider support is an MPS).

---

## Application 1: Diversification

A risk-averse investor must divide wealth $w$ between two assets with returns $R_1$ and $R_2$ that are independent and identically distributed. The fully diversified portfolio invests half in each, with return $R = \frac{R_1 + R_2}{2}$. When is it optimal?

Any other portfolio investing $\alpha$ in asset 1 has return
$$\alpha R_1 + (1-\alpha) R_2 = \frac{R_1}{2} + \Big(\alpha - \frac{1}{2}\Big) R_1 + \frac{R_2}{2} + \Big(1 - \alpha - \frac{1}{2}\Big) R_2 = R + \Big(\alpha - \frac{1}{2}\Big)(R_1 - R_2)$$
which is $R$ plus another random variable. By Theorem 2.5, every risk-averse investor prefers the fully diversified portfolio if
$$\mathbb{E}\Big( \Big(\alpha - \frac{1}{2}\Big)(R_1 - R_2) \,\Big|\, R \Big) = 0$$
i.e. if the alternative portfolio is an MPS of the fully diversified one. Since $R_1$ and $R_2$ are iid, $\mathbb{E}(R_1 \mid R) = \mathbb{E}(R_2 \mid R)$, so the condition holds. Hence full diversification is optimal: every portfolio has the same expected return, but diversifying minimizes the risk from any single asset realizing an extreme return.

---

## Application 2: Precautionary Savings

A consumer lives two periods. Period-1 income $w_1$ is certain; period-2 income $\tilde{w}_2$ is random. Saving $s$ in period 1 gives consumptions $c_1 = w_1 - s$ and $c_2 = \tilde{w}_2 + s$. Utility is $u(c_1) + u(c_2)$ with $u$ three times continuously differentiable, $u' > 0$, $u'' < 0$, and $u''' > 0$:
$$\max_{s \geq 0}\ u(w_1 - s) + \mathbb{E}u(\tilde{w}_2 + s), \qquad \text{FOC: } -u'(w_1 - s) + \mathbb{E}u'(\tilde{w}_2 + s) \leq 0$$
with equality if $s^* > 0$. Strict concavity gives existence and uniqueness; assume $s^*(\tilde{w}_2) > 0$, so $-u'(w_1 - s^*(\tilde{w}_2)) + \mathbb{E}u'(\tilde{w}_2 + s^*(\tilde{w}_2)) = 0$.

Now let period-2 income become riskier: $\hat{w}_2 = \tilde{w}_2 + \epsilon$ with $\mathbb{E}\epsilon = 0$ (an MPS). Evaluate marginal utility at the old savings level:
$$\mathbb{E}u'(\hat{w}_2 + s^*(\tilde{w}_2)) = \mathbb{E}\big[ \mathbb{E}\big( u'(\tilde{w}_2 + \epsilon + s^*(\tilde{w}_2)) \,\big|\, \tilde{w}_2 \big) \big] > \mathbb{E}u'\big( \mathbb{E}(\tilde{w}_2 + \epsilon + s^*(\tilde{w}_2) \mid \tilde{w}_2) \big) = \mathbb{E}u'(\tilde{w}_2 + s^*(\tilde{w}_2))$$
The inequality is Jensen's applied to $u'$, which is convex because $u''' > 0$.

So at the old $s^*(\tilde{w}_2)$ the FOC is now strictly positive, and $s^*(\hat{w}_2) > s^*(\tilde{w}_2)$. Interpretation: with a mean-preserving spread the consumer faces more period-2 risk; she is risk averse ($u'' < 0$) with risk aversion decreasing in income ($u''' > 0$, i.e. convex marginal utility — "prudence"), so she saves more, using higher guaranteed period-2 income to offset the increased risk.

---

## Difficulty checklist

- **Independence axiom direction:** $p \succsim q \iff \alpha p \oplus (1-\alpha) r \succsim \alpha q \oplus (1-\alpha) r$ holds for *all* $\alpha \in [0,1]$ and *all* $r$ — the same mixing lottery $r$ on both sides. Swapping $r$ or using different $\alpha$'s breaks the axiom.
- **Allais paradox:** $L_3 = 0.25 L_1 \oplus 0.75 \delta_0$ and $L_4 = 0.25 L_2 \oplus 0.75 \delta_0$; choosing $L_1 \succ L_2$ but $L_4 \succ L_3$ violates independence. A common exam trap.
- **Continuity is the mixture form:** for $p \succ q \succ r$ there is an $\alpha$ with $q \sim \alpha p \oplus (1-\alpha) r$ — not the Chapter 1 topological definition, though they play the same role.
- **Bernoulli vs. VNM utility:** $u$ (Bernoulli) maps consequences to $\mathbb{R}$; the VNM utility of a lottery is $\sum_x p_x u(x)$, linear in probabilities. Bernoulli $u$ is unique only up to positive affine transformations $v = au + b$ with $a > 0$ (Theorem 2.2) — unlike ordinal utility in Chapter 1.
- **Risk aversion $\iff$ concavity:** $\delta_{\mathbb{E}p} \succsim p$ for all $p$ corresponds to concave $u$ via Jensen's inequality; strict versions pair together. Do not confuse with risk neutrality ($\delta_{\mathbb{E}p} \sim p$, linear $u$).
- **Insurance FOC signs:** the FOC is $-(1-\pi)P u'(\cdot) + \pi(L-P)u'(\cdot) = 0$; at actuarially fair $P = \pi L$ the two $u'$ terms must be equal, forcing equal income across states, i.e. $\alpha = 1$. With $P > \pi L$, plug $\alpha = 1$ into the FOC and get $(\pi L - P)u'(Y-P) < 0$, so $\alpha^* < 1$ (Proposition 2.1 is "full insurance $\iff$ actuarially fair").
- **Risk premium approximation:** $R(p) \approx \lambda(\mathbb{E}p) \cdot \mathrm{var}(p)/2$ — the factor $\tfrac{1}{2}$ and the variance (not the standard deviation) are easy to drop. Sign: $u'' < 0$ gives $\lambda > 0$ and $R(p) > 0$.
- **Proposition 2.2's four equivalences:** more risk averse $\iff$ lower $C(p)$ $\iff$ $u = h \circ v$ with $h$ increasing and concave $\iff$ $\lambda_u \geq \lambda_v$ everywhere. The $2 \iff 3$ step hinges on Jensen applied to $h(\mathbb{E}v(p))$ vs. $\mathbb{E}h(v(p))$; the $3 \iff 4$ step gives $\lambda_u - \lambda_v = -h''(v)/h'(v)$.
- **Portfolio FOC logic:** with $\mathbb{E}\theta \leq r$, compare each $u'$ to the constant $k = u'(\alpha(\underline{\theta} - r) + rW)$ using concavity, factor out $k(\mathbb{E}\theta - r) \leq 0$; with $\mathbb{E}\theta > r$, evaluate the FOC at $\alpha = 0$ to get $u'(rW)(\mathbb{E}\theta - r) > 0$. Corner solutions are the point, not interior ones.
- **Comparative statics proof:** splitting the FOC at $\theta < r$ vs. $\theta > r$ and bounding $h'(v(\cdot))$ at the boundary points $\tilde{\theta}, \hat{\theta}$ requires tracking the sign of each partial sum; concavity of $h$ gives both the bounds and $h'(v(\cdot \mid \tilde{\theta})) > h'(v(\cdot \mid \hat{\theta}))$.
- **FOSD integration by parts:** the boundary term $\big[u(x)(F(x)-G(x))\big]_0^{\bar{x}}$ vanishes only because $F(0)=G(0)=0$ and $F(\bar{x})=G(\bar{x})=1$; the survivor is $\int u'(G - F)$, which flips the inequality direction — a common sign error.
- **FOSD vs. SOSD:** FOSD needs $F(x) \leq G(x)$ everywhere and works for *all increasing* $u$; SOSD needs $\int_0^x F \leq \int_0^x G$ everywhere (integrated CDFs) plus equal means, and works for all increasing *concave* $u$. SOSD alone (statement 2) implies only $\mathbb{E}(X) \geq \mathbb{E}(Y)$.
- **Equal means in Theorem 2.5:** $\mathbb{E}(X) = \bar{x} - \int_0^{\bar{x}} F$; equal means kill the boundary term in the second integration by parts. Forgetting the equal-mean condition makes the theorem false.
- **MPS is a conditional statement:** $Y = X + Z$ with $\mathbb{E}(Z \mid X) = 0$ — conditional on $X$, not just $\mathbb{E}Z = 0$. In the diversification example this becomes $\mathbb{E}((\alpha - \tfrac{1}{2})(R_1 - R_2) \mid R) = 0$, which follows from $\mathbb{E}(R_1 \mid R) = \mathbb{E}(R_2 \mid R)$ under iid returns.
- **Precautionary savings need $u''' > 0$:** risk aversion ($u'' < 0$) alone does not raise savings under added risk; the argument applies Jensen to $u'$, which must be *convex* ($u''' > 0$, prudence). With $u''' < 0$ the result reverses.
