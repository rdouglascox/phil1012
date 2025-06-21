---
title: "lecture 13, lost in translation 2"
subtitle: phil1012 introductory logic
---

# overview

## this lecture

* a general strategy for determining how to translate a proposition using the connectives of PL
* issues arising with respect to the translation of conjunction

## learning outcomes

* after doing the relevant reading for this lecture, listening to the lecture, and attending the relevant tutorial, you will be able to:
    * pursue a general strategy for determining how to translate a proposition using the connectives of PL
    * translate sentences which are not obviously conjunctions into PL using the connective conjunction

## required reading

* section 6.2 of chapter 6

# a general strategy for translation

## a general strategy for translation

* at the end of section 6.1 of the textbook, there's a brief discussion of how to approach translating a proposition where we are unsure what connective is involved
* suppose, for instance you have a proposition which seems to be of the form $\alpha$ \* $\beta$ where \* is some two-place connective, but you aren't sure how to translate it

---

* well, one thing you can to is attempt to construct a truth table for the proposition
* for example, suppose we have the proposition "I went to bed, even though I was angry"
* the proposition appears to be of the form $\alpha$ \* $\beta$ where \* is some two-place connective
* but which connective is it?
* let's try to construct a truth table for the proposition

---

::: ttable2

--------  -------   ------------------
$\alpha$  $\beta$   $(\alpha * \beta)$
   T         T
   T         F
   F         T
   F         F
--------  -------   ------------------

:::

---

* now let's ask whether "I went to bed, even though I was angry" is true if "I went to bed" / $\alpha$ is false
* "I went to bed, even though I was angry" is false if "I went to bed" / $\alpha$ is false
* so we fill in our table:

---

::: ttable2

--------  -------   ------------------
$\alpha$  $\beta$   $(\alpha * \beta)$
   T         T
   T         F
   F         T              F
   F         F              F
--------  -------   ------------------

:::

---

* now let's ask whether "I went to bed, even though I was angry" is true if "I was angry" / $\beta$ is false
* "I went to bed, even though I was angry" is false if "I was angry" / $\beta$ is false
* so we fill in our table:

---

::: ttable2

--------  -------   ------------------
$\alpha$  $\beta$   $(\alpha * \beta)$
   T         T
   T         F              F
   F         T              F
   F         F              F
--------  -------   ------------------

:::

---

* finally, let's ask whether "I went to bed, even though I was angry" is true if both "I went to bed" / $\alpha$ and "I was angry" / $\beta$ are true
* "I went to bed, even though I was angry" is true if both "I went to bed" / $\alpha$ and "I was angry" / $\beta$ are true
* (remember that we are focussing on what is said, not what it implied or implicated)
* so we fill in our table:

---

::: ttable2

--------  -------   ------------------
$\alpha$  $\beta$   $(\alpha * \beta)$
   T         T              T
   T         F              F
   F         T              F
   F         F              F
--------  -------   ------------------

:::

---

* of course, this is just the table for conjunction, so we have discovered that the two-place connective here is conjunction
* so we would use conjunction in our translation

---

* things do not always work out so well, however
* suppose we use the method to determine which two-place connective to use to translate "I went to bed because I was angry"
* this is true only if both propositions which make it up are true
* so we can fill out our table like this:

---

::: ttable2

--------  -------   ------------------
$\alpha$  $\beta$   $(\alpha * \beta)$
   T         T
   T         F              F
   F         T              F
   F         F              F
--------  -------   ------------------

:::

---

* but now let us ask whether it is true if both propositions which make it up are true
* not necessarily
* I could have been angry, and I could have gone to bed, and yet, I might not have gone to bed because I was angry

---

* if we can't fill in the truth table, we can conclude that the connective is not a truth-functional connective
* if we can fill in the table, then we know what connective it is
* let's look at some more examples in connection with conjunction now

# issues with conjunction

## issues with conjunction

* we translate 'and' as a conjunction
* but we also translate 'but' as a conjunction
* why? and are we right to do so?

---

* consider:
    *  \(1\) Jane is tall but smart
    * $T$: Jane is tall
    * $S$: Jane is smart
