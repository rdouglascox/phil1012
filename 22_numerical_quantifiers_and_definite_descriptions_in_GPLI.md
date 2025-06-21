---
title: lecture 22, numerical quantifiers and definite descriptions in GPLI
subtitle: phil1012 introductory logic
---

# overview

## this lecture

* two final topics concerning translations into GPLI
* numerical quantifiers and definite descriptions in GPLI

## learning outcomes

* after doing the relevant reading for this lecture, listening to the lecture, and attending the relevant tutorial, you will be able to:
    * identify numerical quantifiers and definite descriptions in ordinary language
    * translation propositions involving numerical quantifiers and definite descriptions into GPLI

## required reading

* section 13.5 and 13.6 of chapter 13

# the expressive power of GPLI

## the expressive power of GPLI

* GPLI is a powerful language. It allows us to express things like this:
   * there is at least one Tasmanian Tiger
   * there are at least two Tasmanian Tigers
   * there are exactly three Tasmanian Tigers
   * there are at most three Tasmanian Tigers
* these expressions involve **numerical quantifiers** like 'at least one', 'at
least two', 'exactly three', 'at most three'

---

* we will look at each of the following numerical quantifiers in turn
   * at least *n*
   * at most *n*
   * exactly *n*

## at least *n*

* suppose we want to translate 'There is at least one Tasmanian Tiger' into
GPLI
* we start with a glossary like this:
    * $Tx$: $x$ is a Tasmanian Tiger
* then we look for a formula which is true if there is at least one Tasmanian
Tiger, and false if there is not at least one Tasmanian Tiger
* any guesses?

---

* yes, it's: $\exists x Tx$
* this is true if there is at least one Tasmanian Tiger and, it is false if
there is not at least one Tasmanian Tiger
* so 'at least one' is just equivalent to the ordinary existential quantifier

---

* suppose we want to translate 'There are at least two Tasmanian Tigers' into
GPLI
* we start with a glossary like this:
    * $Tx$: $x$ is a Tasmanian Tiger
* then we look for a formula which is true if there are at least two Tasmanian
Tigers, and false if there are not at least two Tasmanian Tigers
* any guesses?

---

* well, it's not: $\exists x Tx$
* this is true if there are at least two Tasmanian Tigers. but it is not false
if there are not at least two Tasmanian Tigers. it would be true if there were
only one Tasmanian Tiger

---

* it's not this either: $\exists x Tx \land \exists y Ty$
* why not?
* this just makes the claim that something is a Tasmanian Tiger two times
* in terms of models: we could pick the same tiger each time to make the
conjunction true

---

* it is not this either: $\exists x \exists y (Tx \land Ty)$
* why not?
* again, this just makes the claim that something is a Tasmanian Tiger two times
* in terms of models: we could pick the same tiger each time to make the
conjunction true

---

* how do we ensure that there are at least two Tasmanian Tigers?
* we make sure we must pick a *different* tiger each time to make the proposition true
* we use a negated identity claim like this to do so:
    * $\exists x \exists y (Tx \land Ty \land x \neq y)$
* this is true if there are at least two Tasmanian Tigers. and it is false if
there are not at least two Tasmanian Tigers

---

* okay, now that we've hit upon the relevant strategy for translating 'at least
*n*' claims, let's see if we can extend it

---

* suppose we want to translate 'There are at least three Tasmanian Tigers' into
GPLI
* we start with a glossary like this:
    * $Tx$: $x$ is a Tasmanian Tiger
* then we look for a formula which is true if there are at least three Tasmanian
Tigers, and false if there are not at least three Tasmanian Tigers
* any guesses?

---

* well, it's not:
    * $\exists x \exists y \exists z (Tx \land Ty \land Tz)$
* this is true if there are at least three Tasmanian Tigers
* but it is not false if there are not at least three Tasmanian Tigers
* it would be true if there were only one Tasmanian Tiger!

---

* it's not this either:
    * $\exists x \exists y \exists z (Tx \land Ty \land Tz \land x \neq y \land y \neq z)$
* we could pick the same tiger twice to make the conjunction true

---

* how do we ensure that there are at least three Tasmanian Tigers?
* we make sure we must pick a *different* tiger each time to make the
conjunction true
* like this:
    * $\exists x \exists y \exists z (Tx \land Ty \land Tz \land x \neq y \land  x \neq z \land  y \neq z)$
* this is true if there are at least three Tasmanian Tigers
* and it is false if there are not at least three Tasmanian Tigers

---

* get the pattern?
* you've got to ensure that we must pick *n* different tigers to make the
conjunction true for the relevant *n*

---

* but don't be fooled
* yes, there are three non-identity claims in 'at least three'
* but there were none in 'at least one' and only one in 'at least two'
* and there are six non-identity claims in 'at least four'
    * $\exists x \exists y \exists z \exists w (Tx \land Ty \land Tz \land Tw \land x \neq y \land x \neq z \land x \neq w \land y \neq z \land y \neq w \land z \neq w)$
* the number of quantifiers is a better guide in the case of 'at least *n*'

---

* okay, that's all there is to translating claims involving the numerical quantifer 'at least *n*' into GPLI

## at most *n*

* suppose we want to translate 'There is at most one Tasmanian Tiger' or 'There
is no more than one Tasmanian Tiger' into GPLI
* we start with a glossary like this:
    * $Tx$: $x$ is a Tasmanian Tiger
