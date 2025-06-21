---
title: "lecture 17, uses of trees for MPL"
subtitle: phil1012 introductory logic
---

# overview

## this lecture

* uses of trees for MPL
* how to set up trees to test for various logical properties in MPL
* how to read off models from completed trees
* identifying infinite trees and reading models off the open paths of infinite trees

## learning outcomes

* after doing the relevant reading for this lecture, listening to the lecture, and attending the relevant tutorial, you will be able to:
    * use trees to test for various logical properties of MPL formulas
    * read off (counter)models from open paths of MPL trees
    * identify infinite trees and read models of infinite paths

## required reading

* sections 10.2 and 10.3 of chapter 10

# using trees

## using trees

* MPL trees, like PL trees, test for satisfiability, in the first instance.
* but we can use them to test for much more
* again, you need to know how to set up the tree, and how to interpret
    its results
* in the case of MPL trees, we read off models on which the initial
    propositions are jointly satisfiable
* these are called **countermodels** in the case of arguments.

---

* we set up and use MPL trees to test for various properties in much
    the same way as we did for PL trees.
* let's look at an example of testing some proposition to see whether it is a tautology

---

``` prooftree

\begin{prooftree}
{line numbering=false, to prove={$To prove: whether $ ((\exists x Fx \land \forall x (Fx \rightarrow Gx)) \rightarrow \exists xGx) $ is a tautology$.}}
[]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ ((\exists x Fx \land \forall x (Fx \rightarrow Gx)) \rightarrow \exists xGx) $ is a tautology$.}}
[\lnot(\exists x Fx \land \forall x (Fx \rightarrow Gx)) \rightarrow \exists xGx), just= Assumption]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ ((\exists x Fx \land \forall x (Fx \rightarrow Gx)) \rightarrow \exists xGx) $ is a tautology$.}}
[\lnot(\exists x Fx \land \forall x (Fx \rightarrow Gx)) \rightarrow \exists xGx), just= Assumption, checked [(\exists x Fx \land \forall x (Fx \rightarrow Gx)), just=Negated Conditional [\lnot\exists xGx, just=Negated Conditional]]  ]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ ((\exists x Fx \land \forall x (Fx \rightarrow Gx)) \rightarrow \exists xGx) $ is a tautology$.}}
[\lnot(\exists x Fx \land \forall x (Fx \rightarrow Gx)) \rightarrow \exists xGx), just= Assumption, checked [(\exists x Fx \land \forall x (Fx \rightarrow Gx)), checked, just=Negated Conditional [\lnot\exists xGx, just=Negated Conditional [\exists xFx, just=Conjunction [\forall x(Fx \rightarrow Gx), just=Conjunction]]]]  ]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ ((\exists x Fx \land \forall x (Fx \rightarrow Gx)) \rightarrow \exists xGx) $ is a tautology$.}}
[\lnot(\exists x Fx \land \forall x (Fx \rightarrow Gx)) \rightarrow \exists xGx), just= Assumption, checked [(\exists x Fx \land \forall x (Fx \rightarrow Gx)), checked, just=Negated Conditional [\lnot\exists xGx, checked, just=Negated Conditional [\exists xFx, just=Conjunction [\forall x(Fx \rightarrow Gx), just=Conjunction [\forall x \lnot Gx, just=Negated Existential]]]]]  ]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ ((\exists x Fx \land \forall x (Fx \rightarrow Gx)) \rightarrow \exists xGx) $ is a tautology$.}}
[\lnot(\exists x Fx \land \forall x (Fx \rightarrow Gx)) \rightarrow \exists xGx), just= Assumption, checked [(\exists x Fx \land \forall x (Fx \rightarrow Gx)), checked, just=Negated Conditional [\lnot\exists xGx, checked, just=Negated Conditional [\exists xFx, just=Conjunction, checked=a [\forall x(Fx \rightarrow Gx), just=Conjunction [\forall x \lnot Gx, just=Negated Existential [Fa, just=Existential ]]]]]]  ]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ ((\exists x Fx \land \forall x (Fx \rightarrow Gx)) \rightarrow \exists xGx) $ is a tautology$.}}
[\lnot(\exists x Fx \land \forall x (Fx \rightarrow Gx)) \rightarrow \exists xGx), just= Assumption, checked [(\exists x Fx \land \forall x (Fx \rightarrow Gx)), checked, just=Negated Conditional [\lnot\exists xGx, checked, just=Negated Conditional [\exists xFx, just=Conjunction, checked=a [\forall x(Fx \rightarrow Gx), just=Conjunction, subs=a [\forall x \lnot Gx, just=Negated Existential [Fa, just=Existential [Fa \rightarrow Ga, just=Universal ]]]]]]]  ]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ ((\exists x Fx \land \forall x (Fx \rightarrow Gx)) \rightarrow \exists xGx) $ is a tautology$.}}
[\lnot(\exists x Fx \land \forall x (Fx \rightarrow Gx)) \rightarrow \exists xGx), just= Assumption, checked [(\exists x Fx \land \forall x (Fx \rightarrow Gx)), checked, just=Negated Conditional [\lnot\exists xGx, checked, just=Negated Conditional [\exists xFx, just=Conjunction, checked=a [\forall x(Fx \rightarrow Gx), just=Conjunction, subs=a [\forall x \lnot Gx, just=Negated Existential [Fa, just=Existential [Fa \rightarrow Ga, checked, just=Universal [\lnot Fa, close][Ga, just=Conditional] ]]]]]]]  ]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ ((\exists x Fx \land \forall x (Fx \rightarrow Gx)) \rightarrow \exists xGx) $ is a tautology$.}}
[\lnot(\exists x Fx \land \forall x (Fx \rightarrow Gx)) \rightarrow \exists xGx), just= Assumption, checked [(\exists x Fx \land \forall x (Fx \rightarrow Gx)), checked, just=Negated Conditional [\lnot\exists xGx, checked, just=Negated Conditional [\exists xFx, just=Conjunction, checked=a [\forall x(Fx \rightarrow Gx), just=Conjunction, subs=a [\forall x \lnot Gx, just=Negated Existential, subs=a [Fa, just=Existential [Fa \rightarrow Ga, checked, just=Universal [\lnot Fa, close][Ga, just=Conditional, [\lnot Ga, close, just=Universal]] ]]]]]]]]
\end{prooftree}

```
---

