---
title: lecture 05, the semantics of PL
subtitle: phil1012 introductory logic
---

# overview

## this lecture

* the semantics of PL
* truth tables for the connectives
* truth tables and truth functions
* how the truth value of a compound proposition is determined by the truth values of its components given an assignment of truth values to basic propositions

## learning outcomes

* after doing the relevant reading for this lecture, listening to the lecture, and attending the relevant tutorial, you will be able to:
    * produce the truth tables for the connectives negation, conjunction, disjunction, conditional, and biconditional from memory
    * determine the truth values of PL formulas given an assignment of truth values for their basic components
    * explain the general notion of a truth function and relate it to the truth tables for the connectives

## required reading

* :books: all of chapter 3

# the semantics of PL

## the semantics of PL

* we state the semantics in terms of truth tables for the connectives
* recall the idea behind **truth functional connectives**: when they are
used to make a compound proposition from other propositions, we can be sure
that the truth of the compound expression is determined by the truth or
falsity of the propositions it is made out of
* the semantics of PL is going to capture this idea

## a guiding assumption

* at the outset, we assume that every proposition is either true of false and not both true and false
* this assumption is known as **bivalence**
* given that every proposition is either true or false and not both true and false, we only need to consider two 'cases' for every proposition: the case in which it is true, and the case in which it is false
* the semantics for truth-functional connectives should tell us what the truth value of a compound proposition is for each possible combination of truth values for the propositions the connectives connect
* we represent these possibilities using **truth tables**

## negation

* the truth table for **negation**
* if the negand is true, the negation is false, and if the negand is false,
the negation is true
* if $P$ is true, $\lnot P$ is false, and if $P$ is false, $\lnot P$ is
true
* more generally, using well-formed formula variables:

::: ttable1

---------- -----------------
$\alpha$    $\lnot$$\alpha$
T                  F
F                  T
---------- -----------------

:::

* we only need to consider two cases for negation
* graphically, we can think of the two cases like this:
* when the 'input' is true:

![](negation_truth_function_true.png)

* the 'output' is false
* when the 'input' is false:


![](negation_truth_function_false.png)

* the 'output' is false

* okay, so much for negation. negation is pretty straightforward

## conjunction

* the truth table for **conjunction**
* if both the conjuncts are true, the conjunction is true. if either or both
are false, then the conjunction is false
* if $A$ and $B$ are true, $(A\land B$) is true. If either $A$ or $B$ is
false, $(A\land B)$ is false.
* more generally, using well-formed formula variables:

::: ttable2

---------- --------- --------------------------
$\alpha$   $\beta$    $(\alpha\land\beta)$
   T          T                     T
   T          F                     F
   F          T                     F
   F          F                     F
---------- --------- --------------------------

:::

* we have to consider 4 cases for conjunction
* graphically, we can think of the four cases like this:
* when both 'inputs' are true:


![](conjunction_true_true.png)

* the 'output' is true

* when the first 'input' is true, and the second is false:

![](conjunction_true_false.png)

* the 'output' is false
* when the first 'input' is false, and the second is true:

![](conjunction_false_true.png)

* the 'output' is false
* when both 'inputs' are false:

![](conjunction_false_false.png)

* the 'output' is false

* okay, so the relevant case to keep in mind for conjunction is the case where both conjuncts are true
* only then is the conjunction itself true

## disjunction

* the truth table for **disjunction**
* if either disjunct is true or both disjuncts are true, the disjunction is
true. if both disjuncts are false, the disjunction is false.
* if either $A$ or $B$ is true, $(A \lor B )$ is true. if both $A$ and
    $B$ are false, $(A \lor B)$ is false.
* more generally, using well-formed formula variables:

::: ttable2

---------- --------- -------------------------
$\alpha$   $\beta$    $(\alpha \lor \beta)$
   T          T                     T
   T          F                     T
   F          T                     T
   F          F                     F
---------- --------- -------------------------

:::

* we have to consider 4 cases for disjunction
* graphically, we can think of the four cases like this:
* when both 'inputs' are true:

![](disjunction_true_true.png)

* the 'output' is true
* when the first 'input' is true, and the second is false:

![](disjunction_true_false.png)

* the 'output' is true
* when the first 'input' is false, and the second is true:

![](disjunction_false_true.png)

* the 'output' is true
* when both 'inputs' are false:

![](disjunction_false_false.png)

* the 'output' is false
* okay, so the relevant case to keep in mind for disjunction is the case where both disjuncts are false
* only then is a disjunction false

## conditional

* the truth table for **conditional**
* if the antecedent is true and the consequent is false then the
    conditional is false. otherwise it is true.
* if $A$ is true and $B$ is false then $(A \rightarrow B)$ is false.
otherwise $(A \rightarrow B)$ is true.
* more generally, using well-formed formula variables:

::: ttable2

---------- --------- ---------------------------------
$\alpha$   $\beta$    $(\alpha \rightarrow \beta)$
  T          T                         T
  T          F                         F
  F          T                         T
  F          F                         T
---------- --------- ---------------------------------

:::

* we have to consider 4 cases for conditional
* graphically, we can think of the four cases like this:
* when both 'inputs' are true:

![](conditional_true_true.png)

* the 'output' is true
* when the first 'input' is true, and the second is false:

![](conditional_true_false.png)

* the 'output' is false
* when the first 'input' is false, and the second is true:


![](conditional_false_true.png)

* the 'output' is true
* when both 'inputs' are false:

![](conditional_false_false.png)

* the 'output' is true
* okay, so the relevant case to keep in mind for condition is the case where the antecedent is true and the consequent is false, the case where the first input is true, and the second input is false
* only then is a conditional false

