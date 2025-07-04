---
title: lecture 01, what is logic?
subtitle: phil1012 introductory logic
---

# overview

## this lecture

* what is logic?
* applications of formal/symbolic logic
* central concepts of logic:
    * propositions and truth
    * arguments
    * validity and soundness

## learning outcomes

* after doing the relevant reading for this lecture, listening to the lecture, and attending the relevant tutorial, you will be able to:
    * explain what logic is
    * determine whether a sentence expresses a proposition or not
    * explain what an argument is
    * represent ordinary language arguments in standard form
    * explain what it is for an argument to be valid
    * determine whether an argument is valid or invalid in an informal way

## required reading

* :books: sections 1.1, 1.2, 1.3, 1.4 and 1.5 of chapter 1

# what is logic? 

## what is logic?

* what is logic?
* logic, the subject, is **the systematic study of the laws of truth**
* logic is concerned, with the laws which govern the truth of propositions
* you can think of these claims as saying that *this* is what we mean by 'logic' in this class 

## logic and the laws of truth

* the subject matter of logic:
   * the laws of truth
   * the laws governing the truth of *propositions*
* laws of truth?
   * e.g. if a proposition has such and such a form, it must be true
   * e.g. if a set of propositions with such and such a form are all true, then a proposition with such and such a form must be true
   * we will develop more precise ways of formulating laws of truth as we go

## logic and logics

* this study of the laws of truth is often carried out using using formal languages and formal methods
* these formal languages are often called 'logics'
* these languages make it possible to study the laws of truth in a precise way
* in this unit we we cover two logics: propositional logic and predicate logic with identity 

## the history of logic

* logic, the subject, has a long history
* the history of logic is the history of the development of the study of the laws of truth
* the history of logic is the history of the development of formal languages and formal methods for studying the laws of truth
* Aristotle studied the laws of truth in the context of categorical propositions and categorical syllogisms
* he used variable symbols to represent classes of things and studied the relations between these classes
* he studied laws of truth like the following: if all A are B and all B are C, then all A are C.
* around the same time, the ancient stoics studied the laws of truth in the context of propositional logic
* they studied laws of truth like the following: if A then B, A, therefore B
* the study of propositional logic was updated and refined in the 19th century by Boole, De Morgan, and others
* around the turn of the 20th century, Frege, Russell, and others developed predicate logic
* they studied the laws of truth in the context of quantified propositions
* they used variables to represent objects and studied the relations between these objects
* it was only really in the 20th century that predicate logic received its canonical formulation

## formal/symbolic logic vs informal logic

* what are the varieties of logic?
    * formal/symbolic logic
    * informal/practical/applied logic or critical thinking
* both may deal with notions like (deductively) valid arguments
* formal logic is distinct in that it uses *formal methods* like translation into formal languages and formal proofs
* our aim might ultimately to be to understand the laws of truth, but we might also study the formal languages and proofs themselves 
* another part of the study of logic is the study of the formal languages and proofs themselves 
* this is sometimes called "metalogic" as opposed to "logic"

## logic and the laws of thought

* it is sometimes said that logic is the systematic study of the laws of *thought*
* but logic is not the study of the laws of thought or of human reasoning 
* logic concerns itself with the laws of truth, not the laws of thought
* a particular course of reasoning may be good because it accords with the laws of truth, but the laws of truth are explanatorily prior

# applications of formal/symbolic logic

## applications of formal/symbolic logic

* logic has various applications 
   * computer science
   * artificial intelligence 
   * linguistics
   * philosophy
   * the foundations of mathematics
* we focus on its application to
   * making the logical form of a proposition explicit
   * formally representing the structure of arguments
   * testing for the validity of arguments
* this will involve 
   * learning to translate English into a formal language
   * identifying the elements of arguments in English 
   * learning how to *prove* that an argument is valid
* the following quotation from one of the founders of modern symbolic logic, Whitehead, is apposite: 

> [Formal languages] have invariably been introduced to make things easy. By the aid of symbolism, we can make transitions in reasoning almost mechanically by the eye, which otherwise would call into play the higher faculties of the brain. Civilisation advances by extending the number of important operations which can be performed without thinking about them. (Whitehead 1919 *An Introduction to Mathematics*)

## applications of formal/symbolic logic 

* these are the main 'practical' skills we focus on in this unit
* this should help if you find yourself asking 'what's the point of this?'
* these applications are all very well
* but the aim of this course is to give you a much deeper understanding of what logic is
* recall that we aim to cover both the *how* and the *why* of logic
* so let's turn to some fundamental concepts

# propositions

## the laws of truth and propositions

* we said that logic is the systematic study of the laws of truth 
* and that the laws of truth govern the truth of propositions
* so what is a proposition?

## propositions

* think of propositions, in the first instance, as the kind of thing you might express when you assert that something is the case 
* you express a proposition when you assert that the sky is blue, that the earth is round, that the moon is made of cheese, and so on 
* you express the proposition that the sky is blue when you assert that the sky is blue
* what you assert is something that can be true or false 
* propositions are the primary bearers of truth and falsity
* the truth and falsity of propositions is what the laws of truth govern

