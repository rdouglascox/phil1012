---
title: lecture 03, the formal language PL
subtitle: phil1012 introductory logic
---

# overview

## this lecture

* an introduction to the formal language PL
* the vocabulary and syntax of PL
* how formulas of PL are constructed
* translating propositions from English into PL with the use of a glossary

## learning outcomes

* after doing the relevant reading for this lecture, listening to the lecture, and attending the relevant tutorial, you will be able to:
    * explain what the different symbols of PL mean
    * translate PL formulas into English
    * translate propositions from English into PL, providing a glossary for your translation
    * identify well-formed formulas of PL
    * construct construction tables for formulas of PL

## required reading

* :books: all of chapter 2

# the language of propositional logic (PL)

## the language of propositional logic (PL)

* the formal symbolic language of propositional logic (PL)
* the language of PL consists of a **vocabulary** and a **syntax**
* the vocabulary concerns the basic symbols
* the syntax concerns how basic symbols can be put together to form complex
symbols

# the vocabulary of PL

## sentence letters

* basic propositions are represented in PL by simple capital letters with or
without numerical subscripts
* they are called **sentence letters**
   * $A, A_2, A_3, \ldots B, B_2, B_3, \ldots, C, C_2, C_3, \ldots, Z, Z_2,
Z_3$
* suppose you want to use 'A' to represent the proposition expressed by the
sentence 'John is short'
* in order to do this you would write a **glossary** like this:
    * $A$: John is short
* we use sentence letters only for basic propositions. so the following is
not okay:
    * $A$: John is short and Jane is tall
* remember that a negation is not a basic proposition. so the following is
not okay:
    * $A$: John is not short
* more about glossaries and translations in the next lecture
* we have introduced symbols to represent propositions (sentence letters)
* now we introduce symbols to represent the **connectives**
    * $\lnot, \land, \lor, \rightarrow, \leftrightarrow$

## conjunction

* the connective conjunction is represented in PL by the symbol:
    * $\land$
* the name of the symbol is **caret**
* we can use caret to represent the conjunction of $A$ and $B$ as follows:
    * $(A \land B)$
* we can use this to represent the proposition that John is short and Jane is tall

## disjunction

* the connective disjunction is represented in PL by the symbol:
    * $\lor$
* the name of the symbol is **vel**
* we can use vel to represent the disjunction of $A$ and $B$ as follows:
    * $(A \lor B)$
* we can use this to represent the proposition that John is short or Jane is
tall

## conditional

* the connective conditional is represented in PL by the symbol:
    * $\rightarrow$
* the name of the symbol is **arrow**
* we can use arrow to represent a conditional with $A$ as its antecedent and $B$
as its consequent as follows:
    * $(A \rightarrow B)$
* we can use this to represent the proposition that if John is short,
    then Jane is tall

## biconditional

* the connective biconditional is represented in PL by the symbol:
    * $\leftrightarrow$
* the name of the symbol is **double arrow**
* we can use double arrow to represent a biconditional with $A$ as its left-hand side and $B$ as its right-hand side as follows:
    * $(A \leftrightarrow B)$
* we can use this to represent the proposition that John is short if and
only if Jane is tall

## negation

* the connective negation is represented in PL by the symbol:
    * $\lnot$
* the name of the symbol is **neg**
* we can use neg to represent a negation with $A$ as its negand as follows:
    * $\lnot A$
* we can use this to represent the proposition that John is not tall

## the connectives of PL

* here are the symbols for the connectives in PL:

:::table

  connective      name                 symbol
  --------------- -------------- -------------------
  negation        neg                  $\lnot$
  conjunction     caret                $\land$
  disjunction     vel                  $\lor$
  conditional     arrow             $\rightarrow$
  biconditional   double arrow    $\leftrightarrow$

:::

* different logic textbooks / books / articles may use different symbols for the same connectives
* you may want to learn what some of these are so that you can read more widely in logic 
* since the symbols are part of the definition of our language PL, you must use these symbols 
* other symbols can be used to define equivalent languages---languages that can express exactly the same connectives 
* but they will not be the *same* language as our language PL 
* so although the choice of symbols for the connectives is entirely
arbitrary, the choice we have made is final, and henceforth we will only use
these symbols
* you *will* get marked down for using the wrong symbols 

## auxiliary symbols

* in addition to the connectives, we need to introduce some punctuation symbols
* these are used to group the symbols of PL together 
* they are:
    * `(` and `)` 

# the syntax of PL

* we now have the most important parts of the vocabulary of PL: sentence
letters, connective symbols, and punctuation symbols '(' and ')'
* now we need to say how these can be put together

## the syntax of PL

