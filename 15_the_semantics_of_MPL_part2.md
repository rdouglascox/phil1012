---
title: lecture 15, the semantics of MPL (part 2)
subtitle: phil1012 introductory logic
---

# overview

## this lecture

* second of two lectures on the semantics of MPL
* the semantics of complicated quantified propositions in MPL
* analyses of logical concepts in MPL

## learning outcomes

* after doing the relevant reading for this lecture, listening to the lecture, and attending the relevant tutorial, you will be able to:
    * explain how the truth values of complex quantified propositions are determined in MPL
    * explain how models provide analyses of various logical concepts (like validity) in MPL
    * determine whether a complex quantified proposition of MPL is true or false on a given model
    * describe a model on which an MPL proposition is true and/or a model on which a proposition is false

## required reading

* sections 9.4 and 9.5 of chapter 9

# complex quantified propositions

## complex quantified propositions

* how are the truth values of the following determined?
    * $\forall x(Px \rightarrow Rx)$
    * $\exists x(Px \land Rx)$
* we do not yet have a way of determining the truth values of these
    propositions

---

* but we do have a way of determining the truth values of the
    following in a model:
    * $(Pa \rightarrow Ra)$
    * $(Pa \land Ra)$

---

* so here's an idea . . .
* we can replace a question we *cannot* answer with many questions we
    *can* answer
* we can answer questions about the values of expressions like
    $(Pa \land Ra)$ in models related to $\mathcal{M}$
* it turns out that if we ask the right questions we can answer
    questions about the truth values of complex quantified expressions

## some new terminology

* but before we get to that, we need some new terminology
* we use $\alpha(\underline{x})$ to stand for an arbitrary formula
    which has no free variables other than $\underline{x}$
* we use $\alpha(\underline{a}/ \underline{x})$ to stand for a formula
    that results from $\alpha(\underline{x})$ by replacing all the free
    occurrences of $\underline{x}$ in $\alpha(\underline{x})$ with
    $\underline{a}$

---

* for example
* if we have . . .
    * $\alpha(x): (Fx \rightarrow Gx)$
* then we have . . .
    * $\alpha(a/x): (Fa \rightarrow Ga)$
    * $\alpha(b/x): (Fb \rightarrow Gb)$

---

* if we have . . .
    * $\alpha(x): ((Fx \land Ga) \lor (Gx \leftrightarrow Hx))$
* then we have . . .
    * $\alpha(a/x):((Fa \land Ga) \lor (Ga \leftrightarrow Ha))$
    * $\alpha(b/x): ((Fb \land Ga) \lor (Gb \leftrightarrow Hb))$

---

* if we have . . .
    * $\alpha(y):  \forall x ((Fx \land Ga) \rightarrow (Gx \lor Hy))$
* then we have . . .
    * $\alpha(a/y):  \forall x ((Fx \land Ga) \rightarrow (Gx \lor Ha))$
    * $\alpha(b/y):  \forall x ((Fx \land Ga) \rightarrow (Gx \lor Hb))$

---

* now let's put this new terminology to use

## complex universally quantified propositions

* let's see how we can work out the truth value of a complex
    universally quantified proposition like this:
    * $\forall x(Px \rightarrow Rx)$
* on a model like this:
    * model $\mathcal{M}$:
        * domain: {Bill, Ben, Alice}
        * extensions: $P$: {Bill} $R$: {Bill, Alice}

---

* here's how we do it
* according to the semantics of MPL:
    $\forall \underline{x} \alpha (\underline{x})$ is true in
    $\mathcal{M}$ iff for every object $o$ in the domain of
    $\mathcal{M}$, $\alpha(\underline{a}/\underline{x})$ is true in
    $\mathcal{M}_{o}^{\underline{a}}$, where $\underline{a}$ is some
    name that is not assigned a referent in $\mathcal{M}$, and
    $\mathcal{M}_{o}^{\underline{a}}$ is a model just like $\mathcal{M}$
    except that in it the name $\underline{a}$ is assigned the referent
    $o$

---

* so take some name that doesn't have a referent on $\mathcal{M}$, say
    $b$
