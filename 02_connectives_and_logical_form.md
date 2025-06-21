---
title: lecture 02, connectives and logical form
subtitle: phil1012 introductory logic
---

# overview

## this lecture

* in the previous lecture, we introduced the idea of logical form, the logical form of a proposition
* in this lecture we take a closer look at the logical forms of propositions
* we look at the logical form of propositions constructed using the **truth functional connectives** negation, conjunction, disjunction, conditional, and biconditional

## learning outcomes

* after doing the relevant reading for this lecture, listening to the lecture, and attending the relevant tutorial, you will be able to:
    * identify different sorts of compound propositions and identify their components
        * negations, and the negand of a negation
        * conjunctions, and the conjuncts of a conjunction
        * disjunctions, and the disjuncts of a disjunction
        * conditionals, and the antecedent and consequent of a conditional
        * biconditionals, and the right-hand-side and the left-hand-side of a conditional
     * explain the difference between basic and compound propositions
     * explain what makes a connective a truth-functional connective

## required reading

* :books: section 1.6 of chapter 1

# truth functional connectives and compound propositions

## basic and compound propositions

* some propositions are made up of other propositions
   * Jane lives in Australia and Jack lives in China
   * if Jane lives in Australia, then Jack lives in China
* propositions made up of other propositions are called **compound propositions**
* if a proposition is not made up of other propositions, it is a **basic proposition**
   * Jane lives in Australia
* the observation that some propositions are made up of other propositions is the basic insight which motivates propositional logic
* it is a basic insight about the form of propositions

## connectives and compound propositions

* compound propositions are made up of other propositions and bits that
connect these other propositions together to make a compound proposition
* these 'bits' are called connectives
* a **connective** 'connects' propositions to make propositions
    * Jane lives in Australia **and** Jack lives in China
    * Jane lives in Australia **or** Jack lives in China
    * **if** Jane lives in Australia **then** Jack lives in China
    * Jane does **not** live in Australia
* in each of these examples we can see how a larger proposition is built out
of other propositions by way of the connectives 'and', 'or', 'if, then', and
'not'
* 'not' may seem odd. 'not' doesn't 'connect' propositions. still, it takes
one proposition and makes another. so we call it a connective.


## truth-functional connectives

* some connectives are special in the following sense: when they are used to
make a compound proposition from other propositions, we can be sure that the
**truth** of the compound expression is determined by the truth or falsity
of the propositions it is made out of

* a connective is **truth-functional connective** if and only if the truth
or falsity of a compound proposition formed from the connective and some
other propositions is completely determined by the truth and falsity of
those component propositions

## truth-functional connectives and propositional logic

* the truth-functional connectives are at the heart of **propositional logic**
* we might say that propositional logic is the systematic study of the laws
of truth with respect to the form propositions have as a consequence of
their being built using truth-functional connectives
* since the propositions studied in other areas of logic are built using
truth-functional connectives, propositional logic forms the basis of the
logics studied in these other areas
* the formal language **PL** is designed to assist us in the systematic
study of these laws of truth

# logical connectives in English

## five central logical connectives

* the rest of this lecture introduces the **five** connectives which will
be central to our study of propositional logic
* these are:
   * conjunction
   * disjunction
   * conditional
   * biconditional
   * negation

## conjunction

* **conjunction**
   * e.g. John is short and Jane is tall
* the compound proposition expressed by this sentence is made up of the
proposition that John is short and the proposition that Jane is tall and the
connective **conjunction**
* the compound proposition expressed by 'John is short and Jane is tall' is
a **conjunction**
* the propositions expressed by 'John is short' and 'Jane is tall' are
**conjuncts** of the conjunction
* conjunction is a **two-place connective**, because it connects two propositions
* conjunction is a **truth-functional connective**
* if both the conjuncts are true, the conjunction is true. if either is
false, then the conjunction is false
    * consider: John is short and Jane is tall

## disjunction

* **disjunction**
    * e.g. John is short or Jane is tall
