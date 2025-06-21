---
title: lecture 09, trees for PL
subtitle: phil1012 introductory logic
---

# overview 


## this lecture

*  an introduction to **truth trees** for PL
* general motivation for the use of truth trees for PL
* particular motivations for each tree rule

## next lecture

* how to construct truth trees in general
* how to use truth trees to test for particular logical properties

## learning objectives

* after doing the relevant reading for this lecture, listening to the lecture, and attending the relevant tutorial, you will be able to:
    * explain the motivation behind truth trees for PL
    * write down the tree rules for PL from memory

## required reading

* all of chapter 7

# the motivation for truth trees

## the motivation for truth trees

- the limitations of truth tables as a proof method
- proof trees are the only method of proof we will examine for MPL, GPL, and GPLI

## the limitations of truth tables as a proof method

- recall the maths concerning truth tables
   - 2 basic propositions: 4 rows
   - 3 basic propositions: 8 rows
   - 4 basic propositions: 16 rows
   - 5 basic propositions: 32 rows
   - 6 basic propositions: 64 rows
   - . . .

## the limitations of truth tables as a proof method

- truth tables (or complete ones at least) involve a kind of enumerative search
- if an argument is valid, you've got to fill in every row to be sure
- truth tables may eventually provide an evaluation which is a counterexample
- might we work in a more direct fashion towards a counterexample?
- yes: truth trees

# the basic idea behind truth trees

## re-inventing truth trees  

- let's re-invent truth trees
- suppose you have some proposition or other, and you want to know whether it is satisfiable

. . . 

> $((A \rightarrow B) \land (A \land \lnot B))$   
    
---

- suppose we begin by assuming that it *is* satisfiable
- that is, suppose there is some assignment on which it is true
- what do we know?
- well, we know that the assignment is one on which both conjuncts must be satisfiable (and, in fact must be jointly satisfiable)
- for now, let's just write out a list like this to keep track:

. . . 

> $((A \rightarrow B) \land (A \land \lnot B))$, $(A \rightarrow B)$, $(A \land \lnot B)$
  
---

- okay, now we've got another conjunction in there.
- if there is an assignment on which all these propositions are true together, it must be an assignment on which both conjuncts are satisfiable
- so let's expand our list:

. . . 

> $((A \rightarrow B) \land (A \land \lnot B))$, $(A \rightarrow B)$, $(A \land \lnot B)$, $A$, $\lnot B$

---

- okay, now comes the tricky part. how do we deal with the conditional?
- well, let's ask under what conditions the conditional is satisfiable 
- here it helps to remind ourselves that $(A\rightarrow B)$ is equivalent to $(\lnot A \lor B)$   
- so we can either take an assignment on which $\lnot A$ is true, or an assignment on which $B$ is satisfiable
- take the first first

. . .

> $((A \rightarrow B) \land (A \land \lnot B))$, $(A \rightarrow B)$, $(A \land \lnot B)$, $A$, $\lnot B$, $\lnot A$

---

- uh oh. what is wrong with this list of propositions?

. . . 

> $((A \rightarrow B)\land(A \land \lnot B))$, $(A \rightarrow B)$, $(A \land \lnot B)$, $A$, $\lnot B$, $\lnot A$

- not all of the propositions can be true at once! $A$ and $\lnot A$ cannot be true at once.
- this path isn't going to make our initial assumption about satisfiability work out

---

- what about the other assignment, on which $B$ is satisfiable?

. . .

> $((A \rightarrow B) \land (A \land \lnot B))$, $(A \rightarrow B)$, $(A \land \lnot B))$, $A$, $\lnot B$, $B$

- uh oh.  not all of the propositions can be true at once! $B$ and $\lnot B$ cannot be true at once

---

- our initial assumption was mistaken. the proposition is not satisfiable!
- this method looks like a good one for refuting the initial assumption of satisfiability
- if we reach a contradiction on a path, we can reject that path
- if we reach a contradiction on all paths, we know the proposition isn't satisfiable

--- 

- what if we don't reach a contradiction?
- what if had started with a slightly different proposition?
- what if we had arrived at the following after splitting the conditional?

. . .

> $((C \rightarrow B) \land (A \land \lnot B))$, $(C \rightarrow B)$, $(A \land \lnot B))$, $A$, $\lnot B$, $\lnot C$

