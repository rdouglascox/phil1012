---
title: lecture 10, uses of trees for PL
subtitle: phil1012 introductory logic
---

# overview

## this lecture

* in the previous lecture we looked at the motivation for trees for PL
* we looked at the motivation for the particular tree rules
* in this lecture we look at how we construct trees and how we use them to test for various logical properties

## learning outcomes

* after doing the relevant reading for this lecture, listening to the lecture, and attending the relevant tutorial, you will be able to:
    * construct trees for propositions of PL
    * use trees to determine whether arguments in PL are valid and to find counterexamples to invalid arguments
    * use trees to test for various logical properties of PL propositions and to read off assignments from open paths

# applying the rules

## applying the rules

* let's look at how we apply the rules . . .

## which rule to apply

* before you apply a rule ask yourself: what is the main connective?
    * if it is anything but negation, then apply the relevant rule
    * if it is negation, look for the main connective of the negand and apply
the relevant rule
* suppose you have:

. . .

``` prooftree

\begin{prooftree}
{line numbering=true}
[\lnot(A \lor B),  just=assumption]
\end{prooftree}

```

---

* is this right?

. . .

``` prooftree
\begin{prooftree}
{line numbering=true}
[\lnot(A \lor B), just=assumption, checked  [A][B, just=rule for disjunction]]
\end{prooftree}

```

* no, it is wrong

---

* is this right?

. . .

``` prooftree
\begin{prooftree}
{line numbering=true}
[\lnot(A \lor B), just=assumption, checked  [\lnot A[\lnot B, just=rule for negated disjunction]]]
\end{prooftree}

```

* yes. here the main connective is negation, and the main connective of the
    negand is disjunction.

---

* before you apply a rule ask yourself: what is the main connective?
    * if it is anything but negation, then apply the relevant rule
    * if it is negation, look for the main connective of the negand and apply
the relevant rule

## testing a single proposition for satisfiability

* suppose we want to test whether the following proposition is
    satisfiable: $(A \rightarrow (B \rightarrow A))$
* we begin by writing this proposition on the first line

. . .

``` prooftree
\begin{prooftree}
{line numbering=true}
[(A \rightarrow (B \rightarrow A)), just=assumption]
\end{prooftree}
```

* notice that the assumption is not checked

---

* then we apply the rule for the conditional
* remembering to check off the assumption

---

``` prooftree
\begin{prooftree}
{line numbering=true}
[(A \rightarrow (B \rightarrow A)), just=assumption]
\end{prooftree}
```

---

``` prooftree

\begin{prooftree}
{line numbering=true}
[(A \rightarrow (B \rightarrow A)), just=assumption, checked [\lnot A][(B \rightarrow A), just=rule for conditional]]
\end{prooftree}

```

*  notice that we have now checked the assumption, since we have
    applied the rule
* now we ask: have we applied all the rules we can
    apply?
* no

---

* now we apply the rule for the conditional again

---

``` prooftree

\begin{prooftree}
{line numbering=true}
[(A \rightarrow (B \rightarrow A)), just=assumption, checked [\lnot A][(B \rightarrow A), just=rule for conditional]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true}
[(A \rightarrow (B \rightarrow A)), just=assumption, checked [\lnot A][(B \rightarrow A), just=rule for conditional, checked [\lnot B ][ A, just= rule for conditional ]          ]]
\end{prooftree}

```

* now we ask: have we applied all the rules we can apply?
* yes
* this tree is complete

## the notion of a path

* a helpful notion in thinking about trees is the notion of a path
* a **path** through a tree is a complete route from the topmost
    proposition down until one can go no further
* for example, suppose
    we have this tree:

. . .

``` prooftree
\begin{prooftree}
{line numbering=true}
[((A \land \lnot A) \lor B),  checked,  just=assumption [(A \land \lnot A), checked [A,  just=rule for conjunction [\lnot A,  just=rule for conjunction]] ] [B, just=rule for disjunction]]
\end{prooftree}
```

---

* here is one path through the tree:

. . .

