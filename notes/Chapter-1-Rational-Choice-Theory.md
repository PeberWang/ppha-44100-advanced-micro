# Chapter 1 — Rational Choice Theory

*PPHA 44100 Advanced Microeconomics, Zhaosong Ruan (Harris), 2026-09-27*

## A Motivating Example: Labor Supply with Taxes and Transfers

An agent has 24 hours of time and earns wage $w$ per hour of work. The government taxes a fraction $\tau$ of her labor income and pays a transfer $T \geq 0$. She spends her post-tax income on consumption. If she works $l$ hours, her budget is $c \leq (1-\tau)wl + T$.

She chooses $l$ and $c$ to maximize

$$u(l,c) = \ln c + \ln(24 - l) \quad \text{subject to} \quad c \leq (1-\tau)wl + T$$

Solving the maximization problem gives

$$l^*(w,\tau,T) = 12 - \frac{T}{2(1-\tau)w}, \qquad c^*(w,\tau,T) = 12(1-\tau)w + \frac{T}{2}$$

From the closed-form solution we can read off three comparative-statics statements:

- Increasing transfer payments reduces hours worked: $\frac{\partial l^*}{\partial T} = -\frac{1}{2(1-\tau)w} < 0$
- If $T > 0$, increasing the tax rate reduces hours worked: $\frac{\partial l^*}{\partial \tau} = -\frac{T}{2(1-\tau)^2 w} < 0$
- If $T = 0$, the tax rate does not affect hours worked: $\frac{\partial l^*}{\partial \tau} = 0$

---

## The Policy Experiment

Suppose currently $w = 20$, $\tau = \frac{1}{2}$, $T = 100$. Then the agent works $l^* = 7$ hours, pays a tax of $70$, and receives a transfer of $100$.

Someone proposes changing to $\tau = 0$ and $T = 30$, keeping the agent's net budget the same. Is this change good for the agent?

With the new policy the agent chooses $l^* = 11.25$ and still receives a net transfer of $30$. The key observation: nothing prohibits her from working 7 hours under the new policy — the old bundle $(l,c) = (7, 170)$ is still affordable, since $c = 20 \cdot 7 + 30 = 170$. Hence, if she chooses not to work 7 hours, it must be that working 11.25 hours makes her strictly better off. This is a revealed-preference argument: her observed choice reveals that the new situation is preferred.

More generally, since the parameters $(w,\tau,T)$ pin down the agent's decisions, define the indirect utility function

$$v(w,\tau,T) = u(l^*(w,\tau,T),\, c^*(w,\tau,T)) = \ln\left(12 - \frac{T}{2(1-\tau)w}\right) + \ln\left(12(1-\tau)w + \frac{T}{2}\right)$$

This lets us analyze the welfare implications of policies directly — but it rests on interpreting higher values of $u$ (and $v$) as "better off".

---

## Methodological Questions

The example raises four questions:

1. Why should we model the agent's decision as the result of maximizing a function?
2. Why should the value of that function play a role in policy analysis?
3. How sensitive are the conclusions to the specific functional form chosen for $u$?
4. If they are sensitive, can we get useful conclusions with weaker assumptions?

The modeling methodology: identify a **target of inquiry**, then build a **model** that represents the target. There are two kinds of analysis: **inquiry into the model** (analyzing the model itself) and **inquiry with the model** (relating the model to the target for explanations and assessments).

A model must be similar to the target in some critical way, but it is impossible for a model to replicate all characteristics of the target. Distinguish **representational features** from **auxiliary features**: implications that do not depend on auxiliary features are suitable for assessing the target. This is why we want results that hold for whole classes of utility functions rather than for one functional form.

---

## Preferences: Basic Definitions

Consider a decision maker (DM) facing a set of alternatives $A$.

**Definition (Preference).** The DM has preferences defined by a binary relation $\succsim$ on $A$, with the interpretation that for $a, b \in A$, $a \succsim b$ means the DM does not prefer $b$ to $a$.

From $\succsim$ we derive two further relations on $A$.

**Definition (Strict preference and indifference).**

$$a \succ b \iff a \succsim b \text{ and not } b \succsim a; \qquad a \sim b \iff a \succsim b \text{ and } b \succsim a$$

It follows that $\succsim$ is the weak preference relation:

$$a \succsim b \iff a \succ b \text{ or } a \sim b$$

---

## Rational Preferences

**Definition (Rational preference).** A preference relation is rational if it satisfies two axioms:

