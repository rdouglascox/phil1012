---
title: "lecture 08, functional completeness"
subtitle: phil1012 introductory logic
---

# overview

## this lecture

* some reflection on PL
* functional completeness: the idea that a given set of connectives is able to express all possible truth functions
* are the connectives of PL functionally complete?

## learning outcomes

* after doing the relevant reading for this lecture, listening to the lecture, and attending the relevant tutorial, you will be able to:
    * explain what it means for a set of connectives to be functionally complete
    * define one set of connectives in terms of another set of connectives
    * determine whether a given set of connectives is functionally complete

## required reading

* :books: section 6.6 of chapter 6

# functional completeness

## functional completeness

* are our five connectives, in some sense, sufficient?
* are there formulas with truth conditions that cannot be constructed using our
  five connectives? 
* are there any truth functions that cannot be expressed by some combination of
  our five connectives?
* consider the equivalence of $(A \rightarrow B)$ and $(\lnot A \lor B)$

::: ttable2

---  ---  ---------------------- -----------------------
$A$  $B$       $(A \to B)$           $(\lnot A \lor B)$
 T    T              T                      T
 F    T              T                      T 
 T    F              F                      F
 F    F              T                      T
---  ---  ---------------------- -----------------------

:::

* we can construct a formula with the truth conditions of $(A \rightarrow B)$ using
  $\lnot$ and $\lor$
* we can express the truth function expressed by $\rightarrow$ using $\lnot$ and
  $\lor$
* so there's a sense in which we don't really need $\rightarrow$
* we could just use $\lnot$ and $\lor$ instead of $\rightarrow$
* but now consider the truth table for a connective not included in our five,
  $\veebar$

::: ttable2

---  ---  ----------------------
$A$  $B$      $(A \veebar B)$
 T    T             F
 F    T             T
 T    F             T
 F    F             F
---  ---  ----------------------

:::

* can we construct a formula with the same truth conditions using connectives
  taken from our original five?
* it turns out that we can

::: ttable2

---  ---  ---------------------- ----------------------------------
$A$  $B$      $(A \veebar B)$       $\lnot (A \leftrightarrow B)$
 T    T             F                             F 
 F    T             T                             T 
 T    F             T                             T 
 F    F             F                             F 
---  ---  ---------------------- ----------------------------------

:::

* so there a sense in which we don't need to add $\veebar$
* we can already express with our five connectives what we can express with $\veebar$
* can we do what we just did for $\rightarrow$ and $\veebar$ for any possible connective?
* can we express any possible truth function using just our five connectives?
* it turns out that we can
* with its five connectives, $\lnot$, $\land$, $\lor$, $\rightarrow$, and
  $\leftrightarrow$, PL has the resources to construct a formula with any truth
  conditions whatsoever
* for any possible truth table, there is a formula of PL with that truth table
* our five connectives can express any possible truth function
* we call this feature, **functional completeness**
* a set of connectives is **functionally complete** if we can define all
  possible connectives from the connectives in that set
* let's prove it!
* first, we'll get clearer on what it means to define one connective in terms of
 other connectives
* then we'll get clearer on the space of possible connectives
* then we'll prove that the set of connectives use in PL is functionally
  complete

# defining one connective in terms of others

## defining one connective in terms of others

* we can define some connectives in terms of other connectives
* we show that a form using the connective to be defined is equivalent to a
  form using only the other connectives
* recall that two forms are **equivalent** if and only if they have the same
  truth value on every row of the truth table
* lets consider some examples
* the connective $\rightarrow$ can be defined in terms of $\lnot$ and $\lor$

::: ttable2

---------- --------- -------------------------------- --------------------------------
 $\alpha$   $\beta$   $(\alpha$$\rightarrow$$\beta)$   $(\lnot$$\alpha$$\lor$$\beta)$
      T          T                    T                                T
      T          F                    F                                F
      F          T                    F                                F
      F          F                    T                                T
---------- --------- -------------------------------- --------------------------------

:::

* the connective $\leftrightarrow$ can be defined in terms of $\rightarrow$ and
  $\land$

::: ttable2

---------- --------- ------------------------------------ -----------------------------------------------------------------------
 $\alpha$   $\beta$   $(\alpha$$\leftrightarrow$$\beta)$    $((\alpha$$\rightarrow$$\beta)\land(\beta$$\rightarrow$$\alpha))$
    T          T                      T                                                      T
    T          F                      F                                                      F
    F          T                      T                                                      T
    F          F                      T                                                      T
