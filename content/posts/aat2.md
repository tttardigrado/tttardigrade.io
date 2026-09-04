---
title: "Algebraic Automata Theory #2 - Homomorphisms"
date: 2026-09-02
---

Perhaps the most important feature of modern mathematics is the study of not only
structures, but also of the structure preserving maps between them:

> Def: Let $S = (S, \cdot)$ and $T = (T, \times)$ be semigroups. A semigroup
> homomorphism is a function $\varphi : S \to T$ such that
> $$\varphi(a \cdot b) = \varphi(a) \times \varphi(b)$$

This notion extends easily to monoids by requiring that the identity element is
also preserved, i.e., $\varphi(1_S) = 1_T$. 