* the compound proposition expressed by this sentence is made up of the
proposition that John is short and the proposition that Jane is tall and the
connective **disjunction**
* the compound proposition expressed by 'John is short or Jane is tall' is a
**disjunction**.
* the propositions expressed by 'John is short' and 'Jane is tall' are
**disjuncts** of the disjunction.
* disjunction is a **two-place connective**, because it connects two
propositions.
* disjunction is a **truth-functional connective**
* if either disjunct is true or both disjuncts are true, the disjunction is
true. If both disjuncts are false, the disjunction is false
   * consider: John is short or Jane is tall

## conditional

* **conditional**
    * e.g. if John is short, then Jane is tall
* the compound proposition expressed by this sentence is made up of the
proposition that John is short and the proposition that Jane is tall and the
connective **conditional**.
* the compound proposition expressed by 'If John is short, then Jane is
tall' is a **conditional**
* the proposition expressed by 'John is short' is the **antecedent** of the
conditional and the proposition expressed by 'Jane is tall' is the
**consequent** of the conditional
* conditional is a **two-place connective**, because it connects two
propositions
* the connective conditional is a **truth-functional connective**
* if the antecedent is true and the consequent is false then the conditional
is false. otherwise it is true.
    * consider: if John is short, then Jane is tall

## biconditional

* **biconditional**
    * e.g. John is short if and only if Jane is tall
* the compound proposition expressed by this sentence is made up of the
proposition that John is short and the proposition that Jane is tall and the
connective **biconditional**
* the compound proposition expressed by 'John is short if and only if
    Jane is tall' is a **biconditional**
* the propositions expressed by 'John is short' is the **left-hand
    side** of the biconditional and the proposition expressed by 'Jane
    is tall' is the **right-hand side** of the biconditional
* biconditional is a **two-place connective**, because it connects two
    propositions
* biconditional is a **truth-functional connective**
* if the right-hand side and the left-hand side are either both true or both
false, then the conditional is true. it is false otherwise.
    * consider: John is short if and only if Jane is tall

## negation

* **negation**
    * John is not short
* the compound proposition expressed by this sentence is made up of the
proposition that John is short and the connective **negation**
* the compound proposition expressed by 'John is not short' is the
**negation** of the proposition expressed by 'John is short'
* the proposition expressed by 'John is short' is the **negand** of the
proposition expressed by 'John is not short'
* the proposition expressed by 'It is not the case that John is not short'
is the **double negation** of the proposition expressed by 'John is short'
* negation is a **one-place connective**, because it connects one
proposition
* the connective negation is a **truth-functional connective**
* if the negand is true, the negation is false, and if the negand is
    false, the negation is true
    * consider: John is not short

## connectives in disguise 

* for each connective there is a canonical bit of English used to express it 
* for negation we have "not" or "It is not the case that..." 
* for conjunction we have "...and..." 
* for disjunction we have "...or..." 
* for conditional we have "if .. then .. " 
* for biconditional we have "... if and only if ..."
* it turns out, however, that there are many ways of expressing these truth functional connectives in English 
* for conjunction we sometimes use "...but..."
* for conditional we might use "...only if..." or "...if..." or we might not use "if" at all 
* for biconditional we might use "...just in case..." or "...just when..." 
* the point is that propositions do not wear their form on their sleeves
* you must always ask: what kind of proposition is expressed by this sentence? 

## linguistic form and logical form 

* you might have noticed something strange about negation 
* it is strange in the sense that we say that it "connectives" just one proposition 
* but is also strange that we think that "not" is somehow used to express negation 
* compare "It is not the case that John is short" with "John is not short" 
* the former seems to capture the idea that negation is a one-place connective better than the latter 
* the sentence "John is short" expresses the proposition which is the negand 
* what expresses the proposition that is the negand in "John is not short"? 
* i want you to start to think critically about the relation between linguistic form and logical form
* why, for instance, should we not translate "Jane is unhappy" as a negation? (e.g. as "Jane is not happy")? 
* should we translate "This sentence is untrue" as "This sentence is not true"? 


# wrapping up

## this lecture

* basic and compound propositions
* truth functional connectives in English
    * conjunction
    * disjunction
    * conditional
    * biconditional
    * negation

## next lecture

* [lecture 03, the formal language PL](03_the_formal_language_PL.html)