``` prooftree
\begin{prooftree}
{line numbering=true}
[((A \land \lnot A) \lor B),  checked, highlight wff, just=assumption [(A \land \lnot A), highlight wff, checked [A, highlight wff, just=rule for conjunction [\lnot A, highlight wff, just=rule for conjunction]] ] [B, just=rule for disjunction]]
\end{prooftree}

```

---

* here is another path through the tree:

. . .

``` prooftree

\begin{prooftree}
{line numbering=true}
[((A \land \lnot A) \lor B),  checked, highlight wff, just=assumption [(A \land \lnot A),  checked [A,  just=rule for conjunction [\lnot A,  just=rule for conjunction]] ] [B, highlight wff, just=rule for disjunction]]
\end{prooftree}

```

---

* if at any point we find that a path contains both a formula and its
    negation, we **close** the path with a **cross**
* so, for example, the path above contains both $A$ and $\lnot A$.

. . .

``` prooftree
\begin{prooftree}
{line numbering=true}
[((A \land \lnot A) \lor B),  checked,  just=assumption [(A \land \lnot A), checked [A,  just=rule for conjunction [\lnot A,  just=rule for conjunction, close]] ] [B, just=rule for disjunction]]
\end{prooftree}

```

## applying rules on every open path

* suppose you have the following unfinished tree:

. . .

``` prooftree
\begin{prooftree}
{line numbering=true}
[((A \rightarrow B) \land (B \rightarrow A)), checked, just=assumption
[(A \rightarrow B), checked, just=rule for conjunction
[(B \rightarrow A), just=rule for conjunction [\lnot A] [B, just=rule for conditional]]]
]
\end{prooftree}
```

* the rule for conditional has not been applied to the conditional on
    the third line
* there are two open paths through this tree
* the tree rules must be applied on all open paths on which the formula it is
    being applied to is on.

---

* if you apply the rule correctly this is the tree you get:

. . .

``` prooftree
\begin{prooftree}
{line numbering=true}
[((A \rightarrow B) \land (B \rightarrow A)), checked, just=assumption
[(A \rightarrow B), checked, just=rule for conjunction
[(B \rightarrow A), checked, just=rule for conjunction [\lnot A [\lnot B] [A, close,  just=rule for conditional]] [B, just=rule for conditional [\lnot B, close] [A, just=rule for conditional]]]]
]
\end{prooftree}

```

---

* it is important, however, to apply the rule only on the path on
    which the wff is on
* suppose you have this tree

. . .

``` prooftree
\begin{prooftree}
{line numbering=true}
[((A \lor B) \lor (C \lor D)), just=assumption, checked [(A \lor B)]  [(C \lor D), just=rule for disjunction ]]
\end{prooftree}

```

---

* the next step is not:

. . .

``` prooftree
\begin{prooftree}
{line numbering=true}
[((A \lor B) \lor (C \lor D)), just=assumption, checked [(A \lor B)  [[C][D]]]  [(C \lor D), checked, just=rule for disjunction [[C][D, just=rule for disjunction]]  ]]
\end{prooftree}

```

---

* these are not on the same path:

. . .

``` prooftree
\begin{prooftree}
{line numbering=true}
[((A \lor B) \lor (C \lor D)), just=assumption, checked [(A \lor B)  [[C, highlight wff][D, highlight wff]]]  [(C \lor D), highlight wff, checked, just=rule for disjunction [[C][D, just=rule for disjunction]]  ]]
\end{prooftree}

```

---

* what is wrong with the following tree?

. . .

``` prooftree
\begin{prooftree}
{line numbering=true}
[((A \rightarrow B) \land (B \rightarrow A)), checked, just=assumption  [\lnot B, just=assumption
[(A \rightarrow B), checked, just=rule for conjunction
[(B \rightarrow A), checked, just=rule for conjunction [\lnot A [\lnot B] [A, close,  just=rule for conditional]] [B, just=rule for conditional [\lnot B, close] [A,  just=rule for conditional]]]]]
]
\end{prooftree}
```

---

* the path with B and $\lnot$B should have been closed.

. . .