* \(1\) is false if $T$ is false
* \(1\) is false if $S$ is false
* \(1\) is false if both $T$ and $S$ are false

---


* suppose: \(1\) is true if both $T$ and $S$ are true
* if so, then 'but' is equivalent to 'and'
    * $T$: Jane is tall
    * $S$: Jane is smart
    * $(T \land S)$
* but this fails to capture the sense in which 'Jane is tall but smart' conveys that being tall contrasts with being smart

---

* suppose: \(1\) is not necessarily true if both $T$ and $S$ are true
* if so, then 'but' isn't equivalent to 'and'
* instead, we might translate it as follows
    * $T$: Jane is tall
    * $S$: Jane is smart
    * $C$: Being tall contrasts with being smart
    * $((T \land S )\land C)$
* but this seems to be too strong
    * saying 'Jane is smart but tall' doesn't seem to be equivalent to saying 'Jane is tall and smart and
    being tall contrasts with being smart'

---

* solution . . .
    * claim that 'but' merely conventionally implicates a contrast
    * claim that 'but' and 'and' are truth-functionally equivalent

# wrapping up

## this lecture

* a general strategy for determining how to translate a proposition using the connectives of PL
* issues arising with respect to the translation of conjunction

## next lecture

* lecture 10, trees for PL

# overview

## this lecture

* issues arising with respect to translating conditional statements from English into PL

## learning outcomes

* after doing the relevant reading for this lecture, listening to the lecture, and attending the relevant tutorial, you will be able to:
    * explain some of the problems arising from the assumption that ordinary conditions are to be translated as material conditionals
    * distinguish between the unacceptability of certain conditions and their truth conditions

## required reading

* section 6.3 of chapter 6

# issues with conditional

## issues with conditional

* one of the biggest issues in philosophical logic and philosophy of language concerns how we should tranlate conditional statements into formal language like PL
* logicians and philosophers are fond of the idea that $\rightarrow$ adequately captures the truth conditions of ordinary conditionals
* we call $\rightarrow$ the **material conditional**.
* so the question is whether the material conditional provides an adequate translation for ordinary conditionals

---

* people write entire books defending the claim against evidence to the contrary
* the matter remains controversial
* it is important that you get a sense of the controversy
* but then forget about it for the rest of the course, and just assume that
$\rightarrow$ adequately captures ordinary language conditionals

## the truth table for conditional

* recall the truth table for conditional
* if the antecedent is true and the consequent is false then the conditional is
false. otherwise it is true.

. . .

::: ttable2

---------- --------- ---------------------------------
$\alpha$   $\beta$    ($\alpha$$\rightarrow$ $\beta$)
  T          T                         T
  T          F                         F
  F          T                         T
  F          F                         T
---------- --------- ---------------------------------

:::

---

* so far, we have assumed that the following sentences translate into the
following PL formula.
    * if the train breaks down, then I will be late.
    * I will be late if the train breaks down.
    * the train broke down, only if I am late.
* which we translate with a glossary like this:
    * $T$: The train breaks down
    * $L$: I am late
* using $\rightarrow$ we translate like this:
    * $*(T \rightarrow L)$

---

* let's see if we can do more to motivate translating the ordinary conditional as a material conditional

---

* consider:
    * (1) if the train breaks down, I will be late.
* with the following glossary
    * $B$: The train breaks down
    * $L$: I am late
* we can all agree that (1) is false if $T$ is true and $L$ is false.
* now let's ask:
   * is (1) true if $B$ is true and $L$ is true?
   * is (1) true if $B$ is false and $L$ is true?
   * is (1) true if $B$ is false and $L$ is false?

---


* now consider:
    * (2) if the train breaks down, the train breaks down.
* with the following glossary
    * $B$: The train breaks down
    * $L$: I am late
* (2) had better be true whether $B$ is false or whether $B$ is true.
* so we can agree that (2) is true if $B$ is true and $L$ is true
* and we can agree that (2) is true if $B$ is false and $L$ is false.
* now let's ask:
   * is (1) or (2) true if $B$ is false and $L$ is true?

---

