---
title: lecture 14, the semantics of MPL (part 1)
subtitle: phil1012 introductory logic
---

# overview

## this lecture

* the first of two lectures on the semantics of MPL
* an introduction to the central notion of a model
* how the truth values of MPL formulas are determined on a given model
* just the semantics of MPL for uncomplicated propositions

## learning outcomes

* after doing the relevant reading for this lecture, listening to the lecture, and attending the relevant tutorial, you will be able to:
    * explain what a model consists of
    * explain what a model of a fragment of MPL consists of
    * explain how the truth values of atomic propositions are determined in MPL
    * explain how the truth values of compound propositions are determined by the truth values of their components in MPL
    * explain how the truth values of simple quantified propositions are determine in MPL
    * determine whether a proposition is true or false on a model

## required reading

* sections 9.1, 9.2, and 9.3 of chapter 9

# the semantics of logical languages

## the semantics of logical languages

* the guiding idea behind the semantics of any logical language:
* the values of the non-logical symbols are unconstrained: for any
    distribution at all of values to nonlogical symbols of the language,
    there is a possible scenario in which these symbols have those
    values.
* complex expressions---in particular, propositions---have their
    (truth) values determined by the values of their non-logical
    components, together with the laws of truth governing the logical
    symbols.

---

* in PL the nonlogical symbols are basic propositions.
* the appropriate kind of value for a basic proposition is a truth value.
* a scenario is a truth table row: an assignment of truth values to
    basic propositions.

---

* the limits of PL (again) ...
* there is a possible assignment of values to the basic propositions
    in the following argument on which the premises are all true and the
    conclusion false: All philosophers are drinkers. John is a
    philosopher. Therefore, John is a drinker.
* in MPL, these propositions are complex expressions, and their values
    are constrained.
* they are constrained in such a way that there is no possible
    assignment of values on which the premises of the argument are all
    true and the conclusion false.

---

* two questions ...
    * what are the values of the nonlogical symbols of MPL?
        * possible scenario (model) will then simply be any assignment
        of values to nonlogical symbols (the analogue of a truth-table
        row).
    * what are the laws of truth that determine the truth values of
    propositions of MPL on the basis of the values of their components?

# the semantics of atomic propositions in MPL

## the semantics of atomic propositions in MPL

* the value of a proposition is its **truth value**.
* the value of a name is its **referent**.
* the value of a predicate is its **extension**.

---

* the value of an atomic proposition---its truth value---is determined
    by the value of the name---the name's referent---and the value of
    its predicate---the predicate's extension.
* an atomic proposition is true if and only if the name's referent is
    in the predicate's extension.
* the value of a name, its referent, is an **object**.
* the value of a predicate, its extension, is a **set of objects**.

---

* an atomic proposition is true if and only if the name's referent, an
    object, is in the predicate's extension, a set of objects.
* $Fa$ is true if and only if the referent of $a$ is in the extension
    of $F$.

## the semantics of simple quantified propositions in MPL

* $\forall \underline{x}\underline{F}\underline{x}$ is true if and
    only if everything is in the extension of $\underline{F}$.
* but what do we mean by 'everything' here?
* we make the idea precise by introducing the notion of a **model**.

---

* a **model** consists of:
    1.  a domain (a set of objects)---this specifies what 'everything'
        means according to the model.
    2.  a specification of a referent (an object) for each name.
    3.  a specification of an extension (a set of objects) for each
        predicate.

---

* $\forall \underline{x}\underline{F}\underline{x}$ is true in a model
    if and only if everything in the domain of the model is in the
    extension of $\underline{F}$ on that model.
* $\exists \underline{x}\underline{F}\underline{x}$ is true in a model
    if and only if something in the domain of the model is in the
    extension of $\underline{F}$ on that model.

---

* some constraints on domains . . .
* the domain of a model must be a non-empty set.
* every name and predicate in the fragment must be assigned a referent
    or extension.
* the extension of each predicate must be a subset of the domain of
    the model.

---

* some constraints on domains (continued) . . .
* the referent of each name must be an object in the domain of the
    model.
* the extension of a predicate may be the empty set.
* the extension of a predicate may be the entire domain.
* different names may be assigned the same object as a referent.
* different predicates may be assigned the same set of objects as
    extensions.

---

* open wffs do not get truth values on models. $Px$ is not true or
    false, even once we specify an extension for $P$
* this is because
    the variable $x$ does not get a referent (in a model)
* only names get referents

# fragment and signature

## fragment and signature

* recall the syntax of MPL.
* there were an infinite number of names and predicates.
* if we start with a nonempty set of predicates and a (possibly empty)
    set of names we get a **fragment** of the full language of MPL.
* the wffs of this fragment are generated from the starting set of
    names/predicates using the exact same rules as in the syntax of the
    full language MPL.