``` prooftree
\begin{prooftree}
{line numbering=true}
[((A \rightarrow B) \land (B \rightarrow A)), checked, just=assumption  [\lnot B, highlight wff, just=assumption
[(A \rightarrow B), checked, just=rule for conjunction
[(B \rightarrow A), checked, just=rule for conjunction [\lnot A [\lnot B] [A, close,  just=rule for conditional]] [B, highlight wff, just=rule for conditional [\lnot B, close] [A,  just=rule for conditional]]]]]
]
\end{prooftree}
```

---

* it should have looked like this:

. . .

``` prooftree
\begin{prooftree}
{line numbering=true}
[((A \rightarrow B) \land (B \rightarrow A)), checked, just=assumption  [\lnot B, just=assumption
[(A \rightarrow B), checked, just=rule for conjunction
[(B \rightarrow A), checked, just=rule for conjunction [\lnot A [\lnot B] [A, close,  just=rule for conditional]] [B, just=rule for conditional, close ]]]]
]
\end{prooftree}

```

* every time you add wffs to the tree you *must* check for closure
* this applies when you first write down your assumptions, and
    applies again whenever you apply a rule

# the order of the rules

## the order of the rules

* it doesn't matter which order you apply the rules
* however, it is often convenient to apply non-branching rules first whenever you have
    a choice between non-branching and branching rules
* to see why, suppose we have:

. . .

``` prooftree
\begin{prooftree}
{line numbering=true}
[(A \lor B), just=assumption [(A \rightarrow B), just=assumption]]
\end{prooftree}
```

---

* branching first:

. . .

```prooftree

\begin{prooftree}
{line numbering=true}
[(A \land B), just=assumption, checked [(A \rightarrow B), just=assumption, checked [\lnot A [A [B, just= rule for conjunction, close]]][B, just= rule for conditional [A [B, just= rule for conjunction]]]]]
\end{prooftree}

```

* non-branching first:

. . .

``` prooftree
\begin{prooftree}
{line numbering=true}
[(A \land B), just=assumption, checked [(A \rightarrow B), just=assumption, checked [A [B, just= rule for conjunction [\lnot A, close][B, just= rule for conditional]]]]]
\end{prooftree}
```

* there's only a small difference here (2 wffs to be exact)
* but the difference can be significant with bigger trees
* another good idea is to apply rules which will give you a closed
    branch first
* but this requires some foresight

---

* want to build trees which look exactly like the trees which the
    program I use to generate answers look?
* mechanically follow these steps
    * **step 1.** from the top down, apply double negation rule and check
    for contradictions, until you can't. go to step 2.
    * **step 2.** from the top down, apply any non-branching rule, check
    for contradictions, and do step 1, until you can't. (conjunction
    first, negated disjunction next, then negated conditional). go to
    step 3.
    * **step 3.** from the top down, apply a branching rule if you can,
    check for contradictions, and return to step 1. (disjunction first,
    conditional next, biconditional, then negated biconditional). if you
    can't apply a branching rule (or any other rules for that matter),
    you are done!

---

* if you do this then . . .
    * the input and output of the double negation rule will always be
    together
    * you will never miss a contradiction (think of checking for
    contradictions as part of what you do when you apply a rule)
    * you will never apply a branching rule before you could have applied
    a non-branching rule

# what trees do

## what trees do

* the rules specify things to write which must be true assuming that
    the propositions at the top of the tree are true
* the rules are
    constructed so that if the propositions at the top of the tree are
    true, then there is at least one path such that everything on that
    path is true

---

* each path represents an alleged way for the propositions at the top
    all to be true together: an alleged assignment of truth values to
    basic propositions that makes the propositions at the top true
* this is only an alleged way for them to be true together, since some
    paths close
* a closed path does not represent a possible assignment of values at
    all, while an open path represents a possible assignment of values
    on which the propositions at the top are all true

---

* suppose that all paths close
    * then the propositions at the top are
    unsatisfiable: there is no way of making them all true
* but suppose a path remains open: then the propositions at the top
    are satisfiable: there is an assignment of truth values to basic
    propositions that makes them all true
* this is what allows us to "read off' an assignment of values to
    basic propositions on which our initial propositions are all true

# testing for satisfiability

## testing for satisfiability

* in the first instance, trees allow us to test whether a given set of
    propositions is satisfiable or not
