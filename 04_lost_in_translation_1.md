---
title: "lecture 04, lost in translation 1"
subtitle: phil1012 introductory logic
---

# overview

## last lecture 

* in the last lecture we introduced the formal language PL
* one thing we did not discuss was how to translate sentences of English into PL

## this lecture

* in this lecture we take up the issue of translating English sentences into PL
* we also say a little bit about translating PL back into English
* we talk briefly about the distinction between what is said and what is merely implied or implicated by an utterance of a sentence

## learning outcomes

* after doing the relevant reading for this lecture, listening to the lecture, and attending the relevant tutorial, you will be able to:
    * explain the difference between what is said, what is implied, and what is implicated by the utterance of a sentence
    * distinguish between what is said, the proposition expressed by an utterance of a sentence in a context, and what is merely implied or implicated by an utterance of a sentence in a context
    * translate English sentences into PL using a glossary of symbols

## required reading

* :books: section 6.1 of chapter 6

# translating English sentences into PL 

## translating English sentences into PL 

* translating English sentences into PL is a bit like translating from one natural language into another 
* when translating from English into PL, we are aiming to capture the **truth conditions** of the English sentence in PL
* earlier we learned about the connectives and the corresponding English expressions 
* we used 'and' to introduce conjunction $\land$ 
* we used 'or' to introduce disjunction $\lor$ 
* we used 'if . . . then' to introduce the conditional $\rightarrow$  
* we used 'not' to introduce negation $\lnot$  
* we also learned about the idea of a basic proposition as opposed to a compound proposition 
* when we are translating English into PL we will want to identify the basic propositions in the English sentence
* and we will want to identify the connectives that connect these basic propositions
* one important thing to keep in mind is that negations are compound propositions
* the proposition expressed by "Jane is not tall" is a compound proposition 
* it is made up of the basic proposition "Jane is tall" and connective negation $\lnot$

## glossaries

* we translate basic propositions using symbols like: $A$, $B$, $C$, etc.
* but we need a way of keeping track of what these symbols stand for  
* so we use a **glossary** 
* a glossary is a list of symbols and their meanings
* here is an example of a glossary:
    * $A$: Jane is tall
    * $B$: Jane is smart
    * $C$: Jane is happy
* we can use this glossary to translate "Jane is tall and Jane is smart but Jane is not happy" as:
    * $((A \land B) \land \lnot C)$

## translating English sentences into PL 

* often English sentences do not wear their form on their sleeve, and you will have to think about how to translate them 
* the question to ask yourself when faced with an English sentence is this: what is the main connective? 
* then, of each of the parts of the sentence, ask yourself: what is the main connective?  
* keep doing this until you have identified the basic propositions and the connectives that connect them
* one thing you'll quickly discover is that a proposition may be a conjunction even though it doesn't involve the word 'and' 
* the following is a conjunction even though it doesn't involve the word 'and': Jane is tall but smart 
* another thing you'll discover is that sometimes you need to 'expand' the English sentence to see its logical form  
* this is the case when you encounter a conjunctive or disjunctive noun, verb, or adjectival phrase 

## expanding conjunctive phrases

* consider the following sentence: 
    * Jane and John are tall 
* this sentence is a conjunction of two propositions: Jane is tall, John is tall (namely: $A \land B$)
* consider the following sentence: 
    * Jane is tall and smart 
* this sentence is a conjunction of two propositions: Jane is tall, Jane is smart (namely: $A \land B$)

## expanding disjunctive phrases 

* consider the following sentence:
    * Jane or John is tall 
* this sentence is a disjunction of two propositions: Jane is tall, John is tall (namely: $A \lor B$)
* consider the following sentence:
    * Jane is tall or smart 
* this sentence is a disjunction of two propositions: Jane is tall, Jane is smart (namely: $A \lor B$)

## linguistic form and logical form 

* i said I wanted to encourage you to think critically about the relation between linguistic form and logical form 
* how plausible is it to think that "Jane and John are tall" expresses a proposition that would be better captured with "Jane is tall and John is tall"? 
* should we say that PL is inadequate to translate "Jane and John are tall"? 
* or should we accept that ordinary language (like English) does not wear its logical form on its sleeves? 
* it looks like the following is a valid argument: "Jane and John are tall, therefore Jane is tall". 
* it looks like it is an instance of the valid argument form: "**A** and **B**, therefore **A**". 
* so perhaps our translation is adequate after all? 
* after all, at the end of the day our aim is to capture the laws of truth 
* if we are aiming to capture the laws of truth here, our translation looks like it would help


## making ellipses explicit

* English sentences often involve ellipsis 
* for instance: 
  * Jane is tall and John is too. 
  * Jane is tall and so is John. 
* don't include things like this in your glossary: 
  * $A$: John is too. 
* you should always "expand" the English sentence to make the ellipsis explicit 
* a better glossary would be: 
  * $A$: Jane is tall 
  * $B$: John is tall 

## capturing the logical form of the proposition 

* as the unit goes on, you will become increasingly tempted to translate English sentences into PL using propositions that are truth-conditionally equivalent to the proposition you are trying to translate but which doesn't have the same logical form 
* for instance, you might be asked to translate "it is not the case that Jane is not tall" 
* you might translate this as follows: 
   * here's my glossary: $A$: Jane is tall 
   * here's my translation: $A$
* but this doesn't capture the form of the original proposition 
* the original proposition is a negation of a negation  
* so you should translate it as follows: 
  * $A$: Jane is tall 
  * $\lnot \lnot A$