- **Completeness:** for any $a, b \in A$, either $a \succsim b$ or $b \succsim a$
- **Transitivity:** for any $a, b, c \in A$, if $a \succsim b$ and $b \succsim c$, then $a \succsim c$

**Theorem 1.1.** If $\succsim$ is transitive, then $\succ$ and $\sim$ are both transitive.

Is transitivity always plausible? Consider an individual with three potential dating partners: $a$ is sexier than $b$, who is sexier than $c$; $b$ is smarter than $c$, who is smarter than $a$; $c$ is wealthier than $a$, who is wealthier than $b$. The individual prefers one partner to another if the former is better on two out of three dimensions. Then

$$a \succ b, \quad b \succ c, \quad c \succ a$$

— an intransitive cycle (a Condorcet-type cycle over the three dimensions). Transitivity can also fail because of just-perceptible differences: pairwise indifference based on imperceptible gaps need not aggregate transitively.

---

## Choice Problems and Preference-Maximizing Choices

**Definition (Choice problem).** A choice problem is a subset $B \subset A$ of alternatives that the DM believes to be feasible.

The preference-maximizing choices are

$$C^*(B, \succsim) = \{a \in B \mid a \succsim b \text{ for all } b \in B\}$$

That is, choices are made to (1) maximize (2) a rational preference.

**Theorem 1.2.** Suppose $B$ is finite and $\succsim$ is rational. Then $C^*(B, \succsim)$ is nonempty.

Rational preferences lead to well-defined choices.

---

## Choice Rules and Contraction Consistency

**Definition (Choice rule).** Let $\mathcal{B}$ be the set of all nonempty subsets of $A$. A choice rule $C$ is a mapping from $\mathcal{B}$ to $\mathcal{B}$ with the property that $C(B) \subset B$ for any $B \subset A$.

- A choice rule $C$ is **resolute** if $C(B)$ is always a singleton.
- Suppose $B$ and $D$ are nonempty subsets of $A$ with $D \subset B$. A resolute choice rule $C$ is **contraction consistent** if the following is always true:

$$C(B) \in D \implies C(B) = C(D)$$

Intuition: if the chosen element survives when the menu shrinks, it must still be chosen. Contraction consistency is the choice-rule analog of the Weak Axiom of Revealed Preference (WARP) / Sen's property $\alpha$: an alternative chosen from a large menu and still available in a smaller submenu must remain chosen there.

---

## Revealed Preference

**Definition (Agreement).** A choice rule $C$ and the preference-maximizing choices $C^*(\cdot, \succsim)$ derived from preferences $\succsim$ **agree for finite $B$** if

$$C(B) = C^*(B, \succsim) \text{ for any finite } B \subset A$$

**Theorem 1.3.** Suppose $C$ is a contraction consistent, resolute choice rule. Then there is a rational preference $\succsim_C$ such that $C$ and $C^*(\cdot, \succsim_C)$ agree for finite $B$.

The preference relation $\succsim_C$ is called the **revealed preference**: consistent observed choices can be rationalized as if the DM were maximizing a rational preference.

---

## Utility Representation

**Definition (Utility function).** A function $u : A \to \mathbb{R}$ **represents** $\succsim$ if, for every $a, b \in A$,

$$u(a) \geq u(b) \iff a \succsim b$$

Such a function is called a utility function. Utility functions are invariant to any strictly increasing transformation — they are **ordinal**, not cardinal: if $u$ represents $\succsim$ and $f : \mathbb{R} \to \mathbb{R}$ is strictly increasing, then $f \circ u$ also represents $\succsim$.

**Theorem 1.4.** Suppose $\succsim$ is represented by a utility function $u$. Then it is rational.

This is the easy direction: representability implies rationality, since $\geq$ on $\mathbb{R}$ is complete and transitive.

---

## Finite Alternative Sets: Existence of a Representation

**Definition.** An element $a \in X$ is $\succsim$-minimal in $X$ if $x \succsim a$ for all $x \in X$.

**Lemma 1.1.** Suppose $A$ is finite and $\succsim$ is rational. Then every nonempty subset $X \subset A$ has a $\succsim$-minimal element.

**Theorem 1.5.** Suppose $A$ is finite. A preference relation $\succsim$ can be represented by a utility function if it is rational.

So on finite sets, rationality and utility-representability coincide (Theorems 1.4 and 1.5 together). Lemma 1.1 is the workhorse for constructing the representation.

---

## Infinite Alternative Sets: Lexicographic Preferences

What could go wrong when the set of alternatives is infinite? Let $A = [0,1] \times [0,1]$.

