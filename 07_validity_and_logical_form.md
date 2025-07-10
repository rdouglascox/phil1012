---
title: lecture 07, validity and logical form
subtitle: phil1012 introductory logic
---

# overview

## this lecture

* in the last few lectures we've been examining the semantics of PL and truth tables
* in this lecture we look in more detail at the idea of the **logical form** of a proposition
* recall that logical form was central to the definition of **validity**

## learning outcomes

* after doing the relevant reading for this lecture, listening to the lecture, and attending the relevant tutorial, you will be able to:
    * identify the forms of propositions
    * identify instances of forms
    * identify the forms of arguments
    * identify instances of argument forms
    * explain how truth tables provide a test not only for necessary truth preservation but for validity

## required reading

* :books: all of chapter 5

# validity and logical form

## validity and logical form

* recall: an argument is **valid** if and only if, **in virtue of the form
of the argument**, it is impossible for its conclusion to be false if its
premises are all true
* our truth table test tells us whether it is possible for the conclusion to
be false if all of the premises are true
* does it tell us whether this is in virtue of the form of the
    argument?
* it turns out that the answer is yes, since we can show that every argument
with the same form is valid
* practical upshot: once we know that a given argument is valid, we know
that every other argument of the same form is valid, without having to do
truth tables for them individually

## the form of an argument

* what is the form of an argument?
* suppose we set out to test whether the following argument is valid:

::: arg

--------- -------------------------------------------
P1.       John is a philosopher
P2.       if John is a philosopher, then he drinks
C1.       John drinks
--------- -------------------------------------------

:::

* we begin by writing up our glossary:
    * $P$: John is a philosopher
    * $D$: John drinks
* we translate accordingly:
    * $P$, $(P \rightarrow D)$ $\therefore$ $D$
* we use a truth table to test for validity:


::: ttable2

----- ----- ----- ---------------------- -----
 $P$   $D$    $P$   $(P \rightarrow D)$   $D$
 T     T       T             T             T
 T     F       T             F             F
 F     T       F             T             T
 F     F       F             T             F
----- ----- ----- ---------------------- -----

:::

* great, now suppose we set out to test whether the following argument is
valid:

::: arg

--------- --------------------------------------------
P1.       Jane is a philosopher
P2.       if Jane is a philosopher, then she smokes
C1.       Jane smokes
--------- --------------------------------------------

:::

* we begin by writing up our glossary:
    * $J$: Jane is a philosopher
    * $S$: Jane smokes
*   we translate accordingly:
    * $J$, $(J \rightarrow S)$ $\therefore$ $S$
* and we use a truth table to test for validity:

:::ttable2

----- ----- ----- --------------------- -----
$J$   $S$    $J$   $(J\rightarrow S)$    $S$
T     T       T             T             T
T     F       T             F             F
F     T       F             T             T
F     F       F             T             F
----- ----- ----- --------------------- -----

:::

* after a while we might start to feel that the whole process is a bit
laborious and redundant
* don't these arguments have something in common which means that if we know
that one is valid, we know the other is, and vice versa?
* yep, these arguments are instances of the same **form**
* how can we make the notion of form more precise?

# abstracting from content: from propositions to forms

## from propositions to forms

* consider the following proposition:
  * $(A \land (B \rightarrow \lnot C))$
* what is its form?
* there are many correct answers ranging from very coarse-grained to very
fine-grained
* at its most coarse-grained it is just a proposition:
  * $\underline{(A \land (B \rightarrow \lnot C))}$
* so it has the following form: 
  * $\alpha$
* at a more fine-grained level of description it is a conjunction:
  * $(\underline{A }  \land  \underline{(B \rightarrow \lnot C)})$
* so it has the following form: 
  * $(\alpha \land \beta)$
* at an even more fine-grained level of description it is a conjunction
whose second conjunct is a conditional:
  * $(\underline{A } \land \underline{(\underline{B} \rightarrow \underline{\lnot C})})$
* so it has the following form:
  * $(\alpha \land (\beta \rightarrow \gamma))$
* at the most fine-grained level of description it is a conjunction whose
second conjunct is a conditional, whose consequent is a negation:
  * $(\underline{A }  \land  \underline{(\underline{B} \rightarrow \lnot \underline{C})})$
* so it has the following form:
  * $(\alpha \land (\beta \rightarrow \lnot \gamma))$
* propositions do not have a single form
* they have many forms ranging from the coarse-grained to the fine-grained

# instances: from forms to propositions

## instances: from forms to propositions

* consider the following logical form:
    * $(\alpha \leftrightarrow (\lnot \beta \land \alpha))$
* a **logical form** is like a formula, except that it has variables in the place of formulas
* given a logical form, we can ask: what propositions have this form? We
call such propositions **instances** of the form
* an instance of a logical form can be obtained by replacing the variables
with propositions
* all occurrences of the same variable must be replaced by the same
proposition
* for example . . .
    * $(\alpha \leftrightarrow (\lnot \beta \land \alpha))$
        * $(A \leftrightarrow (\lnot B \land A))$
        * $(B \leftrightarrow (\lnot E \land B))$
        * $((A \rightarrow B) \leftrightarrow (\lnot E \land (A \rightarrow B)))$
        * $(B \leftrightarrow (\lnot B \land B))$
        * $((A \rightarrow B) \leftrightarrow (\lnot (A \rightarrow B) \land (A \rightarrow B)))$
