---
title: "lecture 11, the formal language MPL"
subtitle: phil1012 introductory logic
---

# overview

## this lecture

* an introduction to the formal language MPL
* the limitations of PL and the motivation for MPL
* an introduction to the notions of names, predicates, variables, and quantifiers
* translation of propositions into MPL

## learning outcomes

* after doing the relevant reading for this lecture, listening to the lecture, and attending the relevant tutorial, you will be able to:
    * explain what MPL allows us to do that we cannot do in PL
    * translate propositions with a simple subject-predicate form into MPL
    * translate existential and universal propositions into MPL
    * translate propositions involving restricted quantification into MPL

## required reading

* sections 8.1, 8.2, 8.3 of chapter 8

# beyond propositional logic

## beyond propositional logic

* propositional logic is great
* but there are some arguments which seem to be such that, in virtue of their
form, their premises can't all be true and their conclusion false

---

* consider the following argument

. . .

::: arg

--------- --------------------------------
  P1.     all philosophers are drinkers
  P2.     John is a philosopher
  C1.     John is a drinker
--------- --------------------------------

:::

* a valid argument


---

* let's translate the argument into PL
* we have the following glossary
   * $P$: all philosophers are drinkers
   * $J$: John is a philosopher
   * $D$: John is a drinker
* and the following translation
   * $P$, $J$, $\therefore D$
* but this argument is invalid in PL!

---

* we must go beyond PL!
* for the remainder of the course we will go beyond PL three times over
   * MPL: names, one-place predicates, quantifiers, and variables.
   * GPL: names, many-place predicates, quantifiers, and variables.
   * GPLI: names, many-place predicates, quantifiers, variables, and the
identity predicate.
* for now: MPL

# names and predicates

## names and predicates

* introducing names and predicates
* consider: 'John is a philosopher'
    * this expresses a basic proposition. but let's now take a look at the
    constituents of this sentence
* there is a **name** 'John', which **refers** to an individual thing,
    namely John
* there is a **predicate**, 'is a philosopher' which is **satisfied**
    by certain individual things if and only if they have the property
    of being a philosopher

---

* the symbol for a **name** in MPL is a lowercase letter, $a$, $b$, $c$, $d$,
    $e$, . . ., $r$, $s$, $t$
    * not including the last six letters in the
    alphabet, $u$, $v$, $w$, $x$, $y$, $z$ (these will be used for something else)
* the symbol for a **predicate** in MPL is an uppercase letter,
    $A$, $B$, $C$, $D$, . . ., $X$, $Y$, $Z$ (no reservations here.)
* don't confuse sentences letters from PL with predicate letters from
    MPL!
* and note that there are no sentence letters in PL!

# glossaries in MPL (preliminary)

## glossaries in MPL (preliminary)

* glossaries in MPL work like glossaries in PL
* the give meanings for the non-logical symbols of MPL
* unlike PL whose non-logical symbols were sentence letters, the non-logical
symbols of MPL are names and predicates

---

* we give the meanings of names in our MPL glossaries like this:
    * $b$: Bruce
    * $j$: Jane
    * $m$: *Australian Materialism*
    * $a$: The author of *Australian Materialism*
* we give the meanings of predicates in our MPL glossaries like this:
    * $P$: is a philosopher
    * $B$: is a book
* this is provisional. we'll see a better way of doing glossaries from
    MPL below.

# atomic propositions

## atomic propositions

* an **atomic proposition** is a proposition made up from one name and one
predicate.
* we translate the atomic proposition 'Bruce is a philosopher' like this:
    * $Pb$
* we translate the atomic proposition 'The author of *Australian Materialism* is
a philosopher' like this:
    * $Pa$
* we translate the atomic proposition '*Australian Materialism* is a book' like
this:
    * $Bm$

## connectives in MPL

* we retain all the connectives of PL in MPL.
* we translate a disjunction like 'Bruce is a philosopher or Jane is a
    philosopher' like this:
    * $(Pb \lor Pj)$
* we translate a conjunction like 'Bruce is a philosopher and Jane is
    a philosopher' like this:
    * $(Pb \land Pj)$

---

* we translate a conditional like 'If Bruce is a philosopher, then
    Jane is a philosopher' like this:
    * $Pb \rightarrow Pj$
* we translate a biconditional like 'Bruce is a philosopher if and
    only if Jane is a philosopher' like this:
    * $(Pb \leftrightarrow Pj)$
* we translate a negation like 'Bruce is not a philosopher' like this:
    * $\lnot Pb$

## variables and quantifiers

* introducing **variables** and **quantifiers**
* how should we translate the following?
    * everyone is a philosopher
    * someone is a philosopher
    * no one is a philosopher

---

* not like this:
* here's my glossary:
    * $e$: everyone
    * $s$: someone
    * $n$: no one
* here's my translation:
    * $e$ is a philosopher
    * $s$ is a philosopher
    * $n$ is a philosopher

* this is wrong!
* expressions like 'everyone', 'someone', and 'no one' are not names.

---

* expressions like 'someone' and 'everyone' are **quantifiers**
* 'someone' is an **existential quantifier**
* 'everyone' is a **universal quantifier**