**Definition (Lexicographic preference).** The lexicographic preference on $A$ is defined by

$$(x_1, y_1) \succsim (x_2, y_2) \iff x_1 > x_2 \ \text{or}\ (x_1 = x_2 \text{ and } y_1 > y_2)$$

The first coordinate dominates; the second only breaks ties.

**Proposition 1.1.** There does not exist any utility representation of the lexicographic preference.

Rationality alone is not enough for representability once $A$ is infinite — an extra condition is needed.

---

## Continuous Preferences and Debreu's Theorem

**Definition (Continuous preference).** Preferences are continuous if for any sequences of bundles $x_n \to x$ and $y_n \to y$,

$$x_n \succsim y_n \text{ for all } n \implies x \succsim y$$

Upper and lower contour sets are closed; preferences cannot "jump" at the limit.

**Theorem 1.6 (Debreu's Representation Theorem).** Suppose $A$ is a connected subset of $\mathbb{R}^n$. Preferences are complete, transitive and continuous if and only if they are represented by a continuous utility function.

Lexicographic preferences are rational but not continuous (at any point, a tiny improvement in the second coordinate is outweighed by an arbitrarily small loss in the first), which is exactly why Proposition 1.1 holds.

---

## Behaviorist vs. Intentionalist Readings

**Intentionalist reading:** people act to satisfy their preferences in light of their beliefs. The individual believes that the act is a good way to satisfy their preferences, and such beliefs actually lead to the act. Individuals acting on the basis of preferences and beliefs (satisfying certain conditions) act *as if* they are maximizing a utility function.

**Behaviorist reading:** individuals whose choices are contraction consistent act *as if* they were guided by preferences and beliefs.

Criticisms of the behaviorist reading:

- A pure behaviorist reading cannot provide explanations of choices based on the motivations of economic actors.
- Making sense of the consistency of choices already involves non-choice factors like motivations.

Example: meeting a new friend, with alternatives $x$: go home, $y$: have coffee together, $z$: have drugs together. For many people,

$$C(\{x,y\}) = y \quad \text{but} \quad C(\{x,y,z\}) = x$$

which violates contraction consistency: with $D = \{x,y\} \subset B = \{x,y,z\}$ and $C(B) = x \in D$, contraction consistency would require $C(D) = C(B) = x$, yet $C(D) = y$. The mere presence of $z$ in the menu changes the choice — a menu-dependent (context) effect that the bare choice data cannot explain without invoking motivations.

---

## Problems and Alternatives

People make decisions that deviate from the implications of the standard approach:

- **Framing effects** — choices depend on how the same problem is presented
- **Default effects** — choices depend on which option is the default
- **Choice-set-dependent preferences** — choices depend on what else is on the menu

These require a disciplined way of incorporating them into the standard model approach.

**Example (Default effect).** Let $A$ be the set of all alternatives, $B$ the set of feasible alternatives, and $d \in B$ the default option, so $(B, d)$ is a choice problem. Let $u : A \to \mathbb{R}$ represent the DM's "true" preferences, where $x \neq y$ implies $u(x) \neq u(y)$, and let $b : A \to \mathbb{R}$ represent a bonus attached to the default. Define

$$C_{u,b}(B,d) = \begin{cases} d & \text{if } u(d) + b(d) \geq u(x) \text{ for all } x \neq d \\ x & \text{if } u(x) > u(d) + b(d) \text{ and } u(x) > u(y) \text{ for all } y \neq x \end{cases}$$

The DM sticks with the default unless some alternative beats it by more than the default bonus. One can verify that $C_{u,b}$ is contraction consistent: for $d \in D \subset B$, if $C_{u,b}(B,d) \in D$, then $C_{u,b}(D,d) = C_{u,b}(B,d)$. The lesson: context effects like defaults can be folded into the standard framework in a disciplined way without giving up choice consistency — consistency alone does not rule them out.

---

## Difficulty checklist

- **Direction of the primitive relation:** $a \succsim b$ means the DM does *not* prefer $b$ to $a$. Strict preference and indifference are *derived* from $\succsim$, not primitives. Do not define $\succ$ first.
- **Completeness permits ties:** completeness says $a \succsim b$ or $b \succsim a$ (inclusive or). Both can hold — that is exactly indifference. It also implies reflexivity, $a \succsim a$.
- **Theorem 1.1 is one-directional:** transitivity of $\succsim$ implies transitivity of $\succ$ and $\sim$, but proving $\succ$ transitivity requires combining mixed cases ($a \succ b \sim c$ etc.) and invoking completeness; a naive chain of strict statements is not a proof.
- **Intransitivity examples to know:** the three-dimensional dating cycle (pairwise majority over attributes yields $a \succ b \succ c \succ a$) and just-perceptible differences (indifference thresholds break transitivity).
- **Theorem 1.2 needs finiteness:** $C^*(B,\succsim)$ nonempty is guaranteed for finite $B$ with rational $\succsim$. With infinite $B$ (e.g., open budget sets) a maximizer may fail to exist — continuity/compactness arguments come later.
- **$C^*(B,\succsim)$ is a set:** maximizing choices need not be unique. Resoluteness (singleton values) is an extra property of choice rules, not of preference maximization.
- **Contraction consistency direction:** it applies when $D \subset B$ and the choice from the *large* menu lies in the small one: $C(B) \in D \implies C(B) = C(D)$. Exam trap: the coffee/drugs example $C(\{x,y\}) = y$, $C(\{x,y,z\}) = x$ violates it — check the direction before concluding.
- **Contraction consistency $\approx$ WARP / Sen's $\alpha$:** chosen from a big menu and still available $\Rightarrow$ still chosen. Know how to translate between choice-rule language and revealed-preference language.
- **Theorem 1.3 direction:** choice behavior $\to$ preference (rationalizability). Given a contraction consistent resolute rule, the revealed preference $\succsim_C$ is *constructed from choices*; agreement is only guaranteed for finite $B$.
- **Ordinality:** if $u$ represents $\succsim$, so does $f \circ u$ for any strictly increasing $f$. Utility levels carry no meaning; comparisons of differences or ratios of utilities are meaningless. Only statements invariant to monotone transformations are legitimate.
- **Two directions of representation:** representable $\Rightarrow$ rational (Theorem 1.4, easy: $\geq$ on $\mathbb{R}$ is complete and transitive); rational $\Rightarrow$ representable needs finiteness (Theorem 1.5) or continuity plus a connected $A \subset \mathbb{R}^n$ (Debreu, Theorem 1.6). Do not claim the converse without the extra hypotheses.
- **Lemma 1.1 as proof engine:** existence of a $\succsim$-minimal element in every nonempty subset is what lets one rank a finite $A$; its proof uses transitivity (a set with no minimal element would cycle).
- **Lexicographic preferences:** rational but not representable (Proposition 1.1) and not continuous. Proof idea for non-representability: each $x$ would require a distinct nondegenerate interval of utility values, giving uncountably many disjoint intervals in $\mathbb{R}$, which is impossible.
- **Continuity definition:** preserved under limits: $x_n \to x$, $y_n \to y$, $x_n \succsim y_n$ for all $n \implies x \succsim y$. Equivalent to closed contour sets. Lexicographic fails it: a sequence better on the second coordinate can lose to a limit point worse by an arbitrarily small first-coordinate gap.
- **Comparative statics of the motivating example:** $l^* = 12 - \frac{T}{2(1-\tau)w}$. Transfers always reduce labor ($\partial l^*/\partial T < 0$); taxes reduce labor only when $T > 0$ ($\partial l^*/\partial \tau = -\frac{T}{2(1-\tau)^2 w}$). With $T = 0$ the income and substitution effects of the wage tax exactly cancel (Cobb-Douglas/log utility).
- **The revealed-preference policy argument:** under $(\tau, T) = (0, 30)$ the old bundle $(l,c) = (7,170)$ remains affordable; choosing $l^* = 11.25$ therefore reveals strict improvement. The argument needs affordability of the old choice — verify it before concluding welfare improvement.
- **Indirect utility:** $v(w,\tau,T) = u(l^*(w,\tau,T), c^*(w,\tau,T))$. Using $v$ for policy analysis already *assumes* higher $u$ means better off — an interpretive (intentionalist) step, not a purely behavioral one.
- **Behaviorist vs. intentionalist:** know which reading a theorem supports. Theorem 1.3 supports the behaviorist "as if" reading; welfare statements need the intentionalist reading. Pure behaviorism cannot explain choices via motivations, and judging choice consistency already imports non-choice factors.
- **Default-effect model:** $C_{u,b}(B,d)$ picks the default unless some $x$ beats it by more than the bonus $b(d)$. It is contraction consistent — consistency axioms do *not* exclude defaults/framing; such effects must be modeled explicitly and in a disciplined way.
- **Auxiliary vs. representational features:** conclusions that depend on a specific functional form of $u$ are suspect; robust policy conclusions are those invariant across the admissible class of representations.
