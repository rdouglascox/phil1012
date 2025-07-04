---
title: lecture 06, uses of truth tables
subtitle: phil1012 introductory logic
---

# overview

## this lecture

* the uses of truth tables
* constructing truth tables
* using truth tables to test for various logical properties

## learning outcomes

* after doing the relevant reading for this lecture, listening to the lecture, and attending the relevant tutorial, you will be able to:
    * construct truth tables for arguments, single propositions, pairs of propositions and sets of propositions
    * use truth tables to determine whether an argument is valid, providing a counterexample if not
    * use truth tables to determine whether an proposition is a tautology, a contradiction, or neither
    * use truth tables to determine whether pairs of formulas are jointly
satisfiable, equivalent, contradictory, or contraries.
    * use truth tables to
determine whether sets of propositions are jointly satisfiable


## required reading

* :books: all of chapter 4

# truth tables for complex propositions

## truth tables for complex propositions

* sometimes we want to know the truth value of a complex proposition for every
  possible assignment of truth values to basic propositions.
* or this purpose we construct a **truth table** for the complex proposition.
* each row of a truth table corresponds to a possible assignment of truth
  values to basic propositions
* we set up our table so that the rows in the columns on the left correspond to the possible assignments of truth values to basic propositions
* for example, if we have the basic propositions $P$ and $Q$, the rows of the table will correspond to the four possible assignments of truth values to $P$ and $Q$


:::{.ttable2}

----- ----- ------
$P$   $Q$    ...
T     T      ...
T     F      ...
F     T      ...
F     F      ...
----- ----- ------

:::

* we add the proposition we are interested in evaluating in the rightmost column
* suppose we want to construct a table for $\lnot(P \land \lnot Q)$ 

:::{.ttable2} 

----- ----- --------------------------
$P$    $Q$    $\lnot(P \land \lnot Q)$
T      T                
T      F                
F      T                 
F      F                 
----- ----- --------------------------

:::

* we proceed as in the case of a single assignment, calculating the truth value of the more complex propositions in terms of the truth value of their
constituents
* until we have the values of the complex proposition for each possible
  assignment of values to the basic propositions

:::{.ttable2} 

----- ----- -----------------------------
$P$    $Q$    $\lnot(P \land \lnot Q)$
T      T             T   
T      F             F  
F      T             T      
F      F             T       
----- ----- -----------------------------

:::

# truth tables for multiple propositions

## truth tables for multiple propositions

* we can also construct tables for multiple propositions
* we calculate the possible truth values for every possible assignment of
  values to basic propositions
* for any basic proposition which occurs in any formula

:::{.ttable2}

----- ----- ----------------------- -------------------------------
$P$   $Q$    $(P \rightarrow Q)$     $\lnot(P \land \lnot P )$
T     T                T                           T
T     F                F                           T
F     T                T                           T
F     F                T                           T
----- ----- ----------------------- -------------------------------

:::

# general points about drawing truth tables 

* let's reflect on 

## general points about drawing truth tables 

* one distinct wff variable (alpha)
* column 1 has one T and one F

:::{.ttable1}

---------- -----
$\alpha$    ...
T            F
F            T
---------- -----

:::

* two distinct wff variables (alpha beta)
* the previous matrix occurs in the top right-hand corner of the matrix


:::{.ttable2}

---------- --------- -----
$\alpha$   $\beta$    ...
T          T          ...
T          F          ...
F          T          ...
F          F          ...
---------- --------- -----

:::

* three distinct wff variables (alpha, beta, gamma)
* the previous matrix occurs in the top right-hand corner of the matrix

:::{.ttable3}

---------- --------- ---------- -----
$\alpha$   $\beta$   $\gamma$    ...
T          T         T           ...
T          T         F           ...
T          F         T           ...
T          F         F           ...
F          T         T           ...
F          T         F           ...
F          F         T           ...
F          F         F           ...
---------- --------- ---------- -----

:::

* four distinct wff variables (alpha, beta, gamma, and delta)
* the previous matrix occurs in the top right-hand corner of the matrix

::: ttable4