* now let's ask:
   * is (2) true if $B$ is false and $L$ is true?

---

* well, it had better not be
* if (1) is false if $B$ is false and $L$ is true, then the conditional must have
the same truth table as the biconditional.
* this is absurd.
* so we can agree that (1) is true if $B$ is false and $L$ is true
* and now we have agreed that the ordinary conditional must have the truth table
we have given it if it is a truth functional connective at all

## proving equivalence

* let's have another go. this time we set out to prove the equivalence of the ordinary conditional.
* we do so in two parts
* first part: if "If $A$ then $B$" is true, then $A \rightarrow B$ is true.
* second part: If $A \rightarrow B$ is true, then "If $A$ then $B$".

## the first part

* if "If $A$ then $B$" is true, then $A \rightarrow B$ is true.
* proof:
    * suppose that $A \rightarrow B$ is false.
    * if $A \rightarrow B$ is false, then $A$ is true and $B$ is false.
    * so $A$ is true and $B$ is false.
    * but if $A$ is true and $B$ is false, then "If $A$ then $B$" is
    certainly false.
    * so if "If $A$ then $B$" is true, $A \rightarrow B$ must be true.

## the second part (version 1)

* if $A \rightarrow B$ is true, then "If $A$ then $B$".
* "proof" 1:
    * the proposition $A \rightarrow B$ is equivalent to $\lnot (A \land \lnot
B)$, so if $A \rightarrow B$ is true, $\lnot (A \land \lnot B)$ is true.
    * but from $\lnot (A \land \lnot B)$, "if $A$, then $B$" obviously
    follows. for given that it is not the case that both $A$ and that
    $\lnot B$, if $A$ is the case, then $\lnot B$, must not be the
    case---that is, $B$ must be the case.

## the second part (version 2)

* if $A \rightarrow B$ is true, then "If $A$ then $B$".
* "proof" 2:
    * the proposition $A \rightarrow B$ is equivalent to
    $(\lnot A \lor B)$, so if $A \rightarrow B$ is true,
    $(\lnot A \lor B)$ is true. ...
    * but from $(\lnot A \lor B)$, "if $A$, then $B$" obviously follows.
    For given that at least one of $\lnot A$ and $B$ is the case, if $A$
    is the case---that is, $\lnot A$ is not the case---then $B$ must be
    the case.

## a quick proof

* from Frank Jackson:

. . .

> Instead of saying "if it rains, then the match will be cancelled," one
> could have said, to much the same effect, "either it will not rain, or
> it will and the match will be cancelled:" and the latter is true if
> and only if either "it will rain" is false or "the match will be
> cancelled" is true; that is if and only if \[the material
> conditional\] is true. (Jackson 1991 p. 2)

---

* it is very plausible that if conditionals are truth-functional connectives,
then they are the connective we have chosen.
* but there are problems with the antecedent of this conditional!

---

* let's consider some of the absurd consequences of treating the ordinary
language conditional as $\rightarrow$:

---

* absurdity of assuming that if $C$ is true, then $A \rightarrow C$ is true.
    * if Sydney is in New Zealand, then 2+2=4!
    * if Sydney is in Australia, then 2+2=4!

---

* absurdity of assuming that if $A$ is false, then $A \rightarrow C$ is true.
   * if 2+2=5, then Sydney is in Australia!
   * if 2+2=5, then Sydney is in New Zealand!

---

* one might argue that all of these conditionals are intuitively false
* but according to the truth table for conditional, they should be true.
* what's missing is some kind of connection between the antecedent and
    the consequent.
* but truth functions do not seem to be able to provide the relevant
    connection.

---

* perhaps our intuitions concern the appropriateness of uttering these
conditionals, not their truth values.
* perhaps they are all true, although it would be in appropriate to utter them.
* perhaps it is appropriate to utter a conditional only if there is the relevant
kind of connection between the antecedent and the consequent?

## a gricean explanation