* but not . . .
    * $(\alpha \leftrightarrow (\lnot \beta \land \alpha))$
        * $(A \leftrightarrow (\lnot B \land B))$
        * $(B \leftrightarrow (\lnot E \land D))$
        * $((A \rightarrow B) \leftrightarrow (\lnot E \land B))$
* two propositions share a form when they are both instances of it
* it doesn't make sense to say that they have the same form, they may
    both be instances of some form and not both instances of some other
    form
* okay, now we have a better idea of the forms of a proposition
* and we have a better idea of the propositions which are instances of forms
* we can now generalise this idea to the forms of an argument

# the form(s) of an argument

## the form(s) of an argument

* consider the following argument form:
    * $\alpha$, $(\alpha \rightarrow (\beta \rightarrow \alpha))$ $\therefore \beta \rightarrow \alpha$\
* an **argument form** is just like an argument except that it has variables in
  the place of propositions
* given an argument form, we can ask: what arguments have this form?
* we call such arguments **instances** of the form
* for example . . .
    * $\alpha$, $\alpha \rightarrow (\beta \rightarrow \alpha)$ $\therefore \beta \rightarrow \alpha$
        * $P$, $P \rightarrow (Q \rightarrow P)$, $\therefore Q \rightarrow P$\
        * $(R \lor \lnot Q)$, $(R \lor \lnot Q) \rightarrow (P \rightarrow (R \lor \lnot Q))$, $\therefore P \rightarrow (R \lor \lnot Q)$
* an argument can be an instance of more than one form
* for example . . .
    * $P$, $(P \rightarrow (Q \rightarrow P))$ $\therefore Q \rightarrow P$
        * $\alpha$, $(\alpha \rightarrow (\beta \rightarrow \alpha))$, $\therefore (\beta \rightarrow \alpha)$
        * $\alpha$, $(\alpha \rightarrow \gamma$), $\therefore (\beta \rightarrow \alpha)$
* an argument can be an instance of more than one form
* it is important to keep this in mind when we discuss validity and
    form

# validity and form

## validity and form

* now that we have a precise understanding of the forms of an argument, to what use can we put the idea?
* well, we can use it to make our notion of validity more precise
* and we can appeal to the form of an argument in arguing that it is valid
* we begin by introducing notions analogous to validity and invalidity, which are properties of arguments, for argument forms
* we define the properties **valid\*** and **invalid\*** of **argument
    forms**
* these are distinct from the properties **valid** and **invalid** of
**arguments**
* an argument form is **valid\*** if and only if there is no row in which the premises are true and the conclusion false
* an argument form is **valid\*** if and only if there is no instance of the
form in which the premises are true and the conclusion false
* an argument form is **invalid\*** if and only if there is a row in
    which the premises are true and the conclusion false
* we test for **validity\*** of an argument form using truth tables as
    before


::: ttable2

---------- --------- ---------- ------------------------------ ---------
$\alpha$   $\beta$    $\alpha$   $(\alpha \rightarrow \beta)$   $\beta$
T          T             T                    T                    T
T          F             T                    F                    F
F          T             F                    T                    T
F          F             F                    T                    F
---------- --------- ---------- ------------------------------ ---------

:::


* now, a very nice feature of **valid\*** argument forms is that every instance of a **valid\*** argument form is valid argument
* consider the following argument:
    * $((A \land C) \rightarrow ((B \lor D) \rightarrow E))$, $(A \land C)$, $\therefore ((B \lor D) \rightarrow E)$\
* we need a truth table with 32 rows since we have five distinct basic
    propositions!
* but wait! this argument is an instance of the form:
    * $(\alpha \rightarrow \beta)$, $\alpha$ $\therefore \beta$
* and this form is **valid\*** (we just did the truth table for it)
* so we can immediately conclude that the argument is valid
* hint: unless stated otherwise, it is *always* permissible to save yourself time on a problem set or an exam by appealing to the form of an argument in proving its validity
* we will look at examples in the tutorials

# invalidity and form

## invalidity and form

* :warning: careful: it is not the case that every instance of an **invalid\*** argument
    form is an invalid argument
* the following is an **invalid\*** argument form:
    * $\beta$ $\rightarrow$ $\alpha$, $\alpha$ $\therefore \beta$
* but the following is an instance of the form:
   * $(A \rightarrow A)$, $A$ $\therefore$ $A$
* and this argument is valid
* we can see this by doing the truth
    table, or by noting that this is *also* an instance of a valid form
* indeed, we can distinguish between **A-properties** and **S-properties**
of arguments and argument forms
* every instance of a form with an A-property has that A-property. not so
with the S-properties.

:::table

A-property         S-property
------------------ -------------------
validity           invalidity
logical truth      non-logical truth
equivalence        inequivalence
unsatisfiability   satisfiability

:::

* in other words, there are shortcuts available for establishing A-properties, but no shortcuts for S-properties

# wrapping up

## this lecture

* validity and logical form
* the forms of propositions
* the instances of forms
* valid\* argument forms

## next lecture

* [lecture 08, functional completeness](08_functional_completeness.html)