* we can conclude that $((\exists x Fx \land \forall x (Fx \rightarrow Gx)) \rightarrow \exists xGx)$
    is a tautology, since its negation is not satisfiable.

---

* to take another example, suppose we want to test whether some argument is a valid argument

---

``` prooftree

\begin{prooftree}
{line numbering=false, to prove={$To prove: whether $ \exists xFx, \exists xGx \therefore \exists x(Fx \land Gx) $ is a valid argument$.}}
[]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists xFx, \exists xGx \therefore \exists x(Fx \land Gx) $ is a valid argument$.}}
[\exists xFx, just=Assumption [\exists xGx, just=Assumption [\lnot\exists x(Fx \land Gx), just=Negated Conclusion ]]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists xFx, \exists xGx \therefore \exists x(Fx \land Gx) $ is a valid argument$.}}
[\exists xFx, just=Assumption [\exists xGx, just=Assumption [\lnot\exists x(Fx \land Gx), just=Negated Conclusion ]]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists xFx, \exists xGx \therefore \exists x(Fx \land Gx) $ is a valid argument$.}}
[\exists xFx, just=Assumption [\exists xGx, just=Assumption [\lnot\exists x(Fx \land Gx), checked, just=Negated Conclusion [\forall x \lnot(Fx \land Gx), just=Negated Existential ]]]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists xFx, \exists xGx \therefore \exists x(Fx \land Gx) $ is a valid argument$.}}
[\exists xFx, checked=a, just=Assumption [\exists xGx, just=Assumption [\lnot\exists x(Fx \land Gx), checked, just=Negated Conclusion [\forall x \lnot(Fx \land Gx), just=Negated Existential [Fa, just=Existential ]]]]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists xFx, \exists xGx \therefore \exists x(Fx \land Gx) $ is a valid argument$.}}
[\exists xFx, checked=a, just=Assumption [\exists xGx, checked=b, just=Assumption [\lnot\exists x(Fx \land Gx), checked, just=Negated Conclusion [\forall x \lnot(Fx \land Gx), just=Negated Existential [Fa, just=Existential [Gb, just=Existential ]]]]]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists xFx, \exists xGx \therefore \exists x(Fx \land Gx) $ is a valid argument$.}}
[\exists xFx, checked=a, just=Assumption [\exists xGx, checked=b, just=Assumption [\lnot\exists x(Fx \land Gx), checked, just=Negated Conclusion [\forall x \lnot(Fx \land Gx), subs={a}, just=Negated Existential [Fa, just=Existential [Gb, just=Existential [\lnot (Fa \land Ga), just=Universal ]]]]]]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists xFx, \exists xGx \therefore \exists x(Fx \land Gx) $ is a valid argument$.}}
[\exists xFx, checked=a, just=Assumption [\exists xGx, checked=b, just=Assumption [\lnot\exists x(Fx \land Gx), checked, just=Negated Conclusion [\forall x \lnot(Fx \land Gx), subs={a}, just=Negated Existential [Fa, just=Existential [Gb, just=Existential [\lnot (Fa \land Ga), checked, just=Universal [\lnot Fa, close][\lnot Ga, just=Negated Conjunction ]]]]]]]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists xFx, \exists xGx \therefore \exists x(Fx \land Gx) $ is a valid argument$.}}
[\exists xFx, checked=a, just=Assumption [\exists xGx, checked=b, just=Assumption [\lnot\exists x(Fx \land Gx), checked, just=Negated Conclusion [\forall x \lnot(Fx \land Gx), subs={a, b}, just=Negated Existential [Fa, just=Existential [Gb, just=Existential [\lnot (Fa \land Ga), checked, just=Universal [\lnot Fa, close][\lnot Ga, just=Negated Conjunction [\lnot (Fb \land Gb),  just=Universal ]]]]]]]]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists xFx, \exists xGx \therefore \exists x(Fx \land Gx) $ is a valid argument$.}}
[\exists xFx, checked=a, just=Assumption [\exists xGx, checked=b, just=Assumption [\lnot\exists x(Fx \land Gx), checked, just=Negated Conclusion [\forall x \lnot(Fx \land Gx), subs={a, b}, just=Negated Existential [Fa, just=Existential [Gb, just=Existential [\lnot (Fa \land Ga), checked, just=Universal [\lnot Fa, close][\lnot Ga, just=Negated Conjunction [\lnot (Fb \land Gb), checked, just=Universal [\lnot Fb][\lnot Gb, just=Negated Conjunction, close]]]]]]]]]]
\end{prooftree}

```