---------- --------- ---------- ---------- -----
$\alpha$   $\beta$   $\gamma$   $\delta$    ...
T          T         T          T           ...
T          T         T          F           ...
T          T         F          T           ...
T          T         F          F           ...
T          F         T          T           ...
T          F         T          F           ...
T          F         F          T           ...
T          F         F          F           ...
F          T         T          T           ...
F          T         T          F           ...
F          T         F          T           ...
F          T         F          F           ...
F          F         T          T           ...
F          F         T          F           ...
F          F         F          T           ...
F          F         F          F           ...
---------- --------- ---------- ---------- -----

:::

* in general ...

:::table

 number of basic components   number of rows
---------------------------- ----------------
             1                      2
             2                      4
             3                      8
             4                      16
             5                      32
             6                      64
            ...                    ...
            *n*                   2^*n*^

:::


* the right-most column always alternates T, F, and so on
* then TT, FF, and so on
* then TTTT, FFFF, and so on
* then TTTTTTTT, FFFFFFFF, and so on
* always doubling the Ts and Fs
* basic propositions are sorted alphabetically
* for the problem sets and exam . . .
    * make sure you set up your tables correctly
    * keep your rows and columns neat
    * show the truth values of all sub-formulas

# using truth tables to test for validity

## using truth tables to test for validity

* recall the definition of validity . . .
* an argument is **valid** if and only if, in virtue of the form of the
  argument, it is impossible for its conclusion to be false if its premises are
  all true
* in PL, a possibility is an assignment of truth values to the basic
  propositions
* a joint truth table for a group of propositions shows all of the possible
  ways of making the propositions or true or false
* the question we put to a truth table in order to determine whether
   an argument is valid it this:
    * is there a row on which all of the premises are true and the
    conclusion is false?
* if so, the argument is invalid. if not, then it is valid.
* is this argument valid?

:::{.arg}

--------- ------------------------------------------------
  P1.     Either John is not a philosopher or he drinks
  P2.     John is a philosopher
  C1.     John drinks
--------- ------------------------------------------------

:::

* we begin by translating the argument into PL
* here's our glossary:
    * $P$: John is a philosopher
    * $D$: John drinks
* here's our translation:
    * $(\lnot P \lor D), P \therefore D$
* now consider the joint truth table for the premises and the conclusion.

:::{.ttable2}

----- ----- ---------------------- ------ -----
$P$   $D$    $(\lnot P \lor D)$     $P$    $D$
T     T              T               T      T
T     F              F               T      F
F     T              T               F      T
F     F              T               F      F
----- ----- ----- ---------------------- ----- -----

:::

* is there a row on which the premises are true and the conclusion false?
* if so, the argument is invalid. if not, then it is valid.
* is it valid?
* consider another argument. is this argument valid?

:::{.arg}

--------- --------------------------------------------
  P1.     Either John is a philosopher or he drinks
  P2.     John drinks
  C1.     John is a philosopher
--------- --------------------------------------------

:::

* we begin by translating the argument into PL
* here's our glossary:
    * $P$: John is a philosopher
    * $D$: John drinks
* here's our translation:
    * $( P \lor D), D \therefore P$
* now consider the joint truth table for the premises and the conclusion


:::{.ttable2}

----- ----- -------------- ----- -----
$P$   $D$    $(P \lor D)$   $D$   $P$
T     T           T          T     T
T     F           T          F     T
F     T           T          T     F
F     F           F          F     F
----- ----- -------------- ----- -----

:::

* is there a row on which the premises are true and the conclusion false?
* if so, the argument is invalid. if not, then it is valid.
* if an argument is invalid, then it is possible for all the premises to be
  true and for the conclusion to be false.
* a **counterexample** is an assignment of truth values to basic propositions
  on which the premises are true and the conclusion is false.
* look back at the matrix. $P$ is true and $D$ is false on the relevant row.

:::{.ttable2}

------- ------- -------------------- ------ -------
$P$     $D$      $(P \lor D)$           $D$    $P$
T       T                T              T      T
T       F                T              F      T
**F**   **T**          **T**          **T**  **F**
F       F                F              F     F
------- ------- -------------------- ------ -------

:::

* we write a counterexample as follows:
    * $P$ = F, $D$ = T
* what if there is a row where both premises are true and the conclusion is
  also true?

:::{.ttable2}