* if we know how to set things up
    properly, we can use trees to test for other properties too

---

``` prooftree
\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \{P, \lnot P\} $ is satisfiable.$}}
[P, just=assumption [\lnot P, just=assumption]]
\end{prooftree}
```

* if all of the paths close, then the propositions are not jointly
    satisfiable
* if a path remains open, then the propositions are jointly
    satisfiable

---

``` prooftree
\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \{P, \lnot P\} $ is satisfiable.$}}
[P, just=assumption [\lnot P, just=assumption, close]]
\end{prooftree}
```

* all paths close, so the propositions are not jointly satisfiable

---

``` prooftree
\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \{P, P \rightarrow Q, \lnot Q\} $ is satisfiable.$}}
[P, just=assumption[P \rightarrow Q, just=assumption [\lnot Q, just=assumption]]]
\end{prooftree}
```

---

``` prooftree
\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \{P, P \rightarrow Q, \lnot Q\} $ is satisfiable.$}}
[P, just=assumption[P \rightarrow Q, checked, just=assumption [\lnot Q, just=assumption [\lnot P][ Q]]]]
\end{prooftree}
```

---

``` prooftree
\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \{P, P \rightarrow Q, \lnot Q\} $ is satisfiable.$}}
[P, just=assumption[P \rightarrow Q, checked, just=assumption [\lnot Q, just=assumption [\lnot P, close][ Q, close]]]]
\end{prooftree}
```

*  all paths close, so the propositions are not jointly satisfiable

---

``` prooftree
\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \{P \rightarrow Q, P \land Q\} $ is satisfiable.$}}
[P \rightarrow Q, just=assumption [P \land Q, just=assumption]]
\end{prooftree}
```

---

``` prooftree
\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \{P \rightarrow Q, P \land Q\} $ is satisfiable.$}}
[P \rightarrow Q, checked, just=assumption [P \land Q, just=assumption, checked [P [Q [\lnot P, close][Q]]]]]
\end{prooftree}
```

* the tree is finished and there is an open path

---

``` prooftree
\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \{P \rightarrow Q, P \land Q\} $ is satisfiable.$}}
[P \rightarrow Q, checked, just=assumption [P \land Q, just=assumption, checked [P, highlight wff [Q, highlight wff [\lnot P, close][Q, highlight wff]]]]]
\end{prooftree}
```

* we read off an assignment on which the propositions are true. $P$: T, $Q$: T

---

``` prooftree
\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \{A \lor B, B \land C\} $ is satisfiable.$}}
[A \lor B [B \land C]]
\end{prooftree}
```

---

``` prooftree
\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \{A \lor B, B \land C\} $ is satisfiable.$}}
[A \lor B [B \land C, checked [B[C]]]]
\end{prooftree}
```

---

``` prooftree
\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \{A \lor B, B \land C\} $ is satisfiable.$}}
[A \lor B, checked [B \land C, checked [B[C [A][B]]]]]
\end{prooftree}
```

---

``` prooftree
\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \{A \lor B, B \land C\} $ is satisfiable.$}}
[A \lor B, checked [B \land C, checked [B, highlight wff [C, highlight wff [A, highlight wff][B]]]]]
\end{prooftree}
```

* left path yields: $A$: T, $B$: T, $C$: T

---

``` prooftree
\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \{A \lor B, B \land C\} $ is satisfiable.$}}
[A \lor B, checked [B \land C, checked [B, highlight wff [C, highlight wff [A][B, highlight wff]]]]]
\end{prooftree}
```

* right path yields: $B$: T, $C$: T.
* either: $B$: T, $C$: T, $A$: T or $B$: T, $C$: T, $A$: F.
* so one tree can yield multiple assignments
* these are related to the rows of a truth table

. . .
``` prooftree
\begin{tabular}{|c|c|c||c|c|}\hline A&B&C&(A$\vee{}$B)&(B$\wedge{}$C)\tabularnewline \hline T&T&T&T&T\tabularnewline T&T&F&T&F\tabularnewline T&F&T&T&F\tabularnewline T&F&F&T&F\tabularnewline F&T&T&T&T\tabularnewline F&T&F&T&F\tabularnewline F&F&T&F&F\tabularnewline F&F&F&F&F\tabularnewline \hline \end{tabular}
```