---

* we can conclude that $\exists xFx, \exists xGx \therefore \exists x(Fx \land Gx)$ is not
    a valid argument, since the premises, $\exists xFx, \exists xGx,$
    and the negated conclusion, $\lnot \exists x(Fx \land Gx)$ are
    jointly satisfiable.
* we want to be able to read off a countermodel from our tree.
* how?

# how to read off models from open paths

## how to read off models from open paths

* a model consists of:
    * a domain
    * a referent for each name which appears on the path
    * an extension for each predicate which appears on the path

---

* where there are *n* names in the path, we write our domain as follows:
    * domain: {1, ..., *n*}
* so if there are 3 names in the path, we write our domain as follows:
    * domain: {1,2,3}
* we then assign each name in the path to an object in the domain as
    follows:
    * referents: $a$:1, $b$:2, $c$:3, ...

---

* we then assign an extension to each predicate which makes atomic
    formulas involving the predicate true.
* if $Fa$, $Ga$, and $Gb$, are all on an open path, then we assign the
    following extensions to the predicates:
    * extensions: $F$: {1}, $G$: {1,2}.
* if the predicate $H$ is on the open path but does not occur in an
    atomic formula, then we assign the following extension to the
    predicate:
    * extensions: $H$: $\emptyset$ (Not $H$: {$\emptyset$}).