---

* how should we think about quantified propositions then? what do they
    say?
* well, 'Everything is a philosopher' says, roughly, that every
    *thing* is such that *it* is a philosopher
* and 'Something is a philosopher' says, roughly, that some *thing* is
    such that *it* is a philosopher

---

* to put it slightly more formally (but still informally):
* well, 'Everything is a philosopher' says, roughly, that every *x* is such that
*x* is a philosopher
* and 'Something is a philosopher' says, roughly, that some *x* is
    such that *x* is a philosopher

---

* we use the variable *x* in this informal presentation.
* in MPL the symbols for *individual variables* are $u$, $v$, $w$,
    $x$, $y$, $z$
* using variables, we can get closer to what we are after.

---

* given our glossary for 'is a philosopher' we have:
     * every $x$ is such that $Px$
     * some $x$ is such that $Px$

---

* we introduce two new symbols in MPL which mean 'every $x$ is such
    that' and 'some $x$ is such that'
    * $\forall$$x$ (universal quantifier)
    * $\exists$$x$ (existenial quantifier)

---

* using quantifiers and variables we can translate 'Everything is a
    philosopher' and 'Something is a philosopher' as follows:
    * everything is a philosopher
        * $\forall x Px$
    * something is a philosopher
        * $\exists x Px$

---

* okay, we are getting somewhere
* but we set out to translate the following
    * everyone is a philosopher
    * someone is a philosopher
    * no-one is a philosopher
* 'everything is a philosopher' doesn't mean the same thing as
    'everyone is a philosopher'
* things get just a little bit more complicated
* but before turning to this complication . . .

## glossaries in MPL (official)

* with the introduction of variables, here is a new convention for
    writing glossaries for predicates
    * $P$$x$: $x$ is a philosopher
    * $B$$x$: $x$ is a book
* notice how one variable occurs before the colon and immediately
    after the predicate letter, and another variable occurs after it in
    the place in the sentence where a name might go

# restricted quantification

## restricted quantification

* back to the complication . . .
* how should we translate 'every philosopher is a drinker' and 'some
    philosopher is a drinker'?
* let's think it through carefully

---

* think about 'every philosopher is a drinker'
* you can think of it as saying that every x is such that
    [if]{.underline} x is a philosopher, [then]{.underline} x is a
    drinker.
* so we translate it as follows:
    * $\forall x (Px  \rightarrow Dx)$
* where:
   * $Dx$: $x$ is a person
   * $Px$: $x$ is a philosopher
* you can think of the predicate in the antecent of the conditional as
    'restricting' the things over which we are quantifying

---

* now think about 'Some philosopher is a drinker'
* you can think of it as saying that some x is such that x is a
    philosopher [and]{.underline} x is a drinker
* so we translate it as follows:
    * $\exists x (Px  \land Dx)$
* where:
    * $Dx$: $x$ is a person
    * $Px$: $x$ is a philosopher
* you can think of the predicate in the first conjunct of the conjunction as
'restricting' the things over which we are quantifying

---

* notice that for restricted universal quantification we use a conditional, and
the antecedent of the conditional does the restricting, and that for restricted
existential quantification we use a conjunction, and one conjunct does the
restricting.
* don't confuse the two
* this says that everything is a philosopher and a drinker:
    * $\forall x (Px  \land Dx)$
* and this says that there is something which is either not a
    philosopher or is a drinker.
    * $\exists x (Px \rightarrow Dx)$
* it is true if anything is not a philosopher or if anything is a drinker!

# wrapping up

## this lecture

* an introduction to the formal language MPL
* the limitations of PL and the motivation for MPL
* an introduction to the notions of names, predicates, variables, and quantifiers
* translation of propositions into MPL

## next lecture

* [lecture 12, the syntax of MPL](12_the_syntax_of_MPL.html)

<!--

# translation examples

## translation examples

* let's have a go at translating the following
   * all round things are special
* first we set up our glossary
   * Gx : x is grey
   * Rx: x is round.
   * Sx: x is special.
* now think about which quantifier we need
* and think about any restrictions we might need on the quantifier
* here's our translation
    * $\forall x (Rx \rightarrow Sx)$
* not this:
    * $\forall x (Rx \land Sx)$!

---

* now let's have a go at translating the following
   * some round things are special
* first we set up our glossary
   * Gx : x is grey
   * Rx: x is round
   * Sx: x is special
* now think about which qyantifier we need
* and think about any restrictions we might need on the quantifier
* here's our translation
    * $\exists x (Rx \land Sx)$

---

* how might we translate the following?
   * some round things are round and some are special
* first we set up our glossary
    * Gx : x is grey
    * Rx: x is round
    * Sx: x is special
* now think about main connective
* and then think about the form of the parts
* here's our translation
    * $\exists x (Rx \land Rx) \land \exists x(Rx \land Sx)$

---

* here is another sentence to translate
    * everything is round or non-round
* our glossary
   * Gx : x is grey
   * Rx: x is round
   * Sx: x is special