## biconditional

* the truth table for **biconditional**
* if the right hand side and the left hand side are either both true
    or both false, then the biconditional is true. it is false
    otherwise.
* if $A$ and $B$ are either both true or both false, then
    $(A \leftrightarrow B )$ is true. otherwise $(A \leftrightarrow B )$
    is false.
* more generally, using well-formed formula variables:

::: ttable2

---------- --------- ------------------------------------
$\alpha$   $\beta$    $(\alpha \leftrightarrow \beta)$
   T          T                          T
   T          F                          F
   F          T                          F
   F          F                          T
---------- --------- ------------------------------------

:::

* we have to consider 4 cases for biconditional
* graphically, we can think of the four cases like this:
* when both 'inputs' are true:

![](biconditional_true_true.png)

* the 'output' is true
* when the first 'input' is true, and the second is false:


![](biconditional_true_false.png)

* the 'output' is false
* when the first 'input' is false, and the second is true:

![](biconditional_false_true.png)

* the 'output' is false
* when both 'inputs' are false:

![](biconditional_false_false.png)

* the 'output' is true
* okay, so the relevant cases to keep in mind for biconditional are the cases where both inputs are true and both inputs are false
* only in these cases is a biconditional true
* we will discuss the plausibility of these assumptions about the meanings
of the connectives, and their relation to ordinary English connectives,
later

# connectives and truth functions

## connectives and truth functions

* okay, so we've given the semantics of the connectives of PL using truth tables
* but what exactly have we achieved?
* to see this, let's look at the idea of a truth-function
* the general idea of a truth function is this . . .
* a **truth-function** is a function on {T, F}, that is, a function whose
inputs and outputs are truth values
* there are ever so many truth functions
* for this reason it is helpful to have a naming convention
* we name functions as follows: $f_1^1$, $f_2^1$, . . ., $f_1^2$, $f_2^2$ . . . .
    * superscripts represent the number of places of the function
(one-place, two-place, and so on)
    * subscripts represent index numbers to distinguish between different
functions with the same number of places
* some one-place truth functions

:::table

  input   output of $f_1^1$   output of $f_2^1$
-------- ------------------- -------------------
    T             T                   F
    F             T                   T

:::

* the matrix for $f_1^2$ should ring a bell. Consider the truth table for
$\lnot$ again:

::: ttable1

---------- -----------------
 $\alpha$    $\lnot$$\alpha$
  T                  F
  F                  T
---------- -----------------

:::

* truth tables effectively do two things at once: (i) they define a truth
function and (ii) state that the truth function is the meaning of the
connective
* we can separate the two steps and (i) define a truth function in the way
above and (ii) state that the truth function is the meaning of some
connective
* some two-place truth functions

:::table

 input   output of $f_1^2$   output of $f_2^2$   output of $f_3^2$
------- ------------------- ------------------- -------------------
 (T,T)           T                   F                   T
 (T,F)           F                   F                   T
 (F,T)           F                   T                   T
 (F,F)           T                   F                   F

:::

* the matrix for $f_3^2$ should ring a bell. consider the truth table for
$\lor$ again:

::: ttable2

---------- --------- -------------------------
$\alpha$   $\beta$    $(\alpha$$\lor$$\beta)$
  T          T                     T
  T          F                     T
  F          T                     T
  F          F                     F
---------- --------- -------------------------

:::

* so, instead of doing two things at once with truth tables for connectives, we could instead define a truth function and then declare that the truth function is the meaning of the connective
* finally, we are able to say more precisely what a truth functional connective is: it is any connective whose meaning can be specified as a truth function
* later in the unit we will ask whether we are able to express all possible truth-functions using the connectives of PL (it turns out that we can)

# truth values of complex propositions

## truth values of complex propositions

* consider the following complex proposition
    * $(\lnot P \land (Q \lor R))$
* how do we determine the truth value of this proposition?
* well, first we need to know what the truth values of the basic propositions are
* we need an **assignment** of truth values to basic propositions
* for example, let's say that $P$ is true, $Q$ is false, and $R$ is false
* we can write our assignment slightly more formally like this: 
  * {P = T, Q = F, R = F}
* now we can ask whether our proposition: 
  * $(\lnot P \land (Q \lor R))$
* is true on the assignment: 
  * {P = T, Q = F, R = F}
* we ask:
  * is $\lnot P$ true on the assignment {P = T, Q = F, R = F}?
  * is $(Q \lor R)$ true on the assignment {P = T, Q = F, R = F}?
  * is $(\lnot P \land (Q \lor R))$ true on the assignment {P = T, Q = F, R = F}?
* each step corresponds to a step in the construction table for the formula
* we apply the semantic rule for the relevant connective as we construct the formula

:::table

   step   wff constructed at this step       from steps/by clause
  ------ ---------------------------------- ----------------------
    1                 $P$ = T                       /(2i)
    2                 $Q$ = F                       /(2i)
    3                 $R$ = F                       /(2i)
    4              $\lnot P$ = F               1 /(2ii $\lnot$)
    5             $(Q \lor R)$ =  F           2,3 /(2ii $\lor$)
    6     $(\lnot P \land (Q \lor R))$ = F    4, 5 /(2ii $\land$)

:::

## lots of examples

* work through some examples yourself:
  * assignment: {P = T, Q = T, R = F}
  * $(\lnot P \land (Q \lor R))$
  * $(P \lor (Q \land R))$ 
  * $\lnot ((P \land Q) \rightarrow R)$

# wrapping up

## this lecture

* we looked at the semantics of PL
* we looked at the general idea of a truth function

## next lecture

* [lecture 6, uses of truth tables](06_uses_of_truth_tables.html)