---------- --------- ------------------------------------ -----------------------------------------------------------------------

:::

* the connective $\land$ can be defined in terms of $\lor$ and $\lnot$

::: ttable2

---------- --------- -------------------------- ----------------------------------------------
 $\alpha$   $\beta$   $(\alpha$$\land$$\beta)$    $\lnot(\lnot$$\alpha$$\lor$$\lnot$$\beta)$
    T          T                 T                                    T
    T          F                 F                                    F
    F          T                 F                                    F
    F          F                 F                                    F
---------- --------- -------------------------- ----------------------------------------------

:::

* the connective $\lor$ can be defined in terms of $\land$ and $\lnot$

::: ttable2

---------- --------- ------------------------- -----------------------------------------------
 $\alpha$   $\beta$   $(\alpha$$\lor$$\beta)$   $\lnot(\lnot$$\alpha$$\land$$\lnot$$\beta)$
    T          T                 T                                    T
    T          F                 T                                    T
    F          T                 T                                    T
    F          F                 F                                    F
---------- --------- ------------------------- -----------------------------------------------

:::

* so, we can define connectives in terms of other connectives
* we show that a form using the connective to be defined is equivalent to a
  form using only the other connectives

# the range of possible connectives

## the range of possible connectives

* we want to show that we all possible connectives can be defined in terms of
  the five connectives of PL
* in order to do so we need to understand what all the possible connectives
  are
* there are zero place connectives, one place connectives, two place
  connectives, three place connectives, and so on
* possible zero place connectives

::: ttable0

   $\top$   $\bot$
  -------- --------
     T        F
:::

* possible one place connectives

::: ttable1

  ---------- --- --- --- ---
   $\alpha$
      T       T   T   F   F
      F       T   F   T   F
  ---------- --- --- --- ---

:::

* we use ①~1~ for the first one-place connective
* the number in the circle represents the number of places of the connective
* the subscript represents the number of the connective
* possible one place connectives

::: ttable1

  ---------- ----- ------- ------ -----
   $\alpha$   ①~1~   ①~2~   ①~3~   ①~4~
      T        T     T        F     F
      F        T     F        T     F
  ---------- ----- ------- ------ -----

:::

* possible one place connectives

::: ttable1

  ---------- ----- ------- --------- ------
   $\alpha$   ①~1~   ①~2~   $\lnot$   ①~4~
      T        T     T       F         F
      F        T     F       T         F
  ---------- ----- ------- --------- ------

:::

* ①~3~ is $\lnot$

* possible two place connectives

::: ttable2

---------- --------- ------ ------ ------ ------ ------ ------ ------ ------ ------ ------- ------- ------- ------- ------- ------- -------
$\alpha$   $\beta$   ②~1~   ②~2~   ②~3~   ②~4~   ②~5~   ②~6~   ②~7~   ②~8~   ②~9~   ②~10~   ②~11~   ②~12~   ②~13~   ②~14~   ②~15~   ②~16~
    T          T       T      T      T      T      T      T      T      T      F      F       F       F       F       F       F       F
    T          F       T      T      T      T      F      F      F      F      T      T       T       T       F       F       F       F
    F          T       T      T      F      F      T      T      F      F      T      T       F       F       T       T       F       F
    F          F       T      F      T      F      T      F      T      F      T      F       T       F       T       F       T       F
---------- --------- ------ ------ ------ ------ ------ ------ ------ ------ ------ ------- ------- ------- ------- ------- ------- -------

:::

* possible two place connectives

::: ttable2

---------- --------- ------ ------- ------ ------ --------------- ------ --------------------  --------- ------ ------- ------- ------- ------- ------- ------- -------
$\alpha$   $\beta$   ②~1~   $\lor$   ②~3~   ②~4~   $\rightarrow$   ②~6~    $\leftrightarrow$    $\land$   ②~9~   ②~10~   ②~11~   ②~12~   ②~13~   ②~14~   ②~15~   ②~16~
    T          T       T       T      T      T            T         T             T              T          F      F       F       F       F       F       F       F
    T          F       T       T      T      T            F         F             F              F          T      T       T       T       F       F       F       F
    F          T       T       T      F      F            T         T             F              F          T      T       F       F       T       T       F       F
    F          F       T       F      T      F            T         F             T              F          T      F       T       F       T       F       T       F