---
  
- well, assuming that we have broken down every proposition once
- we know that all of the propositions can be true together if and only if the basic propositions and negations of basic propositions can be true together
- and we can just see that $A$, $\lnot B$ and $\lnot C$ can all be true together
- so we can conclude that the original proposition is satisfiable

---

- even better
- we have derived an assignment on which the proposition is true:

. . .

>  $A$: T, $B$: F, $C$: F

- unlike truth tables, truth trees can take us directly to the relevant assignment

---

- essential to the procedure is the idea of "splitting" or "branching"
- we must check *every* path we create after splitting or branching 
- else we won't know if there is *some* path without a contradiction on it

---

- drawing this method as a tree going down the page is even better 

# the tree method

## the tree method described

- here is the tree proof of the unsatisfiability of $((A \rightarrow B) \land (A \land \lnot B))$ from above

. . .

```{.tree}

\Tree [.{$((A \rightarrow B) \land (A \land \lnot B)) \checkmark$ \\ $(A \rightarrow B) \checkmark$\\$(A \land \lnot B) \checkmark$\\$A$\\$\lnot B$ }
          [.{$\lnot A$ \\ x} ] 
          [.{$B$ \\ x } ]
      ] 
```

---

- how do we construct such a tree?
- well, we begin by writing down the proposition (or propositions) we want to test for satisfiability

. . .

``` tree

\Tree [.{$((A \rightarrow B) \land (A \land \lnot B))$}
      ] 

```

- think of this proposition as the "root" of the tree if you like (the tree is upside down)

---

- now we write down other things which must be true assuming these are true (according to the tree rules)
- if it follows from the assumption that $\alpha$ is true that $\beta$ and $\gamma$ are true, we write  $\beta$ and $\gamma$ at the bottom of every open path on our tree
- in this case we only have one path

. . .

```{.tree}

\Tree [.{$((A \rightarrow B) \land (A \land \lnot B)) $ \\ $(A \rightarrow B)$\\$(A \land \lnot B)$}
      ] 

```

---

- in a moment, we will discuss the rules for building trees (the tree rules)
- these just encapsulate our claims about "what must be true" if some proposition is true   
- each time we apply a tree rule to a proposition we "check it off" with a tick
- this is just a way of keeping track that we've "dealt with" that proposition

. . . 

```{.tree}

\Tree [.{$((A \rightarrow B) \land (A \land \lnot B)) \checkmark$ \\ $(A \rightarrow B) $\\$(A \land \lnot B)$}
      ] 

```

---

- here is the step applied to the conjunction

. . .

```{.tree}

\Tree [.{$((A \rightarrow B) \land (A \land \lnot B)) \checkmark$ \\ $(A \rightarrow B) $\\$(A \land \lnot B) \checkmark$ \\ $A$ \\ $\lnot B$}
      ] 

```

---

- if it follows from the assumption that $\alpha$ is true that either $\beta$ and $\gamma$ are true, or both are true, then we "split" the tree and write them down on either side of the new branch
- we split on every open path the proposition appears on 

. . .

```{.tree}

\Tree [.{$((A \rightarrow B) \land (A \land \lnot B)) \checkmark$ \\ $(A \rightarrow B) \checkmark$\\$(A \land \lnot B) \checkmark$\\$A$\\$\lnot B$ }
          [.{$\lnot A$} ] 
          [.{$B$} ]
      ] 

```

---

- note that each time we apply a rule, we write down propositions which are simpler than those we began with
- the process ends when we cannot apply any more rules
- whenever we encounter a contradiction on a path we immediately "close" the path/branch with a cross
- there's no point continuing with that path because not all propositions on that path can be true together

---

* in the case at hand, both paths close 

. . .

```{.tree}

\Tree [.{$((A \rightarrow B) \land (A \land \lnot B)) \checkmark$ \\ $(A \rightarrow B) \checkmark$\\$(A \land \lnot B) \checkmark$\\$A$\\$\lnot B$ }
          [.{$\lnot A$ \\ x} ] 
          [.{$B$ \\ x} ]
      ] 

```


---