---

* let's consider an example ...

---

* suppose we want to read a model off of this tree:

---

``` prooftree

\begin{prooftree}
{line numbering=true}
[\exists xFx, checked=a, just=Assumption [\exists xGx, checked=b, just=Assumption [\lnot\exists x(Fx \land Gx), checked, just=Negated Conclusion [\forall x \lnot(Fx \land Gx), subs={a, b}, just=Negated Existential [Fa, just=Existential [Gb, just=Existential [\lnot (Fa \land Ga), checked, just=Universal [\lnot Fa, close][\lnot Ga, just=Negated Conjunction [\lnot (Fb \land Gb), checked, just=Universal [\lnot Fb][\lnot Gb, just=Negated Conjunction, close]]]]]]]]]]
\end{prooftree}

```

---

* first step: find the number of names on the open path

---

``` prooftree

\begin{prooftree}
{line numbering=true}
[\exists xFx, checked=a, just=Assumption [\exists xGx, checked=b, just=Assumption [\lnot\exists x(Fx \land Gx), checked, just=Negated Conclusion [\forall x \lnot(Fx \land Gx), subs={a, b}, just=Negated Existential [Fa, just=Existential [Gb, just=Existential [\lnot (Fa \land Ga), checked, just=Universal [\lnot Fa, close][\lnot Ga, just=Negated Conjunction [\lnot (Fb \land Gb), checked, just=Universal [\lnot Fb][\lnot Gb, just=Negated Conjunction, close]]]]]]]]]]
\end{prooftree}

```

---

* there are two, so we have the following domain:
    * domain: {1, 2}

---

* second step: assign each name in the path to an object in the
    domain

---


``` prooftree

\begin{prooftree}
{line numbering=true}
[\exists xFx, checked=a, just=Assumption [\exists xGx, checked=b, just=Assumption [\lnot\exists x(Fx \land Gx), checked, just=Negated Conclusion [\forall x \lnot(Fx \land Gx), subs={a, b}, just=Negated Existential [Fa, just=Existential [Gb, just=Existential [\lnot (Fa \land Ga), checked, just=Universal [\lnot Fa, close][\lnot Ga, just=Negated Conjunction [\lnot (Fb \land Gb), checked, just=Universal [\lnot Fb][\lnot Gb, just=Negated Conjunction, close]]]]]]]]]]
\end{prooftree}

```

---

* we assign referents in the most natural manner:
    * referents: $a$: 1, $b$: 2

---

* third step: assign an extension to each predicate which makes
    atomic formulas involving the predicate true

---

``` prooftree

\begin{prooftree}
{line numbering=true}
[\exists xFx, checked=a, just=Assumption [\exists xGx, checked=b, just=Assumption [\lnot\exists x(Fx \land Gx), checked, just=Negated Conclusion [\forall x \lnot(Fx \land Gx), subs={a, b}, just=Negated Existential [Fa, highlight wff, just=Existential [Gb, just=Existential [\lnot (Fa \land Ga), checked, just=Universal [\lnot Fa, close][\lnot Ga, just=Negated Conjunction [\lnot (Fb \land Gb), checked, just=Universal [\lnot Fb][\lnot Gb, just=Negated Conjunction, close]]]]]]]]]]
\end{prooftree}

```

---

* we assign an extension to $F$ which makes $Fa$ true:
    * extensions: $F$: {1}