* what this means is that $\forall x(Px \rightarrow Rx)$ is true in
    $\mathcal{M}$ if and only if $Pb \rightarrow Rb$ is true on every
    model that is exactly like $\mathcal{M}$ except that it assigns a
    referent to $b$
* so to check whether our proposition is true on this model, we
    literally check every model which meets this condition

---

* here's one such model which is exactly like $\mathcal{M}$ except
    that it assigns a referent to $b$:
    * model $\mathcal{M}^1$:
        * domain: {Bill, Ben, Alice}
        * referents: $b$: Bill
        * extensions: $P$: {Bill}, $R$: {Bill, Alice}
* we ask whether the following is true on the model:
   * $\alpha(b/x): (Pb \rightarrow Rb)$
* it is true in $\mathcal{M}^1$

---

* here's another model which is exactly like $\mathcal{M}$ except that
    it assigns a referent to $b$:
    * model $\mathcal{M}^2$:
        * domain: {Bill, Ben, Alice}
        * referents: $b$: Ben
        * extensions: $P$: {Bill}, $R$: {Bill, Alice}
* we ask whether the following is true on the model:
    * $\alpha(b/x): (Pb \rightarrow Rb)$
* it is true in $\mathcal{M}^2$

---

* here's another model which is exactly like $\mathcal{M}$ except that
    it assigns a referent to $b$:
    * model $\mathcal{M}^3$:
        * domain: {Bill, Ben, Alice}
        * referents: $b$: Alice
        * extensions: $P$: {Bill}, $R$: {Bill, Alice}
* we ask whether the following is true on the model:
    * $\alpha(b/x): (Pb \rightarrow Rb)$
* it is true in $\mathcal{M}^3$

---

* $\forall x(Px \rightarrow Rx)$ is true in $\mathcal{M}$ if and only
    if $Pb \rightarrow Rb$ is true on every model that is exactly like
    $\mathcal{M}$ except that it assigns a referent to $b$
* we haven't checked every such model
* but we've checked one for each
    object in the domain of $\mathcal{M}$
* so $\forall x(Px \rightarrow Rx)$ is true in $\mathcal{M}$

---

## complex existentially quantified propositions

* let's see how we can work out the truth value of a complex
    existentially quantified proposition like this:
    * $\exists x(Px \rightarrow Rx)$
* on a model like this:
    * model $\mathcal{M}$:
        * domain: {Bill, Ben, Alice}
        * extensions: $P$: {Bill} $R$: {Bill, Alice}

---

* here's how we do it
* according to the semantics of MPL:
    $\exists\underline{x} \alpha (\underline{x})$ is true in
    $\mathcal{M}$ iff there is at least one object $o$ in the domain of
    $\mathcal{M}$ such that $\alpha(\underline{a}/\underline{x})$ is
    true in $\mathcal{M}_{o}^{\underline{a}}$, where $\underline{a}$ is
    some name that is not assigned a referent in $\mathcal{M}$, and
    $\mathcal{M}_{o}^{\underline{a}}$ is a model just like $\mathcal{M}$
    except that in it the name $\underline{a}$ is assigned the referent
    $o$

---

* so take some name that doesn't have a referent on $\mathcal{M}$, say
    $b$
* what this means is that $\exists x(Px \rightarrow Rx)$ is true in
    $\mathcal{M}$ if and only if $Pb \rightarrow Rb$ is true on *some*
    model that is exactly like $\mathcal{M}$ except that it assigns a
    referent to $b$
* so to check whether our proposition is true on this model, we check
    to see if there is such a model which meets this condition

---

* here's one such model which is exactly like $\mathcal{M}$ except
    that it assigns a referent to $b$:
    * model $\mathcal{M}^1$:
        * domain: {Bill, Ben, Alice}
        * referents: $b$: Bill
        * extensions: $P$: {Bill}, $R$: {Bill, Alice}
* we ask whether the following is true on the model:
    * $\alpha(b/x): (Pb \rightarrow Rb)$
* it is true on $\mathcal{M}^1$

---

* $\exists x(Px \rightarrow Rx)$ is true in $\mathcal{M}$ if and only
    if $Pb \rightarrow Rb$ is true on *some* model that is exactly like
    $\mathcal{M}$ except that it assigns a referent to $b$
