---
title: "Algebraic Automata Theory #1 - Semigroups"
date: 2026-09-02
---

Most intro courses to automata theory only cover the classical theory of
authomata: DFAs, NFAs, regular expressions, their properties, and the
conversions between them. But some important results in automata theory
cannot be proved using only those methods. Sometimes we need to reach to the
scary algebraic structures of semigroups and monoids.

Algebraic Automata Theory studies the (perhaps surprising) connection
between automata and algebra. This series of posts are my personal notes as I
try to learn AAT. I'm sure they contain many errors, but I hope that they are
usefull to someone trying to learn it too.

Since we want to study the connection between algebra and automata, we need
to start with some algebrai concepts.

> Def: A semigroup is a pair $S = (S, \cdot)$ where $S$ is a set and
> $\cdot : S \times S \to S$ is an associative binary operation on $S$, that is:
> $$
> a \cdot (b \cdot c) = (a \cdot b) \cdot c \qquad \forall a,b,c \in S
> $$

Since the semigroup operation (often called "multiplication") is associative,
we don't need to worry about parenthesis since the evaluation of expressions
becomes unambiguous. It is common to use the notation $a^n$ to denote the
multiplication of $n \in \mathbb N$ copies of $a\in S$.

> Lemma: The following properties hold:  
> 1. $a^n a^m = a^{n+m}$  
> 2. $(a^n)^m = a^{nm}$

There are some important kinds of semigroup elements with certain properties:  
1. Left identities: $1_l \cdot a = a ~ (\forall a \in S)$   
2. Right identities: $a\cdot 1_r = a ~ (\forall a \in S)$   
3. Left zeroes: $0_l\cdot a = 0_l ~ (\forall a \in S)$   
4. Right zeroes: $a\cdot 0_r = 0_r ~ (\forall a \in S)$   
5. Identities: $1 \cdot a = a = a \cdot 1 ~ (\forall a \in S)$  
6. Zeroes: $0 \cdot a = 0 = a \cdot 0 ~ (\forall a \in S)$  


> Lemma: A semigroup can have, at most, one identity and one zero element.
>
> Proof: Let $a, b$ be two identity elements. Then $a = ab = b$. The same
> argument applies to the other case. 

A semigroup with identity is called a monoid (which are also important for
automata theory):

> Def: A monoid is a triple $M = (M, \cdot, 1)$ where $M$ is a set,
> $\cdot : M \times M \to M$ is an associative binary operation on $M$,
> and $1\in M$ is an identity element, that is:
> $$
> a \cdot (b \cdot c) = (a \cdot b) \cdot c \qquad \forall a,b,c \in M
> $$
> $$
> a \cdot 1 = a = 1 \cdot a \qquad \forall a \in M
> $$

Any semigroup $S$ can be turned into a monoid $S^1$:
$$
S^1 = \begin{cases}
    S & \text{if } S \text{ has an identity element}\\
    S\cup\{1\} & \text{otherwise}
\end{cases}
$$
where $1 \notin S$ is the identity of the monoid and the multiplication is
extended accordingly.

There are other important kinds of semigroups:  
1. Finite Semigroups: the carrier set is finite  
2. Abelian Semigroups: the multiplication is commutative  
3. Groups: All elements have inverses  

Another important kind of element of a semigroup are the idempotents.
An element $i \in S$ is said to be idempotent if $i^2 = i$. The set of
idempotent elements of $S$ is denoted by $E(S)$.

> Thm: Every finite semigroup has an idempotent element.
>
> Proof: Let $a \in S$. Since $S$ is finite, the sequence $a, a^2, a^3, \cdots$
> must eventually become periodic with period $p$. Let $k$ be the first integer
> such that $a^k = a^{k+p}$. Let $m = kp$. Since $m > k$,
> $a^m = a^{m + kp} = a^{m+m} = a^{2m} = (a^m)^2$. Thus, $a^m$ is an idempotent
> element.

Next time, we will tackle homomorphisms.