------- ------- -------------------- ------ -------
$P$     $D$      $(\lnot P \lor D)$    $D$    $P$
**T**   **T**          **T**          **T**  **T**
T       F                T              F      T
F       T                T              T      F
F       F                F              F      F
------- ------- -------------------- ------ -------

:::

* this does not show that the argument is valid. (recall the definition of
  validity)

## some examples 

* here are some arguments that are instances of common argument forms for propositional logic. check for yourself that they are valid: 
  * modus ponens
      * $P, (P \rightarrow Q) \therefore Q$ 
  * modus tollens 
      * $P \rightarrow Q, \lnot Q \therefore \lnot P$
  * disjunctive syllogism  
    * $P \lor Q, \lnot P \therefore Q$
  * hypothetical syllogism 
    * $P \rightarrow Q, Q \rightarrow R \therefore P \rightarrow R$ 
  * constructive dilemma 
    * $(P \rightarrow Q), (R \rightarrow S), (P \lor R) \therefore (Q \lor S)$ 
  * conditional proof 
    * $P \therefore (Q \rightarrow P)$
  * reductio ad absurdum 
    * $\lnot P \rightarrow (Q \land \lnot Q) \therefore P$

# using truth tables to test single propositions

## using truth tables to test single propositions

* we can use truth tables to determine whether a single propositions is:
    * a tautology
    * a contradiction
    * a non-contradiction
    * satisfiable
* intuitively, a proposition is a tautology if it *must* be true
    * e.g. the ball is round or the ball is not round
* a proposition is a **tautology** if and only if it is true on every row of its
  truth table

:::{.ttable1}

---- --------------------
$P$   $(P \lor \lnot P)$
 T           T
 F           T
---- --------------------

:::

* we can use a truth table to determine whether a proposition is a tautology: we check whether it is true on every row of its truth table
* intuitively, a proposition is a contradiction if it *cannot* be true
    * e.g. the ball is round and the ball is not round
* a proposition is a **contradiction** if and only if it is false on every row
  of its truth table


:::{.ttable1}

----- --------------------
$P$   $(P \land \lnot P)$
  T            F
  F            F
----- --------------------

:::

* we can use a truth table to determine whether a proposition is a contradiction: we check whether it is false on every row of its truth table
* intuitively, a proposition is satisfiable if it *can* be true
* a proposition is **satisfiable** if and only if it is true in some or all rows
  of its truth table

:::{.ttable1}

----- ---------------------------
$P$   $(P \rightarrow \lnot P)$
  T               F
  F               T
----- ---------------------------

:::

* we can use a truth table to determine whether a proposition is satisfiable: we check whether it is true on some row of its truth table
* contradictions and satisfiable propositions are opposites
    * if a proposition is not a contradiction, then it is satisfiable
    * if a proposition is not satisfiable, then it is a contradiction
* contradictions and tautologies are not opposites
    * a proposition may be neither a contradiction nor a tautology
* satisfiable propositions and tautologies are not opposites
    * a tautology is a satisfifiable proposition

:::table

values in truth table   type of proposition
----------------------- -----------------------------
T in every row          **tautology**
F in every row          **contradiction**
T in some or all rows   **satisfiable proposition**
F in some or all rows   **nontautology**

:::

## some example tautologies 

* here are some common propositional logic tautologies 
  * $P \lor \lnot P$ 
  * $P \rightarrow P$  
  * $(P \land Q) \rightarrow P$  
  * $(P \rightarrow Q) \rightarrow (\lnot P \lor Q)$   
  * $(P \lor Q) \rightarrow (Q \lor P)$   
  * $(P \land Q) \rightarrow (Q \land P)$    
  * $(P \lor Q) \rightarrow (Q \lor P)$ 
  * $(P \land (Q \lor R)) \rightarrow ((P \land Q) \lor (P \land R))$  
  * $(P \lor (Q \land R)) \rightarrow ((P \lor Q) \land (P \lor R))$  
  * $(P \land (Q \lor R)) \leftrightarrow ((P \land Q) \lor (P \land R))$  

# using truth tables to test pairs of propositions

## using truth tables to test pairs of propositions

* we can use truth tables to determine whether a pair of propositions are:
    * equivalent or not equivalent
    * jointly satisfiable or not jointly satisfiable
    * contrary or contradictory