---------- --------- ------ ------- ------ ------ --------------- ------ --------------------  --------- ------ ------- ------- ------- ------- ------- ------- -------

:::


* there are also three place connectives
* they look like this: ③~1~
* they make propositions like this: ③~1~$(P,Q,R)$
* there are 256 three place connectives!
* there are also four place connectives
* they look like this: ④~1~
* they make propositions like this: ~④1~$(P,Q,R,S)$
* there are 65,536 four place connectives!!
* and so on . . .
* obviously, we won't be proving that we can define any connective in terms of our five one by one!
* we better find a method that can obviously be extended to show that we can define any connective in terms of our five

# defining any connective using $\lnot$, $\land$, and $\lor$

## defining any connective using $\lnot$, $\land$, and $\lor$

* okay, we are finally ready to show that any possible connective can be
  defined in terms of our five
* in fact, we will show that any possible connective can be defined in terms of $\lnot$, $\land$, and $\lor$
* obviously we aren't going to define them one by one
* we'll define the zero-place connectives first, one by one
* then we will develop a method for defining any n-place connective in terms of
  $\lnot$, $\land$, and $\lor$
* the zero-place connectives $\top$ and $\bot$ can be defined in terms of the
  connectives {$\lnot$, $\land$, $\lor$}


::: ttable1

---------- -------- ------------------------------- -------- --------------------------------
 $\alpha$   $\top$   $(\alpha \lor \lnot \alpha)$   $\bot$    $(\alpha \land \lnot \alpha)$
 T              T             T                        F              F
 F              T             T                        F              F
---------- -------- ------------------------------- -------- --------------------------------

:::

* so there's a sense in which we don't need the zero place connectives
* remember that to define one connective in terms of others, it is enough to
  show that formulas using them are equivalent
* now we show that any n-place connective can be defined in terms of {$\lnot$,
  $\land$, $\lor$} by the following procedure
* take some n-place connective. call it '\*'
* and take any function from n truth values to truth values

::: ttable2

---------- --------- -----------------------
$\alpha$   $\beta$    $(\alpha$ \* $\beta)$
    T          T                T
    T          F                F
    F          T                T
    F          F                F
---------- --------- -----------------------

:::

* now take the conjunctions which 'describe' the rows in which ($\alpha$ \*
  $\beta$) is true
* in this case: $(\lnot \alpha \land \beta)$, $(\alpha \land \beta)$

::: ttable2

---------- --------- -----------------------
$\alpha$   $\beta$    $(\alpha$ \* $\beta)$
    T          T                T
    T          F                F
    F          T                T
    F          F                F
---------- --------- -----------------------

:::

* in other words
   * if $\alpha$ is true on the row on which $(\alpha$ \* $\beta)$ is true,
     then make $\alpha$ the first conjunct
   * if it is false, make $\lnot \alpha$ the first conjunct
   * do the same for $\beta$, and then do the same for each row on which
     ($\alpha$ \* $\beta$) is true
* by this method we get: $(\lnot \alpha \land \beta)$, $(\alpha \land \beta)$
* now form a disjunction from the conjunctions you got from the previous step:
  $((\lnot \alpha \land \beta) \lor (\alpha \land \beta))$
* and you are done!
* to see that you are done, you can put the disjunction into the table, and you will see that it is equivalent to the formula using '\*'


::: ttable2

---------- --------- ----------------------- --------------------------------------------------------
 $\alpha$   $\beta$   ($\alpha$ \* $\beta$)   $(\lnot \alpha \land \beta) \lor (\alpha \land \beta)$
    T          T                T                                       T
    T          F                F                                       F
    F          T                T                                       T
    F          F                F                                       F
---------- --------- ----------------------- --------------------------------------------------------

:::

* any n-place connective can be defined in terms of {$\lnot$, $\land$, $\lor$}
  by this procedure!
* it should be obvious that for any truth table whatsoever, we only need $\lnot$, $\land$, and $\lor$ to carry out the procedure of describing the row on which some proposition is true and making a disjunction of these conjunctions
* by this method we prove that {$\lnot$, $\land$, $\lor$} is a functionally complete set of connectives!
* we can use this method to convert any proposition whatsoever into an equivalent proposition in **disjunctive normal form** 
* a proposition is in disjunctive normal form if it is a disjunction of conjunctions whose conjuncts are either basic propositions or negations of basic propositions

# functionally complete sets of connectives

## functionally complete sets of connectives