---

``` prooftree

\begin{prooftree}
{line numbering=true}
[\exists xFx, checked=a, just=Assumption [\exists xGx, checked=b, just=Assumption [\lnot\exists x(Fx \land Gx), checked, just=Negated Conclusion [\forall x \lnot(Fx \land Gx), subs={a, b}, just=Negated Existential [Fa, highlight wff, just=Existential [Gb, highlight wff, just=Existential [\lnot (Fa \land Ga), checked, just=Universal [\lnot Fa, close][\lnot Ga, just=Negated Conjunction [\lnot (Fb \land Gb), checked, just=Universal [\lnot Fb][\lnot Gb, just=Negated Conjunction, close]]]]]]]]]]
\end{prooftree}

```

---

* we assign an extension to $G$ which makes $Gb$ true:
    * extensions: $F$: {1}, $G$: {2}

---

* here is our completed model:
    * domain: {1, 2}
    * deferents: $a$: 1, $b$: 2
    * extensions: $F$: {1}, $G$: {2}


# oh no! infinite trees

## oh no! infinite trees

* unlike PL trees, MPL trees have an interesting feature: they can be
    infinitely long
* see pp. 372--373 of the textbook for how to avoid infinite trees in
    MPL
* let's consider an example of an infinite tree

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $  \forall x (Fx \land \exists y Gy) $ is satisfiable$.}}
[ \forall x (Fx \land \exists y Gy)]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $  \forall x (Fx \land \exists y Gy) $ is satisfiable$.}}
[ \forall x (Fx \land \exists y Gy), subs=a [(Fa \land \exists y Gy)]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $  \forall x (Fx \land \exists y Gy) $ is satisfiable$.}}
[ \forall x (Fx \land \exists y Gy), subs=a [(Fa \land \exists y Gy), checked [\exists y Gy [Fa ]]]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $  \forall x (Fx \land \exists y Gy) $ is satisfiable$.}}
[ \forall x (Fx \land \exists y Gy), subs=a [(Fa \land \exists y Gy), checked [\exists y Gy, checked=b [Fa [Gb]]]]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $  \forall x (Fx \land \exists y Gy) $ is satisfiable$.}}
[ \forall x (Fx \land \exists y Gy), subs={a,b} [(Fa \land \exists y Gy), checked [\exists y Gy, checked=b [Fa [Gb  [(Fb \land \exists y Gy), checked [\exists y Gy, checked=c [Fb [Gc]]]]]]]]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $  \forall x (Fx \land \exists y Gy) $ is satisfiable$.}}
[ \forall x (Fx \land \exists y Gy), subs={a,b,c} [(Fa \land \exists y Gy), checked [\exists y Gy, checked=b [Fa [Gb  [(Fb \land \exists y Gy), checked[\exists y Gy, checked=c [Fb [Gc [(Fc \land \exists y Gy), checked [\exists y Gy, checked=d [Fc [Gd]]]]]]]]]]]]]
\end{prooftree}