* then we look for a formula which is true if there are no Tasmanian Tigers or
there is one Tasmanian Tiger, and false if there are more than one Tasmanian
Tigers
* any guesses?

---

* in this case, there are two approaches we might take

---

* one approach captures the idea that for any two things you pick from the
domain, if they are Tasmanian Tigers they are one and the same thing
* here is our translation then:
    * $\forall x \forall y((Tx \land Ty) \rightarrow x = y)$
* this is true if there are no Tasmanian Tigers or there is one Tasmanian Tiger,
and it is false if there are more than one Tasmanian Tigers

---

* the other approach captures the idea that you cannot pick two things from the
domain which are both Tasmanian Tigers and not identical to each other
* here is our translation then:
    * $\lnot \exists x \exists y (Tx \land Ty \land x \neq y)$
* this is true if there are no Tasmanian Tigers or there is one Tasmanian Tiger,
and it is false if there is more than one Tasmanian Tiger

---

* you might find one approach more natural than the other
* they are equivalent!
* let's see if we can extend the approach

---

* suppose we want to translate 'There are no more than two Tasmanian Tigers'
into GPLI
* we start with a glossary like this:
    * $Tx$: $x$ is a Tasmanian Tiger
* then we look for a formula which is true if there are no Tasmanian Tigers or
there is one Tasmanian Tiger or there are two Tasmanian Tigers, and false if
there are more than two Tasmanian Tigers. Any guesses?

---

* again, there are two approaches we might take

---

* one approach captures the idea that for any three things you pick from the
domain, if they are Tasmanian Tigers at least two of them are one and the same
thing
* here is our translation then:
    * $\forall x \forall y \forall z((Tx \land Ty \land Tz) \rightarrow (x = y \lor x = z \lor y = z))$
* this is true if there are no Tasmanian Tigers or there is one Tasmanian Tiger
or there are two Tasmanian Tigers, and it is false if there are more than two
Tasmanian Tigers

---

* the other approach captures the idea that you cannot pick three things from
the domain which are all Tasmanian Tigers where no two things are identical to
each other
* here is our translation then:
    * $\lnot \exists x \exists y \exists z (Tx \land Ty \land Tz \land x \neq y \land x \neq z \land y \neq z)$
* this is true if there are no Tasmanian Tigers or there is one Tasmanian Tiger
or there are two Tasmanian Tigers, and it is false if there are more than two
Tasmanian Tigers

---

* again, you might find one approach more natural than the other
* they are equivalent!

---

* don't be fooled! the number of quantifiers is not a guide to the numerical
    quantifier involved in these translations
* you need two quantifiers for 'at most one', three quantifiers for 'at most
two', and so on

## exactly *n*

* suppose we want to translate 'There is exactly one Tasmanian Tiger' into GPLI
* think about what 'there is exactly one Tasmanian Tiger' means
* any guesses as to how we might translate the proposition into GPLI?

---

* well, if there is exactly one Tasmanian Tiger, then there is at least one
Tasmanian Tiger, and at most one Tasmanian Tiger
* exactly *n* = at least *n* $\land$ at most *n*
* there is exactly one Tasmanian tiger:
    * $\exists x Tx \land \ldots \ldots \forall x \forall y((Tx \land Ty)
\rightarrow x = y)$

---

* suppose we want to translate 'There are exactly two Tasmanian Tigers' into
GPLI
* well, if there are exactly two Tasmanian Tigers, then there are at least two
Tasmanian Tigers, and at most two Tasmanian Tigers
* exactly *n* = at least *n* $\land$ at most *n*
* there is exactly one Tasmanian tiger:
    * $\exists x \exists y (Tx \land Ty \land x \neq y) \land \ldots \ldots
\forall x \forall y \forall z((Tx \land Ty \land Tz) \rightarrow (x = y \lor x =
z \lor y = z))$

---

* that translation is a little unwieldy
* there's a more refined way of expressing the same thing
* it captures the idea that if there are exactly two Tasmanian Tigers, then you
can pick two things from the domain which are not identical and are such that
any third thing you pick is a Tasmanian Tiger if and only if the third thing is
identical to one or the other of the first things you picked!
* here is the translation based on that thought
    * $\exists x  \exists y (x \neq y \land \forall z(Tz \leftrightarrow (z = x
\lor z = y)))$

# definite descriptions in GPLI

## definite descriptions in GPLI

* do we have a way of translating sentence like this 'the man is tall'? in any of our formal languages?
* well so far, we have treated 'the man' as if it were a name (or we have avoided it entirely)

---

* exactly how we should go about translating definite descriptions like 'the man' is a matter of controvery
* there is a famous approach, due to Bertrand Russell, which treats definite descriptions as quantifiers
* the idea is that 'the man is tall' means something like there 'there is exactly one man and that man is tall'

---

* we already have all of the tools we need to translate 'there is exactly one man and that man is tall'
* start with a glossary:
    * $Mx$ : $x$ is a man
    * $Tx$ : $x$ is tall
* and translate accordingly
    * $\exists x (\forall y (My \leftrightarrow x = y) \land Tx)$

---

* see the textbook for more complicated cases involving definite descriptions

---

# wrapping up

## this lecture

* numerical quantifiers and definite descriptions in GPLI
* the introduction of identity into our formal language has led to quite the increase in expressive power
* we are now able to capture the logical form of a decent portion of English