* okay, we just proved that {$\lnot$, $\land$, $\lor$} is a functionally complete set of connectives
* now let's consider the general case of functionally complete sets of connectives
* let's do so by considering some consequences of the fact that {$\lnot$, $\land$, $\lor$} is a functionally complete set of connectives
* **fact**: the set of connectives {$\lnot$, $\land$, $\lor$} is functionally
  complete
* to show that some set of connectives is functionally complete, it suffices to
  show that $\lnot$, $\land$, and $\lor$, can be defined using members of that
  set
    * if {$\lnot$, $\land$, $\lor$} is functionally complete, and $\lnot$, $\land$, and $\lor$ can be defined in terms of some other set of connectives, then that set must be functionally complete too
* **fact**: the set of connectives $\{\lnot, \land \}$ is functionally
  complete
* **proof**: $\lnot$, $\land$, and $\lor$ can be defined in terms of $\lnot$
  and $\land$ alone, and {$\lnot$, $\land$, and $\lor$} is functionally
  complete
* recall...
* the connective $\lor$ can be defined in terms of $\land$ and $\lnot$

::: ttable2

---------- --------- ------------------------- -----------------------------------------------
 $\alpha$   $\beta$   $(\alpha$$\lor$$\beta)$   $\lnot(\lnot$$\alpha$$\land$$\lnot$$\beta)$
    T          T                 T                                    T
    T          F                 T                                    T
    F          T                 T                                    T
    F          F                 F                                    F
---------- --------- ------------------------- -----------------------------------------------

:::

* **fact**: the set of connectives $\{\lnot, \lor \}$ is functionally complete
* **proof**: $\lnot$, $\land$, and $\lor$ can be defined in terms of $\lnot$
  and $\lor$ alone, and {$\lnot$, $\land$, and $\lor$} is functionally
  complete
* recall: 
* the connective $\land$ can be defined in terms of $\lor$ and $\lnot$

::: ttable2

---------- --------- -------------------------- ----------------------------------------------
 $\alpha$   $\beta$   $(\alpha$$\land$$\beta)$    $\lnot(\lnot$$\alpha$$\lor$$\lnot$$\beta)$
    T          T                 T                                    T
    T          F                 F                                    F
    F          T                 F                                    F
    F          F                 F                                    F
---------- --------- -------------------------- ----------------------------------------------

:::

* **fun fact**: {②~9~} is a functionally complete set of connectives
* to sum up, then
* to show that some set of connectives is functionally complete, it suffices to
  show that $\lnot$, and either $\land$ or $\lor$, can be defined using members
  of that set (for then you can rely on the proof that  {$\lnot$, $\land$, $\lor$} is functionally
  complete above)
* to show that a set of connectives is not functionally complete, we need to
  show that there is *some* connective that cannot be defined in terms of those
  in the set

## some exercises 

* just for fun, we could extend our earlier proof about functional completeness by taking our proposition in disjunctive normal form and converting it into a proposition involving either just conjunction and negation or just disjunction and negation 
* recall from above that a conjunction of $\alpha$ and $\beta$ is equivalent to a negated disjunction of $\lnot \alpha$ and $\lnot \beta$
* that is: $(\alpha \land \beta)$ is equivalent to $\lnot (\lnot \alpha \lor \lnot \beta)$
* we can use this fact to convert a proposition in disjunctive normal form into a proposition involving just disjunction and negation
* and recall from above that a disjunction of $\alpha$ and $\beta$ is equivalent to a negated conjunction of $\lnot \alpha$ and $\lnot \beta$
* that is: $(\alpha \lor \beta)$ is equivalent to $\lnot (\lnot \alpha \land \lnot \beta)$
* we can use this fact to convert a proposition in disjunctive normal form into a proposition involving just conjunction and negation

# wrapping up

## this lecture

* with its five connectives, $\lnot$, $\land$, $\lor$, $\rightarrow$, and
  $\leftrightarrow$, PL has the resources to construct a formula with any truth
  conditions whatsoever
* in other words, the set of connectives in PL are **functionally complete**
* you (probably) will not be required to prove that {$\lnot$, $\land$, $\lor$} is
  functionally complete
* but you will be required to prove that some given set of connectives is
  functionally complete
* to do so, you need only show that $\lnot$, $\land$ and $\lor$ can be defined
  in terms of the connectives you are given

## next lecture

* [lecture 09, trees for PL](09_trees_for_PL.html) 