* the starting set of nonlogical symbols (names/predicates) is called
    the **signature** of the fragment.
* note: at least one predicate must be in the fragment so that we can
    generate wffs.

---

* a **model** of a fragment of MPL consists of:
    1.  a domain (a set of objects)
    2.  a specification of a referent (an object) for each name in the
        fragment
    3.  a specification of an extension (a set of objects) for each
        predicate in the fragment

---

* here's a potential model of a fragment of MPL:
   * $\mathcal{M}_1$:
       * domain: {Alice, Ben, Carol}
       * referents: $a$: Alice
       * extensions: $P$: {Alice, Ben}
* this model meets the conditions on a model for a fragment of MPL.

---

* here's a potential model of a fragment of MPL:
    * $\mathcal{M}_2$:
        * domain: {Alice, Ben, Carol}
        * referents: $a$: Alice, $b$:
        * extensions: $P$: {Alice}
* this model does not meet the conditions on a model for a fragment of
    MPL. why not?

---

* here's a potential model of a fragment of MPL:
     * $\mathcal{M}_3$:
         * domain: {Alice, Ben, Carol}
         * referents: $a$: Alice
         * extensions: $P$: {Alice}, $Q$:
* this model does not meet the conditions on a model for a fragment of
    MPL. why not?

---

* here's a potential model of a fragment of MPL:
    * $\mathcal{M}_4$:
        * domain: {Alice, Ben, Carol}
        * referents: $a$: Danny
        * extensions: $P$: {Alice}
* this model does not meet the conditions on a model for a fragment of
    MPL. why not?

---

* here's a potential model of a fragment of MPL:
     * $\mathcal{M}_5$:
         * domain: {Alice, Ben, Carol}
         * referents: $a$: Alice
         * extensions: $P$: {Danny}
* this model does not meet the conditions on a model for a fragment of
    MPL. why not?

---

* here's a potential model of a fragment of MPL:
    * $\mathcal{M}_6$:
        * domain: {Alice, Ben, Carol}
        * referents: $a$: Alice
        * extensions: $P$: $\emptyset$
* does this model meet the conditions on a model for a fragment of
    MPL?

---

* here's a potential model of a fragment of MPL:
    * $\mathcal{M}_7$:
        * domain: {Alice, Ben, Carol}
        * referents: $a$: Alice
        * extensions: $P$: {Alice, Ben, Carol}
* does this model meet the conditions on a model for a fragment of
    MPL?

---

* here's a potential model of a fragment of MPL:
    * $\mathcal{M}_8$:
         * domain: {Alice, Ben, Carol}
         * referents: $a$: Alice, $b$: Alice
         * extensions: $P$: {Alice}
* does this model meet the conditions on a model for a fragment of
    MPL?

---

* here's a potential model of a fragment of MPL:
    * $\mathcal{M}_9$:
        * domain: {Alice, Ben, Carol}
        * referents: $a$: Alice
        * extensions: $P$: {Alice}, $Q$: {Alice}
* does this model meet the conditions on a model for a fragment of
    MPL?

# the semantics of connectives in MPL

## the semantics of connectives in MPL

* the treatment of the semantics of connectives carries over from PL

---

* rule for negation
    * $\lnot\alpha$ is true in $\mathcal{M}$ if and only if $\alpha$ is false in $\mathcal{M}$

---

* rule for conjunction
    * $(\alpha \land \beta)$ is true in $\mathcal{M}$ if and only if $\alpha$ and $\beta$ are true in $\mathcal{M}$

---

* rule for disjunction
    * $(\alpha \lor \beta)$ is true in $\mathcal{M}$ if and only if either $\alpha$ or $\beta$ or both are true in $\mathcal{M}$

---

* rule for conditional
    * $(\alpha \rightarrow \beta)$ is true in $\mathcal{M}$ if and only if either $\alpha$ is false or $\beta$ is true or both in $\mathcal{M}$

---

* rule for biconditional
    * $(\alpha \leftrightarrow \beta)$ is true in $\mathcal{M}$ if and only if either both $\alpha$ and $\beta$ are true or both $\alpha$ and $\beta$ are false in $\mathcal{M}$

---

* we have looked at simple cases of universally and existentially
    quantified propositions . . .

---

* rule for simple universally quantified propositions
    * $\forall \underline{x}\underline{F}\underline{x}$ is true in $\mathcal{M}$ if and only if everything in the domain of $\mathcal{M}$ is in the extension of $\underline{F}$ on $\mathcal{M}$

---

* rule for simple existentially quantified propositions
    * $\exists \underline{x}\underline{F}\underline{x}$ is true in in $\mathcal{M}$ if and only if something in the domain of $\mathcal{M}$ is in the extension of $\underline{F}$ on $\mathcal{M}$