## propositions and sentences

* propositions are not sentences, even though sentences are the kind of thing
  that can be true or false
* sentences can be said to *express* propositions
* a declarative sentence is true (as used in a context) if it expresses a true
  proposition and is false if it expresses a false proposition

## laws of truth for single propositions

* logic, as we will see, will often not itself tell us whether a proposition is true or false, but sometimes it will
* e.g. if a proposition has so-and-so a form, it must be true / it must be false

## laws of truth for sequences of propositions

* we are often more interested in the question of whether a proposition with some form or another *must be true* if a sequence of propositions with some other form or another are true
* these sequences are what we call **arguments** . . .

# arguments

## what is an argument?

* an **argument** is a sequence of propositions
* a **sequence** is a collection of objects in a particular order
* the final proposition in the sequence is the **conclusion** of the argument
* the other propositions in the sequence (if any) are the **premises** of the
  argument

## identifying conclusions

* in ordinary language, conclusions are often introduced by words like
  'therefore', 'hence', 'thus', 'so', 'it follows that'

## identifying premises 

* in ordinary language premises are often introduced by words like 'because',
  'since', and 'given that'

## an argument

* all humans are mortal. socrates is a human. therefore, socrates is mortal
* what is the conclusion of this argument?
* what are its premises?

## another one

* since all humans are mortal and socrates is a human, socrates is mortal 
* what is the conclusion of this argument?
* what are its premises?

## standard form

* we can represent the argument (in **standard form**) as follows:


::: arg

--------- ------------------------
   P1.    All humans are mortal
   P2.    Socrates is a human
   C1.    Socrates is mortal
--------- ------------------------

:::

* is this a good argument? why?
* this is a **valid** argument

## an argument

* all humans are mortal. socrates is not a human. therefore, socrates is not mortal
* what is the conclusion of this argument? what are its premises?

## another one

* since all humans are mortal and socrates is a human, socrates is not mortal
* what is the conclusion of this argument? what are its premises?

## in standard form

* we can represent the argument as follows:

::: arg

--------- --------------------------
  P1.     All humans are mortal
  P2.     Socrates is not a human
  C1.     Socrates is not mortal
--------- --------------------------

:::

* is this a good argument?
* this is an **invalid** argument
* bad arguments are arguments too

## good and bad arguments

* there are good arguments and there are bad arguments
* there are **valid** arguments and there are **invalid** arguments
* there are **sound** arguments and there are **unsound** arguments
* validity and soundness have precise definitions in logic . . .

# arguments and validity

## validity

* you are going to need to know what validity is in this course
* you should make sure you remember at least one of these equivalent ways of defining validity

1. an argument is **valid** if and only if, in virtue of its form, it is
  impossible for its conclusion to be false if its premises are true
2. an argument is **valid** if and only if, because of its form, the conclusion
  cannot be false if the premises are true
3. an argument is **valid** if and only if, in virtue of its form, the
  conclusion must be true if the premises are true
4. an argument is **valid** if and only if, because of its form, it is necessary
  for its conclusion to be true if its premises are true

* these are all equivalent 
* they each mention both *form* and the connection between the truth of the premises and the truth or falsity of the conclusion

## necessary truth preservation

* one important property a valid argument has is that of being necessarily truth preserving 
* if the premises of the argument are all true, then the conclusion must be true 
* it is not possible for the premises to all be true and for the conclusion to be false

::: arg

--------- ----------------------------------------------------
   P1.    If Anne ate the cake, she will get in trouble
   P2.    Anne ate the cake
   C1.    Anne will get in trouble
--------- ----------------------------------------------------

:::

* is it possible for the conclusion to be false if the premises of this
argument are all true?
* now consider another example:

::: arg

--------- ----------------------------------------------------
  P1.     If Anne ate the cake, she will get in trouble
  P2.     Anne will get in trouble
  C1.     Anne ate the cake
--------- ----------------------------------------------------

:::

* is it possible for the conclusion to be false if the premises of this
  argument are all true?
* must the conclusion be true if the premises are all true? 
* the important point for now: an argument is **valid** only if it is not
  possible for the conclusion to be false if all of the premises are true, that
  is only if it has the property of necessary truth preservation.
* but what about the part of the definition that mentions *form*? 
* what is it for an argument to be necessarily truth preserving *in virtue of its form*? 

## argument forms

* think about it like this: if you only need to know what the form of the
  argument is in order to see that it is necessarily truth preserving, then it
  is necessarily truth preserving in virtue of its form
* consider the following argument

::: arg

--------- ---------------------------------------------------------
  P1.     Either Anne ate the cake or Ben ate the cake
  P2.     Anne did not eat the cake
  C1.     Ben ate the cake
--------- ---------------------------------------------------------

:::

* it should be obvious that this is a valid argument 
* now consider another argument

::: arg

--------- ---------------------------------------------------------
  P1.     Either Carl is dancing or Danny is dancing 
  P2.     Carl is not dancing
  C1.     Danny is dancing
--------- ---------------------------------------------------------

* again, it should be obvious that this is a valid argument
* but notice that the previous two arguments have something in common 
* they are instances of the same argument form
* they are instances of the following argument form:

::: arg

--------- -----------------------
   P1.    Either **A** or **B**
   P2.    Not **A**
   C1.    **B**
--------- -----------------------

:::

* any argument with this form is a valid argument
* it is obvious that the values for **A** and **B** do not matter
* this is a valid argument form
* we have discovered a law of truth: any argument with premises of the form above and with a conclusion of the form above is such that it is not possible for all of its premises to be true while its conclusion is false
* since we do not need to know about the values for **A** and **B** we know that an argument of this form is necessarily truth preserving *in virtue of its form*: it is **valid**.


## more valid argument forms

* here are some familiar valid argument forms

::: arg

--------- ---------------------
  P1.     If **A** then **B**
  P2.     **A**
  C1.     **B**
--------- ---------------------

:::

* for instance: 

:::arg 

--------- -----------------------------------------
  P1.     If it is raining then the ground is wet
  P2.     It is raining
  C1.     The ground is wet
--------- -----------------------------------------

:::

* this is called **modus ponens** 
* here is another valid argument form:

::: arg

--------- ---------------------
   P1.    If **A** then **B**
   P2.    Not **B**
   C1.    Not **A**
--------- ---------------------

:::

* for instance: 

:::arg 

--------- -----------------------------------------
  P1.     If it is raining then the ground is wet
  P2.     The ground is not wet
  C1.     It is not raining
--------- -----------------------------------------

:::

* this is called **modus tollens** 
* here is another one:

::: arg

--------- ---------------------
  P1.     If **A** then **B**
  P2.     If **B** then **C**
  C1.     If **A** then **C**
--------- ---------------------

:::

* for instance:

:::arg 

--------- -----------------------------------------------------
  P1.     If it is raining then the ground is wet
  P2.     If the ground is wet then the grass is wet
  C1.     If it is raining then the grass is wet
--------- -----------------------------------------------------

:::

* this is called the **hypothetical syllogism** 
* explore some other valid argument forms in your own time
* informal logic textbooks treat valid argument forms at length

## validity and form

* at this stage, you might be wondering why we made such a big deal out of argument form 
* how could an argument be necessarily truth preserving if it does not have a valid argument form?
* well, sometimes it is impossible for the conclusion of an argument to be false if
  its premises are all true, but not in virtue of the form of the argument
* consider this argument:

::: arg

--------- -------------------------
  P1.     This chair is red
  C1.     This chair is coloured
--------- -------------------------

:::

* is it possible for the conclusion to be false if the premises of
    this argument are all true?
* no 
* but is it valid? 
* well, what is its form?

::: arg

--------- --------
  P1.     **A**
  C1.     **B**
--------- --------

:::

* this is not a valid argument form* to see why, we need only consider the
  following argument which has the same form, but whose conclusion can be false even when its premises are true

::: arg

--------- ---------------------
  P1.     This chair is red
  C1.     This chair is blue
--------- ---------------------

:::

* by the way, it isn't enough to show that some argument is an instance of an
  invalid form to conclude that it is not a valid argument 
* we must show that there is no valid argument form that the argument is an
  instance of
* more on this in the lecture on logical form
* :warning: beware! in other areas of philosophy, validity is often defined without
  reference to the form of the argument
* the notion of validity we are interested in is sometimes called **formal
  validity** to distinguish it from this sense of validity
* we are going to develop a more precise analysis of validity later
* we are going to develop a more precise conception of the form of an argument
* we are going to look at methods for determining whether a particular argument
  is formally valid

# soundness

## what is soundness?

* before wrapping up, let us look at one more property of arguments 
* we mainly look at this property in order to avoid confusion between it and validity
* this is the property of soundness
* an argument is **sound** if and only if (i) it is valid and (ii) all of its
  premises are true

## an argument

* consider this argument:

::: arg

--------- -----------------------------------------------------
   P1.    If Australia is a republic then it has a president
   P2.    Australia is a republic
   C1.    Australia has a president
--------- -----------------------------------------------------

:::

* is it valid? 
* is it sound? 

## another argument

* now consider this argument:

::: arg

--------- -----------------------------------------------------
   P1.    If Australia is a republic then it has a president
   P2.    Australia is not a republic
   C1.    Australia does not have a president
--------- -----------------------------------------------------

* it is valid? 
* is it sound? 

:::

## yet another argument

* consider one more argument:

::: arg

--------- -------------------------------------------------------
   P1.    If Australia is a republic then the monarchists lost
   P2.    If the monarchists lost then the republicans won
   C1.    If Australia is a republic then republicans won
--------- -------------------------------------------------------

:::

* it is valid? 
* is it sound? 

## validity and soundness

* don't confuse validity with soundness 
* an argument can be valid even if its premises are false 
* it can be valid if its conclusion is false 
* it just can't be valid if it is possible for its premises to all be true and for its conclusion to be false (at the same time)

# wrapping up

## this lecture

* what is logic?
* applications of formal/symbolic logic
* central concepts of logic:
    * propositions and truth
    * arguments
    * validity and soundness

## upcoming lectures

* [lecture 2, connectives and logical form](02_connectives_and_logical_form.html)