- because the propositions we add always get simpler, we eventually end up with only basic propositions and negations of basic propositions
- if a path contains a contradiction, the propositions on that path cannot all be true at once
- if a finished path does not contain a contradiction, the propositions can all be true together  
- we can "read off" an assignment on which all the propositions are true from the basic propositions and negated propositions on such a path

# the tree rules

## the tree rules stated

- rather than thinking about "what must be true" every time we build a tree, we can write down some rules that capture the relevant claims for each connective
- we'll go over the motivation here
- if you forget a tree rule, it is helpful to know the motivation
- if is also helpful to think of the truth table for the connectives (and connectives in the immediate scope of negation).

## disjunction

- here is the tree rule for disjunction:

. . .

```{.tree}

\Tree [.{$(\alpha \lor \beta) \checkmark$}
          [.{$\alpha$ } ]
          [.{$\beta$ } ]
      ]

```

- let's think through the motivation for the rule in terms of truth tables
- ask: what must be *true* if the disjunction is true?

. . .

::: ttable2

--------  -------  ------------------------------------
$\alpha$  $\beta$           $(\alpha \lor \beta)$
   T         T                       T
   T         F                       T
   F         T                       T
   F         F                       F
--------  -------  ------------------------------------

:::

. . . 

* answer: either $\alpha$ *or*  $\beta$ (or both) 

## conjunction

* here is the tree rule for conjunction:

. . .

```{.tree}

\Tree [.{$(\alpha \land \beta) \checkmark$ \\ $\alpha$ \\ $\beta$}
      ]

```

- let's think through the motivation for the rule in terms of truth tables
- ask: what must be *true* if the conjunction is true?

::: ttable2

--------  -------  ------------------------------------
$\alpha$  $\beta$           $(\alpha \land \beta)$
   T         T                       T
   T         F                       F
   F         T                       F
   F         F                       F
--------  -------  ------------------------------------

:::

. . . 

answer: $\alpha$ *and* $\beta$ must be true

## negated disjunction

* here is the tree rule for negated disjunction:

. . .

```{.tree}

\Tree [.{$\lnot(\alpha \lor \beta) \checkmark$ \\ $\lnot \alpha$ \\ $\lnot \beta$}
      ]

```

- let's think through the motivation for the rule in terms of truth tables
* ask: what must be *true* if the negated disjunction is true?

::: ttable2

--------  -------  ------------------------------------
$\alpha$  $\beta$           $\lnot(\alpha \lor \beta)$
   T         T                       F
   T         F                       F
   F         T                       F
   F         F                       T
--------  -------  ------------------------------------

:::

* answer: $\lnot\alpha$ *and*  $\lnot\beta$ must be true
* this one is easy if you remember the following equivalence:
   * $\lnot(\alpha \lor \beta)$$\equiv$$(\lnot\alpha \land \lnot\beta)$ 

## negated conjunction

* here is the tree rule for negated conjunction:

. . .

```{.tree}

\Tree [.{$\lnot(\alpha \land \beta) \checkmark$}
          [.{$\lnot \alpha$} ]
          [.{$\lnot \beta$} ]  
      ]

```

- let's think through the motivation for the rule in terms of truth tables
- ask: what must be true if the negated conjunction is true?

::: ttable2

--------  -------  ------------------------------------
$\alpha$  $\beta$       $\lnot(\alpha \land \beta)$
   T         T                       F
   T         F                       T
   F         T                       T
   F         F                       T
--------  -------  ------------------------------------

:::

. . . 

- answer: either $\lnot\alpha$ *or* $\lnot\beta$ (or both)
- this one is easy if you remember the following equivalence:
   * $\lnot(\alpha \land \beta)$$\equiv$$(\lnot\alpha \lor \lnot \beta)$

## conditional

* here is the tree rule for conditional:

. . .

```{.tree}

\Tree [.{$(\alpha \to \beta) \checkmark$}
          [.{$\lnot \alpha$} ]
          [.{$\beta$} ]  
      ]

```

- let's think through the motivation for the rule in terms of truth tables
- ask: what must be true if the conditional is true?

::: ttable2

--------  -------  ---------------------------------------
$\alpha$  $\beta$           $(\alpha \rightarrow \beta)$
   T         T                       T
   T         F                       F
   F         T                       T
   F         F                       T
--------  -------  ---------------------------------------

:::

. . . 