* we are now ready to precisely state the syntax of PL
* the syntax of PL tells us which sequences of symbols taken from the vocabulary above are **well-formed formulas** (of **wffs**) of PL. 
* see the handout on the syntax of PL
* we use lowercase Greek letters like $\alpha$ and $\beta$ to express
general claims about the formulas of PL
* these are called **well-formed formula variables**
* well-formed formula variables can stand in for single sentence letters
like $A$ or for complex formulas like $(A \land B)$
* they are not part of the language of PL
* here, then, is our statement of the syntax of PL
* the symbols of PL are:
    * sentence letters (basic propositions):
        * $A, A_2, A_3, \ldots B, B_2, B_3, \ldots, C, C_2, C_3, \ldots, Z, Z_2, Z_3$
    * connectives:
        * $\lnot \hspace{6pt} \land \hspace{6pt} \lor \hspace{6pt} \rightarrow \hspace{6pt} \leftrightarrow$
    * punctuation symbols (parentheses):
        * $( \hspace{12pt} )$
* wffs of PL are then defined as follows:
    * any basic proposition is a wff
    * if $\alpha$ and $\beta$ are wffs, then so are:
        * $\lnot \alpha$
        * $(\alpha \land \beta )$
        * $(\alpha \lor \beta )$
        * $(\alpha \rightarrow \beta)$
        * $(\alpha \leftrightarrow \beta)$
    * nothing else is a wff
* the syntax of PL is specified by a **recursive definition**
* the **base clause** of the definition states certain things are wffs
* the **recursive clause** states that certain other things are wffs in
terms of things we already know to be wffs 

## some examples

* all of the following can be generated using this definition:
    * $((R\rightarrow P)\leftrightarrow R)$
    * $(B\leftrightarrow ((C\land A)\lor C))$
    * $\lnot (B\lor (B\leftrightarrow A))$
    * $((H\rightarrow G)\rightarrow (H\leftrightarrow (G\lor H)))$
    * $((Z\lor (((Y\lor Y)\land (Z\rightarrow Z))\lor Y))\lor Y)$
    * $(((C\lor ((G\leftrightarrow (D\land A))\rightarrow A))\lor I)\land ((D\leftrightarrow J)\leftrightarrow J))$

## some helpful divisions

* the symbols of PL can be divided into the following categories:
    * **logical symbols** (the connective symbols)
    * **nonlogical symbols** (sentence letters)
    * **auxiliary symbols** (parentheses)
* the nonlogical symbols do not have a fixed meaning and need to be
  specified in a glossary
* this is why you must always provide a **glossary** for your translations

## construction tables

* given this syntax for PL we can show how any well-formed formula of PL is
constructed
- having an explicit understanding of how a well-formed formula is constructed can be helpful when you are constructing proofs or attempting to work out the truth value of a formula
* suppose we want to construct $(\lnot P \land (Q \lor R))$
* we might construct it as follows using a **construction table**
* first we write out all of the sentence letters that appear in the formula

:::table

   step   wff constructed at this step   from steps/by clause
  ------ ------------------------------ ----------------------
    1                 $P$                       /(2i)
    2                 $Q$                       /(2i)
    3                 $R$                       /(2i)

:::

* we also write a justification for our writing down the sentence letters 
* in this case our justification is that clause 2i from the handout/book tells us that we we can start by writing down sentences letters
- now that we have these sentences letters, we can apply further rules to them

:::table

   step   wff constructed at this step   from steps/by clause
  ------ ------------------------------ ----------------------
    1                 $P$                       /(2i)
    2                 $Q$                       /(2i)
    3                 $R$                       /(2i)
    4              $\lnot P$               1 /(2ii $\lnot$)
    5             $(Q \lor R)$            2,3 /(2ii $\lor$)

:::

- this time we note both the justification and the line number we applied the clause/rule to
- and now we are in a position to construct the formula we set out to construct

:::table

   step   wff constructed at this step   from steps/by clause
  ------ ------------------------------ ----------------------
    1                 $P$                       /(2i)
    2                 $Q$                       /(2i)
    3                 $R$                       /(2i)
    4              $\lnot P$               1 /(2ii $\lnot$)
    5             $(Q \lor R)$            2,3 /(2ii $\lor$)
    6     $(\lnot P \land (Q \lor R))$   4, 5 /(2ii $\land$)

:::

* the other wffs in the construction are **subformulas** of the formula
* the connective added last in the construction is the **main connective**
* the main connectives gives its name to the formula it constructs

## alternative representations / syntax

* the same information from our construction table can be represented in the format of a tree 
- can you think of what such a tree would look like? 
- it is important to keep in mind that a well-formed formula is really just a sequence of symbols 
- on the syntax we have given, formulas do not have what is sometimes called "constituent structure" 

# wrapping up

## this lecture

* an introduction to the formal language PL
* the vocabulary and syntax of PL
* how formulas of PL are constructed

## next lecture 

* [lecture 4, lost in translation 1](04_lost_in_translation_1.html)