* for it to be appropriate to assert "If $A$, then $C$", one must believe it to
be true. (Maxim of Quality).
* so one must either believe (i) that $A$ is false, or (ii) that $C$ is true, or (iii) that both $A$ is true and $C$ is true.
* if (i), then asserting $\lnot A$ would be more informative than asserting "If
$A$, then $C$". so if you were to assert former rather than the latter you would
violate the Maxim of Quality.
* if (ii), then asserting $C$ would be more informative than asserting "If $A$,
then $C$". so if you were to assert former rather than the latter you would
violate the Maxim of Quality.
* if (iii) then, since you believe that $A$ is true, and believe "If $A$, then
$C$", you should believe that $C$. then asserting $A$ or $C$ or $A \lor C$ would
be more informative than assering 'If $A$, then $C$''.
* finally, if you believe that $B$ is false, then since you believe "If $A$,
then $C$", you should believe that $\lnot A$. then asserting $\lnot A$ would be
more informative than asserting "If $A$, then $C$".

---

* for it to be appropriate to utter 'If $A$, then $C$'' one must not be
confident that $A$ is true or that $B$ is false.
* yet, one must be confident that it is not the case that $A$ is true and $C$ is
false.
* but this is plausible only if is confident that there is some kind of
connection between $A$ and $C$.
* so, an utterance of "If $A$, then $C$" will implicate a connection between $A$
and $C$.
* this is what goes wrong in the examples on a Gricean explanation.

---

* but there are problems which can't be explained away in Gricean terms
* here's a logical entailment involving $\rightarrow$.
    * $(A \land B) \rightarrow C \models (A \rightarrow C) \lor (B \rightarrow C)$
* and here's an ordinary language equivalent:

. . .

> If you close switch A and switch B the light will go on. Hence, it is
> the case that either if you close switch A the light will go on, or
> that if you close switch B the light will go on. (Priest 2008 p. 14)

* this example is a problem for the Gricean explanation since we are not
confident in either the antecedent or the consequent

---

* here's another logical entailment involving $\rightarrow$.
    * $(A \rightarrow B) \land (C \rightarrow D) \models (A \rightarrow D) \lor (C \rightarrow B)$
* here's an ordinary language equivalent:

. . .

> If John is in Paris he is in France, and if John is in London he is in
> England. Hence, it is the case either that if John is in Paris he is
> in England, or that if he is in London he is in France. (Priest 2008
> p. 15)

* trouble!

---

* here's is one more logical entailment involving $\rightarrow$.
    * $\lnot (A \rightarrow B) \models A$
* here's an ordinary language equivalent:

. . .

> It is not the case that if there is a good god the prayers of evil
> people will be answered. Hence, there is a god. (Priest 2008 p. 15)

* trouble!

---

* this should be enough to give you a sense of the issues with translating ordinary conditionals using the material conditional
* but as I said earlier, while it is important for you to know the controvery, controversial matters won't make much of a difference to what you are doing in this course

# issues with 'only if'

## issues with 'only if'

* many students have trouble with 'only if'
* they get the antecedent and consequent confused
* they are tempted to translate 'A only if B' as $B$$\rightarrow$$A$
* let's see if we can set your thinking straight on this one

---

* why translate 'A only if B' as $A \rightarrow B$?
* well, we want to make sure that the following argument is valid:

. . .

::: arg

--------- -----------------------------------------
   P1.     John is home only if the lights are on.
   P2.     John is home.
   C1.     The lights are on.
--------- -----------------------------------------

:::

---

* to do so we must translate 'John is home only if the lights are on'
    as follows.
* glossary:
    * $J$ : John is home.
    * $L$: The lights are on.
* translation:
    * $(J \rightarrow L), J \therefore L$

---

* we are pretty certain that the argument is valid.
* so we must at
    least translate 'A only if B' as $A$$\rightarrow$$B$.
* the question is whether it *also* goes 'the other way'.
* but if it did, there would be no difference between 'John is home if
    and only if the lights are on' and 'John is home only if the lights
    are on'.
* so it can only go one way.
* and if it doesn't go the way we
    standardly assume, then it doesn't make a the argument at issue
    valid.

# wrapping up

## this lecture

* issues arising with respect to translating conditional statements from English into PL

## next lecture

* [lecture 14, the semantics of MPL part 1](14_the_semantics_of_MPL_part1.html)