---

``` prooftree
\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \{A \leftrightarrow \lnot B, A \lor \lnot B\} $ is satisfiable.$}}
[A \leftrightarrow \lnot B [A \lor \lnot B]]
\end{prooftree}
```

---

``` prooftree
\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \{A \leftrightarrow \lnot B, A \lor \lnot B\} $ is satisfiable.$}}
[A \leftrightarrow \lnot B, checked [A \lor \lnot B [A [\lnot  B ]][\lnot A [\lnot \lnot B ]]]]
\end{prooftree}
```

---

``` prooftree
\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \{A \leftrightarrow \lnot B, A \lor \lnot B\} $ is satisfiable.$}}
[A \leftrightarrow \lnot B, checked [A \lor \lnot B, checked [A [\lnot  B [A][\lnot B]]][\lnot A [\lnot \lnot B [A][\lnot B]]]]]
\end{prooftree}
```

---

``` prooftree
\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \{A \leftrightarrow \lnot B, A \lor \lnot B\} $ is satisfiable.$}}
[A \leftrightarrow \lnot B, checked [A \lor \lnot B, checked [A [\lnot  B [A][\lnot B]]][\lnot A [\lnot \lnot B, checked [A, close][\lnot B [B, close]]]]]]
\end{prooftree}
```

* there are two open paths

---

``` prooftree
\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \{A \leftrightarrow \lnot B, A \lor \lnot B\} $ is satisfiable.$}}
[A \leftrightarrow \lnot B, checked [A \lor \lnot B, checked [A, highlight wff [\lnot  B, highlight wff [A][\lnot B, highlight wff]]][\lnot A [\lnot \lnot B, checked [A, close][\lnot B [B, close]]]]]]
\end{prooftree}
```

* this path yields: $A$: T, $B$: F

---

``` prooftree
\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \{A \leftrightarrow \lnot B, A \lor \lnot B\} $ is satisfiable.$}}
[A \leftrightarrow \lnot B, checked [A \lor \lnot B, checked [A, highlight wff [\lnot  B, highlight wff [A, highlight wff][\lnot B]]][\lnot A [\lnot \lnot B, checked [A, close][\lnot B [B, close]]]]]]
\end{prooftree}
```

* this path yields: $A$: T, $B$: F
* so different paths can yield the same assignment

---

* one tree can yield multiple assignments
* different paths can yield the same assignment
* every truth-making assignment, if there are any at all, can be read
    of some path
     * none are overlooked

# testing for validity

## testing for validity

* validity: is it possible for the premises to be true and the
    conclusion false?
* is it possible for the premises to be true and the negation of the
    conclusion to be true?
* is the set containing the premises and the negation of the
    conclusion satisfiable?

---

``` prooftree
\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ (A \rightarrow B), (B \rightarrow C) \therefore (A \rightarrow C) $ is valid.$}}
[(A \rightarrow B), just=assumption [(B \rightarrow C), just=assumption [\lnot(A \rightarrow C), just=negation of Conclusion ]]]
\end{prooftree}
```

* if all of the paths close, then the argument if valid.
* if any paths remain open, then the argument is invalid.

---

* as with truth tables, if an argument is invalid, we can read off a
    counterexample
* the counterexample is provided by the basic
    propositions and negations of basic propositions on an open path
* we assign T to the basic propositions on an open path, and F to the
    basic proposition which is the negand of the negation on an open
    path

---

``` prooftree
\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ (A \rightarrow B), (B \rightarrow C) \therefore (B \rightarrow A) $ is valid.$}}
[(A \rightarrow B), just=assumption [(B \rightarrow C), just=assumption [\lnot(B \rightarrow A), just=negation of Conclusion, checked [B [\lnot A, just=rule for negated conditional ]] ]]]
\end{prooftree}
```

---

``` prooftree
\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ (A \rightarrow B), (B \rightarrow C) \therefore (B \rightarrow A) $ is valid.$}}
[(A \rightarrow B), just=assumption, checked [(B \rightarrow C), just=assumption [\lnot(B \rightarrow A), just=negation of Conclusion, checked [B [\lnot A, just=rule for negated conditional [\lnot A][B, just= rule for conditional] ]] ]]]
\end{prooftree}
```