* intuitively, a pair of propositions are equivalent if it is not possible for one proposition to be true without the other being true and vice versa
* a pair of propositions are **equivalent** if and only if they have the same value
  in every row of the truth table

:::{.ttable2}

----- ----- --------------------- --------------------
 $P$   $Q$   $(P \rightarrow Q)$   $(\lnot P \lor Q)$
  T     T             T                    T
  T     F             F                    F
  F     T             T                    T
  F     F             T                    T
----- ----- --------------------- --------------------

:::

* we can use a truth table to determine whether a pair of propositions are equivalent: we check whether they have the same value on every row of the truth table
* intuitively, a pair of propositions are jointly satisfiable if they can both be true together
* a pair of propositions are **jointly satisfiable** if and only if there is some
  row of the truth table in which they are both true

:::{.ttable2}

----- ----- -------------------------- --------------
$P$   $Q$   $\lnot(P \rightarrow Q)$   $(P \lor Q)$
  T     T               F                    T
  T     F               T                    T
  F     T               F                    T
  F     F               F                    F
----- ----- -------------------------- --------------

:::


* we can use a truth table to determine whether a pair of propositions are jointly satisfiable: we check whether there is some row of the truth table on which they are both true
* intuitively, a pair of propositions are jointly unsatisfiable if they cannot both be true together
* a pair of propositions are **jointly unsatisfiable** if and only if there is no
  row of the truth table in which they are both true

:::{.ttable2}

----- ----- -------------------------- --------------
$P$   $Q$   $\lnot(P \lor Q)$           $(P \lor Q)$
  T     T               F                    T
  T     F               F                    T
  F     T               F                    T
  F     F               T                    F
----- ----- -------------------------- --------------

:::

* we can use a truth table to determine whether a pair of propositions are jointly unsatisfiable: we check whether they have the same value on every row of the truth table
* note: as the example above shows, two satisfiable propositions may be jointly unsatisfiable
* when a pair or propositions are jointly unsatisfiable they can be classified either as contradictories or contraries
* let's consider the two cases now
* intuitively, a pair of propositions are contradictory when if one is true the other is false and vice versa
* a pair of propositions are **contradictory** if and only if they are jointly
  unsatisfiable and there is no row of the truth table in which they are both
  false

:::{.ttable2}

----- ----- --------------- --------------------
 $P$   $Q$   $(P \land Q)$   $\lnot(P \land Q)$
  T     T          T                 F
  T     F          F                 T
  F     T          F                 T
  F     F          F                 T
---- ----- --------------- --------------------

:::

* we can use a truth table to determine whether a pair of propositions are contradictory: we check whether their truth values are opposed on every row of the truth table 
* if a pair of propositions are contradictory, we can always infer from the falsity of one proposition to the truth of the other
* but this will not always be the case when a pair of propositions are jointly unsatisfiable
* why?
* they might both be false
* intuitively, a pair of propositions are (merely) contraries if they are jointly unsatisfiable, but aren't contradictory: they can't be true together, but they can be false together
* a pair of propositions are **contraries** if and only if they are jointly
  unsatisfiable and there is some row in which both are false

:::{.ttable2}

----- ----- --------------------- --------------------
 $P$   $Q$   $(P \land \lnot P)$   $\lnot(P \land Q)$
  T     T             F                    F
  T     F             F                    T
  F     T             F                    T
  F     F             F                    T
----- ----- --------------------- --------------------

:::

* we can use a truth table to determine whether a pair of propositions are contraries: we check whether there is no row of the truth table on which they are both true and some row on which they are both false

:::table

values in truth table                                type of propositions
---------------------------------------------------- ---------------------------
same value in every row                              **equivalent**
some row in which both T                             **jointly satisfiable**
no row in which both T                               **jointly unsatisfiable**
j-unsat and no row in which both F                   **contradictory**
j-unsat and some row in which both F                 **contraries**

:::

## some examples  