* now think about what quantifier we need here
* do we need a restriction?
* how do we translate the material in the scope of the quantifier?
    * $\forall x (Rx \lor \lnot Rx)$

---

* here is yet another sentence to translate
    * everything is round or everything is non-round
* here's a glossary
    * Gx : x is grey
    * Rx: x is round
    * Sx: x is special
* think about what the main connective is here
* and then think about the form of the parts
* here's our translation
   * $\forall x Rx \lor \forall x \lnot Rx$

---

* here is another one
    * nothing is round
* here's a glossary
    * Gx : x is grey
    * Rx: x is round
    * Sx: x is special
* think about what quantifier we need here
* here is our translation
    * $\lnot \exists x R x$

---

* let's try to translate the following
   * everything is non-round
* here's a glossary
    * Gx : x is grey
    * Rx: x is round
    * Sx: x is special
    * Ex: x is empty
* think about what quantifier we need
* think about how to translate what's in the scope of the quantifier
* here's our translation
   *  $\forall x \lnot R x$

---

* now let's try to translate the following
    * something isn't round
* here's our glossary
    * Gx : x is grey
    * Rx: x is round
    * Sx: x is special
* think about what quanfier we need
* and about the scope of the quantifier
* here's our translation
   *  $\exists x \lnot R x$

---

* here is yet another sentence to translate
    * not everything is round
* here's our glossary
    * Gx : x is grey
    * Rx: x is round
    * Sx: x is special
* think about the main connective
* think about the quantifier we need
* here's our translation
    * $\lnot \forall x R x$

---

::: frame
-   Here's a glossary:

> Gx : x is grey.\
> Rx: x is round.\
> Sx: x is special.\

-   Translate the following into MPL using this glossary:

> Something is round but not special.

> $\exists x (Rx \land \lnot Sx)$
:::

::: frame
-   Here's a glossary:

> Gx : x is grey.\
> Rx: x is round.\
> Sx: x is special.\

-   Translate the following into MPL using this glossary:

> Something is neither round nor special.

> $\exists x (\lnot Rx \land \lnot Sx)$

> $\exists x \lnot(Rx \lor Sx)$
:::

::: frame
-   Here's a glossary:

> Gx : x is grey.\
> Rx: x is round.\
> Sx: x is special.\

-   Translate the following into MPL using this glossary:

> All round things are grey or special.

> $\forall x (Rx \rightarrow (Gx \lor Sx))$
:::

::: frame
-   Here's a glossary:

> Gx : x is grey.\
> Rx: x is round.\
> Sx: x is special.\

-   Translate the following into MPL using this glossary:

> All round things that are not grey are special.

> $\forall x ((Rx \land \lnot Gx) \rightarrow Sx)$
:::

::: frame
-   Here's a glossary:

> Gx : x is grey.\
> Rx: x is round.\
> s: Sydney Tower

-   Translate the following into MPL using this glossary:

> Sydney Tower is grey and round.

> $Gs \land Rs$
:::

::: frame
-   Here's a glossary:

> Rx: x is round.\
> s: Sydney Tower

-   Translate the following into MPL using this glossary:

> If Sydney Tower is round, then something is round.

> $Rs \rightarrow \exists x Rx$
:::

::: frame
-   Here's a glossary:

> Gx : x is grey.\
> s: Sydney Tower

-   Translate the following into MPL using this glossary:

> If Sydney Tower is grey, then something is.

> $Gs \rightarrow \exists x Gx$
:::

::: frame
-   Here's a glossary:

> Sx: x is special.\

-   Translate the following into MPL using this glossary:

> Everything is special.

> $\forall x Sx$
:::

::: frame
-   Here's a glossary:

> Sx: x is special.\
> Px: x is a person.\

-   Translate the following into MPL using this glossary:

> Everyone is special.

> $\forall x (Px \rightarrow Sx)$
:::

::: frame
-   Here's a glossary:

> Mx: x smells.

-   Translate the following into MPL using this glossary:

> Something smells.

> $\exists x Mx$
:::

::: frame
-   Here's a glossary:

> Mx: x smells.\
> Px: x is a person.

-   Translate the following into MPL using this glossary:

> Someone smells.

> $\forall x (Px \rightarrow Mx)$
:::

::: frame
-   Here's a glossary:

> Bx: x is a bird.\
> Fx: x is flies.

-   Translate the following into MPL using this glossary:

> Only birds fly.

> $\forall x (Fx \rightarrow Bx)$
:::

::: frame
-   Here's a glossary:

> Wx: x loves walking.\
> Px: x is a postman.

-   Translate the following into MPL using this glossary:

> A love of walking is necessary for being a postman.

> $\forall x (Px \rightarrow Wx)$
:::

::: frame
-   Here's a glossary:

> Wx: x loves walking.\
> Px: x is a postman.

-   Translate the following into MPL using this glossary:

> A love of walking is sufficient for being a postman.

> $\forall x (Wx \rightarrow Px)$
:::

::: frame
-   Recap ...

-   Shortcomings of PL.

-   Monadic Predicate Logic (MPL)

-   Names and predicates

-   Variables and Quantifiers

-   Restricted Quantifiers

-->