---

``` prooftree
\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ (A \rightarrow B), (B \rightarrow C) \therefore (B \rightarrow A) $ is valid.$}}
[(A \rightarrow B), just=assumption, checked [(B \rightarrow C), just=assumption, checked [\lnot(B \rightarrow A), just=negation of Conclusion, checked [B [\lnot A, just=rule for negated conditional  [\lnot A [\lnot B, close][C, just= rule for conditional]][B, just= rule for conditional [\lnot B, close][C, just= rule for conditional]] ]] ]]]
\end{prooftree}
```

---

``` prooftree
\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ (A \rightarrow B), (B \rightarrow C) \therefore (B \rightarrow A) $ is valid.$}}
[(A \rightarrow B), just=assumption, checked [(B \rightarrow C), just=assumption, checked [\lnot(B \rightarrow A), just=negation of Conclusion, checked [B, highlight wff,  [\lnot A, highlight wff,  just=rule for negated conditional  [\lnot A [\lnot B, close][C, just= rule for conditional]][B, highlight wff,  just= rule for conditional [\lnot B, close][C, highlight wff,  just= rule for conditional]] ]] ]]]
\end{prooftree}
```

* a counterexample: $B$: true, $C$: true, $A$: false

---

* the relevant row of the truth table looks like this:

. . .

::: ttable3

  ----- ----- ----- ------------------------- ------------------------- -------------------------
   $A$   $B$   $C$   $(A \rightarrow B )$     $(B \rightarrow C)$         $(B \rightarrow A)$
    F     T     T               T                         T                         F
  ----- ----- ----- ------------------------- ------------------------- -------------------------

:::

# testing for contraries and contradictories

## testing for contraries and contradictories


``` prooftree
\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \{ \alpha, \beta \} $ are contraries or contradictories. Step 1.$}}
[\alpha, just=assumption [\beta, just=assumption]]
\end{prooftree}
```

*  if the propositions are jointly satisfiable, they are not contraries
    or contradictories
* if they are not jointly satisfiable, they are
    either contraries or contradictories, but we need a further test to
    determine which

---

``` prooftree
\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \{ \alpha, \beta \} $ are contraries or contradictories. Step 2.$}}
[\lnot\alpha, just=negation of $\alpha$ [\lnot\beta, just=negation of $\beta$]]
\end{prooftree}
```

* if the propositions are jointly satisfiable then they are
    contraries
* if they are not jointly satisfiable, then they are
    contradictories

# testing for tautologies and logical truths

## testing for tautologies and logical truths

* tautology: is it possible for the proposition to be false?
* is it possible for the negation of the proposition to be true?
* is the set containing the negation of the proposition satisfiable?
    * if it is not, then it is a tautology

---

``` prooftree
\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \alpha $ is a logical truth.$}}
[\lnot\alpha, just=negation of Proposition to be Tested]
\end{prooftree}
```

* if the negation of the proposition is not satisfiable (if all paths
    close), then the proposition itself is a logical truth.

# testing for equivalence

## testing for equivalence

* equivalent: is it possible for one proposition to be true while the
    other is false or vice versa?
* is the biconditional constructed from the propositions a tautology?
* is the set containing the negation of the biconditional constructed
    from the propositions unsatisfiable? If it is, then they are
    equivalent

---

``` prooftree
\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \alpha $ and $ \beta $ are equivalent.$}}
[\lnot(\alpha \leftrightarrow \beta), just=negated biconditional formed from $\alpha$ and $\beta$ ]
\end{prooftree}
```

* if the negated biconditional is not satisfiable (all paths close)
    then the propositions are equivalent.

# wrapping up

## this lecture

* trees can be used to test for various properties
* once you know how to build trees, all you need to know is how to set them
up the right way to test for various properties, and how to understand the
results of your test
* we've looked at a few examples in this lecture
* you will do many more in tutorials

## next lectures

* [lecture 11, the formal language MPL](11_the_formal_language_MPL.html)