* here are some common propositional logic equivalences with their common names 
  * $(P \land Q) \equiv (Q \land P)$: commutativity of conjunction  
  * $(P \lor Q) \equiv (Q \lor P)$: commutativity of disjunction   
  * $(P \land (Q \land R)) \equiv ((P \land Q) \land R)$: associativity of conjunction   
  * $(P \lor (Q \lor R)) \equiv ((P \lor Q) \lor R)$: associativity of disjunction    
  * $(P \land (Q \lor R)) \equiv ((P \land Q) \lor (P \land R))$: distributivity of conjunction over disjunction   
  * $(P \lor (Q \land R)) \equiv ((P \lor Q) \land (P \lor R))$: distributivity of disjunction over conjunction   
  * $\lnot (P \land Q) \equiv (\lnot P \lor \lnot Q)$: De Morgan's law for conjunction   
  * $\lnot (P \lor Q) \equiv (\lnot P \land \lnot Q)$: De Morgan's law for disjunction    
  * $(P \rightarrow Q) \equiv (\lnot P \lor Q)$: material implication   
  * $(P \leftrightarrow Q) \equiv ((P \rightarrow Q) \land (Q \rightarrow P))$: material equivalence   

# using truth tables to test sets of propositions

## using truth tables to test sets of propositions

* equivalence and joint satisfiability can be generalised from pairs of
  propositions to sets of propositions in obvious ways
* I will leave equivalence as an exercise for you
* but let us look at the satisfiability and unsatisfiability of sets of
  propositions
* intuitively, a set of propositions is satisfiable if they can all be true
  together
* a set of propositions is **satisfiable** if and only if there is some row in
  the truth table on which all the members of the set are true
* intuitively, a set of propositions is unsatisfiable if they cannot all be
  true together
* set of propositions is **unsatisfiable** if and only if there is no row in
  the truth table on which all the members of the set are true
* we can use truth tables to test for the satisfiability of sets of
  propositions
* suppose we want to know whether {$(P \rightarrow Q)$, $(P \land Q)$, $(P \lor
  Q)$} is satisfiable
* we draw up a joint truth table as follows:


:::{.ttable2}

----- ----- --------------------- --------------- --------------
 $P$   $Q$   $(P \rightarrow Q)$   $(P \land Q)$   $(P \lor Q)$
  T     T             T                  T              T
  T     F             F                  F              T
  F     T             T                  F              T
  F     F             T                  F              F
----- ----- --------------------- --------------- --------------

:::

* now, the notion of the satisfiability of a set of propositions will play a central role in the course going forward
* notice that the truth table not only tells us that the set of propositions are satisfiable, it also provides assignments on which the set of propositions are satisfiable
* as noted earlier, truth tables get unwieldy very quickly: what if we have 5 basic propositions?
* might there be a more efficient method for testing the satisfiability of sets of propositions?
* might there be a more efficient search procedure for assignments on which the propositions are satisfiable?
* yes: truth trees

:::table

values in truth table     set of propositions
------------------------- ---------------------
some row on which all T   **satisfiable**
no row on which all T     **unsatisfiable**

:::

# wrapping up

## this lecture

* truth tables for complex propositions and multiple propositions
* using truth tables to test for various logical properties
* single propositions
    * tautologies
    * contradictions
    * satisfiable propositions
    * noncontradictions
* pairs of propositions
    * equivalence
    * joint satisfiability
    * joint unsatisfiability
    * contradictories
    * contraries
* sets of propositions
    * joint satisfiability
    * joint unsatisfiability

## names for metavariables 

* if, like me, you never learned about Greek letters at school, you might benefit from a quick primer 
  * $\alpha$: alpha 
  * $\beta$: beta 
  * $\gamma$: gamma  
  * $\delta$: delta  
  * $\epsilon$: epsilon   
  * $\zeta$: zeta  
  * $\eta$: eta 
  * $\theta$: theta   
  * $\iota$: iota   
  * $\kappa$: kappa  
  * $\lambda$: lambda  
  * $\mu$: mu  
  * $\nu$: nu  
  * $\xi$: xi  
  * $\pi$: pi  
  * $\rho$: rho  
  * $\sigma$: sigma  
  * $\tau$: tau  
  * $\upsilon$: upsilon  
  * $\phi$: phi   
  * $\chi$: chi   
  * $\psi$: psi   
  * $\omega$: omega   

## next lecture

* [lecture 07, validity and logical form](07_validity_and_logical_form.html)