* we have just seen such a model
* so $\exists x(Px \rightarrow Rx)$ is true in $\mathcal{M}$

# the semantics of MPL

## the semantics of MPL, stated again

* we are now, finally, in a position to state complete semantics of
    MPL . . .
* see handout "The Semantics of MPL"

---

1.  $\underline{P}\underline{a}$ is true in $\mathcal{M}$ iff the
    referent of $\underline{a}$ in $\mathcal{M}$ is in the extension of
    $\underline{P}$ in $\mathcal{M}$

2.  $\lnot \alpha$ is true in $\mathcal{M}$ iff $\alpha$ is false in
    $\mathcal{M}$

3.  $(\alpha \land \beta)$ is true in $\mathcal{M}$ iff $\alpha$ and
    $\beta$ are both true in $\mathcal{M}$

4.  $(\alpha \lor \beta)$ is true in $\mathcal{M}$ iff one or both of
    $\alpha$ and $\beta$ is true in $\mathcal{M}$

5.  $(\alpha \rightarrow \beta)$ is true in $\mathcal{M}$ iff $\alpha$
    is false in $\mathcal{M}$ or $\beta$ is true in $\mathcal{M}$ or
    both

6.  $(\alpha \leftrightarrow \beta)$ is true in $\mathcal{M}$ iff
    $\alpha$ and $\beta$ are both true in $\mathcal{M}$ or both false in
    $\mathcal{M}$

---

7.  $\forall \underline{x} \alpha (\underline{x})$ is true in
    $\mathcal{M}$ iff for every object $o$ in the domain of
    $\mathcal{M}$, $\alpha(\underline{a}/\underline{x})$ is true in
    $\mathcal{M}_{o}^{\underline{a}}$, where $\underline{a}$ is some
    name that is not assigned a referent in $\mathcal{M}$, and
    $\mathcal{M}_{o}^{\underline{a}}$ is a model just like $\mathcal{M}$
    except that in it the name $\underline{a}$ is assigned the referent
    $o$

8.  $\exists\underline{x} \alpha (\underline{x})$ is true in
    $\mathcal{M}$ iff there is at least one object $o$ in the domain of
    $\mathcal{M}$ such that $\alpha(\underline{a}/\underline{x})$ is
    true in $\mathcal{M}_{o}^{\underline{a}}$, where $\underline{a}$ is
    some name that is not assigned a referent in $\mathcal{M}$, and
    $\mathcal{M}_{o}^{\underline{a}}$ is a model just like $\mathcal{M}$
    except that in it the name $\underline{a}$ is assigned the referent
    $o$

# analyses of logical concepts

## analyses of logical concepts

* we now get analyses of our core logical notions
* they are just what you would expect given that a model plays the
    same role in MPL as truth table rows played in PL

---

* an argument is **valid** iff there is no model in which the premises
    are all true and the conclusion is false
* an argument is **invalid** iff there is a model in which the
    premises are all true and the conclusion is false
* such a model is a **counterexample** or **countermodel** to the
    argument

---

* a proposition is a **tautology** iff there is no model in which it
    is false
* a proposition is a **contradiction** iff there is no model in which
    it is true
* a proposition is **satisfiable** if and only if there is at least
    one model in which it is true

---

* two propositions are **equivalent** iff there is no model in which
    one is true and the other is false
* two propositions are **contradictory** iff there is no model in
    which they have the same truth value
* two propositions are **jointly satisfiable** iff there is at least
    one model in which they are both true

---

* a set of propositions is **satisfiable** iff there is at least one
    model in which all the propositions in the set are true

# analyses and tests

## analyses and tests

* in PL truth tables provided an analysis of validity and a method of
    testing for validity
* in MPL, models give analyses---but *not* tests
* our analysis of validity *fixes the facts* concerning which arguments in
    MPL are valid
* however, we have no way of finding out whether an argument is valid
    How do you know that there is *no* model on which the premises are
    all true and the conclusion is false? There is an infinite number of
    models. you can't check them all!
* trees for MPL to the rescue!

# wrapping up

## this lecture

* the semantics of complicated quantified propositions in MPL
* analyses of central logical notions in terms of models

## next lecture

* [lecture 16, trees for MPL](16_trees_for_MPL.html)