* :warning: side note, what is wrong with: $\lnot (\lnot A)$?

## adequacy of translations

* ah, but how can you say that when you tell us that we should translate conjunctive phrases as conjunctions of sentences? 
* you might have convinced us with your argument and conjunctive noun phrases 
* but what about conjunctive verb phrases
* you just told us to translate "Anne is tall and smart" as ($A \land B$) 
* but ($A \land B$) captures the form of "Anne is tall and Anne is smart" 
* it doesn't capture the form of "Anne is tall and smart"
* okay, okay. 
* what I should say is that you should aim to capture the logical form of the proposition or you should translate the proposition in the way we tell you to translate it!
* a better translation for "Anne is tall and smart" requires a different formal
  language 
* we could translate it as follows: 
  * $(\lambda x . (Tx \land Sx))(a)$
* but even the most expressive language we consider in this course can't
  express *this*!
* question: does this translation make the following an instance of a valid
  argument form: "Anne is tall and smart, therefore Anne is tall"? (to answer
  this, you would need to study the logical language this expression is an
  expression of).
* so what precisely do I mean when I ask whether our translation is adequate?
  i mean: "is it good enough, that is, does it capture the truth conditions of
  the original sentence and does it capture the most important aspects of the
  form (those aspects that enter into our assessment of whether arguments
  involving it are valid? 
* translating conjunctive verb phrases as conjunctions is clearly adequate in this sense
* but it doesn't capture everything about the form of the proposition we might want to capture

## a note on translating English conditionals into PL 

* finally, note that "if" doesn't always introduce the antecedent of a conditional  
* it does in "if Jane is tall then Jane is smart" 
* and it does in "Jane is smart if Jane is tall"
* but it doesn't in "Jane is tall only if she is smart" 
* the inclusion of "only" before "if" reverses the role of "if"
* just remember this where "A" is for antecedent, and "C" for consequent": 
  * if **A**, then **C** = $(A\rightarrow C)$ 
  * if **A**, **C** = $(A\rightarrow C)$ 
  * **C** if **A** = $(A\rightarrow C)$  
  * **A** only if **C** = $(A\rightarrow C)$ 
  * only if **C**, **A** = $(A\rightarrow C)$ 

# what is said and what is merely implicated

## what is said and what is merely implicated

* one of the main challenges, when translating English sentences into PL, is to capture the **truth conditions** of the English sentence
* the truth conditions relate to what would make the English sentence true or false in a given context 
* there is an important distinction between 
    * what is **said** when someone utters a sentence
    * what is **implicated** or implied when someone utters a sentence
* consider an example:
    * you: Did you pass the exam?
    * me: If I didn't, I'm fool
* what is **said**: if I didn't pass the exam, I am a fool
    * $P$: I passed the exam
    * $F$: I am a fool
    * translation: $(\lnot P \rightarrow F)$
* what is **implicated**: I passed the exam
    * $P$: I passed the exam
    * $F$: I am a fool
    * translation: $P$
* what's the point of knowing the distinction between what is said and what is implicated by an utterance?
* well, we are aiming to translate what is said by an utterance; we are aiming to translate the proposition expressed by an utterance of a sentence
* so it is important to be able to distinguish between what is said and what is merely implicated or implied
* in light of all of this, think about how we should translate: 
  * Jane is tall but shy

# lots of examples 

## lots of examples

* let's do some examples together 
* we will translate some English sentences into PL 
  * Jane is going to the party only if John is 
  * Jane is going to the party and John is not 
  * Bill and Sue are going to the party 
  * Only if Jane is going to the party are Bill and Sue
  * If and only if Jane is going to the party is Bill crying 
  * It is not the case that John and Jane are going to the party
  * Both John and Jane are not going to the party 
  * Neither John nor Jane are going to the party 
  * It is not the case that it is not the case that John smokes
  * It is the case that that it is not the case that John smokes 

## now for some challenging examples 

* these examples are a bit more challenging  
* the connective involved is not so obvious
* let's translate them into PL 
  * Jane is tall but not happy
  * Unless Jane is tall, she is not smart  
  * Supposing that Jane is tall, she is smart 
  * Only supposing that Jane is tall is she smart
  * Just in case Jane is tall, she is smart  
  * Jane is tall just if she is smart  
  * Jane is tall if but only if she is smart  
  * Jane is tall on the condition that she is smart  
  * Only on the condition that Jane is tall is she smart  

## examples going in the other direction

* let's translate some examples into English  
* here's our glossary: 
  * $A$: Jane is tall  
  * $B$: Jane is smart   
  * $C$: Jane is happy   
* translate these into English:
  * $A \land B \land \lnot C$ 
  * $A \lor B \lor C$  
  * $\lnot A \land \lnot B \land \lnot C$   
  * $\lnot A \lor \lnot B \lor \lnot C$    
  * $\lnot (A \land B \land C)$   
  * $\lnot (A \lor B \lor C)$   
  * $\lnot \lnot A$    
  * $\lnot \lnot \lnot A$    
  * $\lnot (A \land B)$     
  * $\lnot (A \lor B)$

# wrapping up

## this lecture

* we took up the issue of translating English sentences into PL
* we looked at some important distinctions in the philosophy of language which can help us with our translations
* we are aiming, in our translations, to capture only what is said, not what is implied or implicated by an utterance

## next lecture

* [lecture 05, the semantics of PL](05_the_semantics_of_PL.html) 