```

---

* this tree is going to go on like this forever
* it will never be complete
* it has an infinite path

---

* is the proposition satisfiable or not?
* is the path saturated or not?
* it is saturated
* so it is satisfiable
* we can read off a model

---

* will the proposition always be satisfiable if we have an infinite
    tree?
* will infinite paths always be saturated?
* no and no.
* here is an example

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \forall x(Fx \land \exists y Gy) \land (Ga \land \lnot Ga)$ is satisfiable$.}}
[\forall x(Fx \land \exists y Gy) \land (Ga \land \lnot Ga)]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \forall x(Fx \land \exists y Gy) \land (Ga \land \lnot Ga)$ is satisfiable$.}}
[\forall x(Fx \land \exists y Gy) \land (Ga \land \lnot Ga), checked [\forall x(Fx \land \exists y Gy) [(Ga \land \lnot Ga)]]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \forall x(Fx \land \exists y Gy) \land (Ga \land \lnot Ga)$ is satisfiable$.}}
[\forall x(Fx \land \exists y Gy) \land (Ga \land \lnot Ga), checked [\forall x(Fx \land \exists y Gy), subs=a [(Ga \land \lnot Ga)[Fa \land \exists y Gy]  ]]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \forall x(Fx \land \exists y Gy) \land (Ga \land \lnot Ga)$ is satisfiable$.}}
[\forall x(Fx \land \exists y Gy) \land (Ga \land \lnot Ga), checked [\forall x(Fx \land \exists y Gy), subs=a [(Ga \land \lnot Ga)[Fa \land \exists y Gy, checked [Fa [\exists y Gy]]]]]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \forall x(Fx \land \exists y Gy) \land (Ga \land \lnot Ga)$ is satisfiable$.}}
[\forall x(Fx \land \exists y Gy) \land (Ga \land \lnot Ga), checked [\forall x(Fx \land \exists y Gy), subs={a,b} [(Ga \land \lnot Ga)[Fa \land \exists y Gy, checked [Fa [\exists y Gy, checked=b [Gb [Fb \land \exists y Gy [Fb [\exists y Gy, checked=c [Gc]]]]]]]]]]]
\end{prooftree}

```

---

* here is another infinite path (if we ignore $Ga \land \lnot Ga$).
* but the proposition is not satisfiable.
* and the path is not saturated.
* and if we were to saturate it, by applying the rule for $\land$ to
    $Ga \land \lnot Ga$, it would close straight away.

# reading models off infinite trees

## reading models off infinite trees

* I said we could read a model off of our infinite tree above.
* let's look at how.
* here is our tree again:

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $  \forall x (Fx \land \exists y Gy) $ is satisfiable$.}}
[ \forall x (Fx \land \exists y Gy), subs={a,b,c} [(Fa \land \exists y Gy), checked [\exists y Gy, checked=b [Fa [Gb  [(Fb \land \exists y Gy), checked[\exists y Gy, checked=c [Fb [Gc [(Fc \land \exists y Gy), checked [\exists y Gy, checked=d [Fc [Gd]]]]]]]]]]]]]
\end{prooftree}

```

---

* what is the domain?
* how many names occur on the open path?
* an infinite number of names occur
* so here is our domain:
    * domain: {1, 2, 3, . . . }

---

* how shall we assign referents to each of the infinite number of
    names?
* like this of course:
     * referents: $a$: 1, $b$: 2, $c$: 3 . . .

---

* and what about extensions for the predicates?
* well, there are only two predicates $F$ and $G$.
* but we need an assignment which makes them true whenever they appear
    in atomic propositions on the path.
* let's look at our tree and think about it . . .

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $  \forall x (Fx \land \exists y Gy) $ is satisfiable$.}}
[ \forall x (Fx \land \exists y Gy), subs={a,b,c} [(Fa \land \exists y Gy), checked [\exists y Gy, checked=b [Fa [Gb  [(Fb \land \exists y Gy), checked[\exists y Gy, checked=c [Fb [Gc [(Fc \land \exists y Gy), checked [\exists y Gy, checked=d [Fc [Gd]]]]]]]]]]]]]
\end{prooftree}

```

---

* the pattern for $G$ is: $Gb$, $Gc$, $Gd$, ...
* the pattern for $F$ is: $Fa$, $Fb$, $Fc$, ...
* our complete model, then:
    * domain: {1, 2, 3, . . . }
    * referents: $a$: 1, $b$: 2, $c$: 3 . . .
    * extensions: $F$: {$1$, $2$, $3$, . . .}, $G$: {$2$, $3$, . . .}.

---

* will you have to read off a model from an infinite tree in the
    problem sets or the exam?
* possibly. but if so, it won't be a difficult pattern to identify.

# wrapping up

## this lecture

## next lecture

* [lecture 18, the formal language GPL](18_the_formal_language_GPL.html)