# the semantics of MPL

## the semantics of MPL, stated formally

* see handout "the semantics of MPL"
* note: the following includes the general versions of the semantics
    for the quantifiers. We will look at this in the next lecture.

---

1.  $\underline{P}\underline{a}$ is true in $\mathcal{M}$ iff the
    referent of $\underline{a}$ in $\mathcal{M}$ is in the extension of
    $\underline{P}$ in $\mathcal{M}$.

2.  $\lnot \alpha$ is true in $\mathcal{M}$ iff $\alpha$ is false in
    $\mathcal{M}$.

3.  $(\alpha \land \beta)$ is true in $\mathcal{M}$ iff $\alpha$ and
    $\beta$ are both true in $\mathcal{M}$.

4.  $(\alpha \lor \beta)$ is true in $\mathcal{M}$ iff one or both of
    $\alpha$ and $\beta$ is true in $\mathcal{M}$.

5.  $(\alpha \rightarrow \beta)$ is true in $\mathcal{M}$ iff $\alpha$
    is false in $\mathcal{M}$ or $\beta$ is true in $\mathcal{M}$ or
    both.

6.  $(\alpha \leftrightarrow \beta)$ is true in $\mathcal{M}$ iff
    $\alpha$ and $\beta$ are both true in $\mathcal{M}$ or both false in
    $\mathcal{M}$ .

---

7.  $\forall \underline{x} \alpha (\underline{x})$ is true in
    $\mathcal{M}$ iff for every object $o$ in the domain of
    $\mathcal{M}$, $\alpha(\underline{a}/\underline{x})$ is true in
    $\mathcal{M}_{o}^{\underline{a}}$, where $\underline{a}$ is some
    name that is not assigned a referent in $\mathcal{M}$, and
    $\mathcal{M}_{o}^{\underline{a}}$ is a model just like $\mathcal{M}$
    except that in it the name $\underline{a}$ is assigned the referent
    $o$.

8.  $\exists\underline{x} \alpha (\underline{x})$ is true in
    $\mathcal{M}$ iff there is at least one object $o$ in the domain of
    $\mathcal{M}$ such that $\alpha(\underline{a}/\underline{x})$ is
    true in $\mathcal{M}_{o}^{\underline{a}}$, where $\underline{a}$ is
    some name that is not assigned a referent in $\mathcal{M}$, and
    $\mathcal{M}_{o}^{\underline{a}}$ is a model just like $\mathcal{M}$
    except that in it the name $\underline{a}$ is assigned the referent
    $o$.

# wrapping up

## this lecture

* in this lecture we looked at the semantics for uncomplicated propositions in MPL
* we introduced models in order to provide the semantics for MPL

## next lecture

* [lecture 15, the semantics of MPL, part 2](15_the_semantics_of_MPL_part2.html)







<!--

::: frame
-   Let's work through some examples...

![image](images/projector)
:::

::: frame
-   Here's a model:

> $\mathcal{M}_1$:\
> Domain: {Bill, Ben, Alice, Mary}\
> Extensions: $P$: {Bill, Ben, Alice, Mary}\

-   Evaluate the Following

> $\forall x Px$

> $\exists x Px$\

> $\forall x Px \rightarrow \exists x Px$\

> $\lnot(\forall x Px \lor \exists x Px)$\

> $(\forall x Px \land \exists x Px) \rightarrow \lnot \forall x Px$
:::

::: frame
-   Here's another model:

> $\mathcal{M}_2$:\
> Domain: {Bill, Ben, Alice, Mary}\
> Extensions: $P$: {Bill, Ben, Alice}\

-   Evaluate the Following

> $\forall x Px$

> $\exists x Px$\

> $\forall x Px \rightarrow \exists x Px$\

> $\lnot(\forall x Px \lor \exists x Px)$\

> $(\forall x Px \land \exists x Px) \rightarrow \lnot \forall x Px$
:::

::: frame
-   Here's yet another model:

> $\mathcal{M}_3$:\
> Domain: {Bill, Ben, Alice, Mary}\
> Extensions: $P$: $\emptyset$\

-   Evaluate the Following

> $\forall x Px$

> $\exists x Px$\

> $\forall x Px \rightarrow \exists x Px$\

> $\lnot(\forall x Px \lor \exists x Px)$\

> $(\forall x Px \land \exists x Px) \rightarrow \lnot \forall x Px$
:::

::: frame
-   Recap ...

-   Semantics of atomic propositions in MPL.

-   Semantics of simple quantified propositions in MPL.

-   Fragments and signatures of MPL.

-   Semantics of connectives of MPL.
:::

::: frame
-   Moving forward ...

-   The semantics of complex quantified propositions in MPL.
:::

-->