* answer: either $\alpha$ *or* $\lnot\beta$ must be true
* this is easy to remember if you keep the following equivalence in mind:
   * $(\alpha \rightarrow \beta)$$\equiv$$(\lnot\alpha \lor \beta)$


## negated conditional

* here is the tree rule for negated conditional:

. . .

```{.tree}

\Tree [.{$\lnot (\alpha \to \beta) \checkmark$ \\ $\alpha$ \\ $\lnot \beta$}
      ]

```

- let's think through the motivation for the rule in terms of truth tables
- ask what must be true if the negated conditional is true?

::: ttable2

--------  -------  ------------------------------------
$\alpha$  $\beta$    $\lnot(\alpha \rightarrow \beta)$
   T         T                       F
   T         F                       T
   F         T                       F
   F         F                       F
--------  -------  ------------------------------------

:::

. . . 

- answer: $\alpha$ and $\lnot \beta$ must be true
* this is easy if you remember the following equivalence:
    * $\lnot(\alpha \rightarrow \beta)$$\equiv$$(\alpha \land \lnot \beta)$

## biconditional

* here is the tree rule for biconditional:

. . .

```{.tree}

\Tree [.{$(\alpha \leftrightarrow \beta) \checkmark$}
          [.{$\alpha$ \\ $\beta$} ]
          [.{$\lnot \alpha$ \\ $\lnot \beta$} ]  
      ]

```

- let's think through the motivation for the rule in terms of truth tables
- ask: what must be true if the biconditional is true?

::: ttable2

--------  -------  ------------------------------------
$\alpha$  $\beta$    $(\alpha \leftrightarrow \beta)$
   T         T                       T
   T         F                       F
   F         T                       F
   F         F                       T
--------  -------  ------------------------------------

:::

* answer: either both $\alpha$ and $\beta$ must be true or $\lnot\alpha$ and $\lnot\beta$ must be true.
* this is easy if you remember the following equivalence:
   * $(\alpha \leftrightarrow \beta)$$\equiv$$((\alpha \land \beta) \lor (\lnot\alpha \land \lnot\beta))$

## negated biconditional

* here is the tree rule for negated biconditional:

. . .

```{.tree}

\Tree [.{$\lnot(\alpha \leftrightarrow \beta) \checkmark$}
          [.{$\alpha$ \\ $\lnot \beta$} ]
          [.{$\lnot \alpha$ \\ $\beta$} ]  
      ]

```

- let's think through the motivation for the rule in terms of truth tables

::: ttable2

--------  -------  -----------------------------------------
$\alpha$  $\beta$    $\lnot(\alpha \leftrightarrow \beta)$
   T         T                       F
   T         F                       T
   F         T                       T
   F         F                       F
--------  -------  -----------------------------------------

:::

. . . 

* answer: either both $\alpha$ and $\lnot\beta$ must be true or $\lnot\alpha$ and $\beta$ must be true.
* this is easy if you remember the following equivalence:
   * $(\alpha \leftrightarrow \beta)$$\equiv$$((\alpha \land \lnot\beta) \lor (\lnot\alpha \land \beta))$


## double negation

* here is the tree rule for double negation:

. . .

```{.tree}

\Tree [.{$\lnot \lnot \alpha \checkmark$ \\ $\alpha$}
      ]

```

- let's think through the motivation for the rule

--------- --------------------------------
$\alpha$       $\lnot\lnot\alpha$
   T                    T
   F                    F
--------- --------------------------------

## closure   

* finally, here is the closure rule:

. . .

```{.tree}

\Tree [.{$\alpha$} [.{\ldots} [.{$\lnot \alpha$ \\ x } ] ] ] 

```

- let's think through the motivation for the rule
* if a proposition and its negation both appear on a path, then it is not the case that all the propositions on that path can be true at the same time
* so we close that path

---

* a note on closure: the closure rule applies to *all* propositions and their negations, not just basic propositions and their negations

# wrapping up

## this lecture

* an introduction to **truth trees** for PL
* general motivation for the use of truth trees for PL
* particular motivations for each tree rule

## next lecture

* how to construct truth trees in general
* how to use truth trees to test for particular logical properties

## next lecture

* [lecture 10, uses of trees for PL](10_uses_of_trees_for_PL.html)

