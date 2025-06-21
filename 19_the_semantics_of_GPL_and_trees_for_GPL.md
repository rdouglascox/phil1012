---
title: lecture 19, the semantics of GPL and trees for GPL
subtitle: phil1012 introductory logic
---

# overview

## this lecture

* the semantics of GPL and trees for GPL
* the notion of sets of ordered n-tuples as extensions of n-place predicates in GPL

## learning outcomes

* after doing the relevant reading for this lecture, listening to the lecture, and attending the relevant tutorial, you will be able to:
    * explain how the truth values of atomic formulas are determined on a model in GPL
    * determine the truth value of a GPL proposition on a model
    * find a model on which a GPL proposition is true and/or a model on which a GPL proposition is false
    * construct trees using the tree rules for GPL
    * use trees to test for various logical properties of GPL formulas
    * read off (counter)models from open paths of GPL trees

## required reading

* sections 12.3 and 12.3 of chapter 12

# the semantics of GPL

## the semantics of GPL

* recall that the semantics for MPL proceeded in two stages.
* in the first stage we say what the values of nonlogical symbols are.
    A *model* is then *any* assignment of values to nonlogical symbols
    (together with a domain from which these values are drawn.
* in the second stage we specify how the truth values of all
    propositions (closed wffs) are determined, given values for their
    nonlogical components.

---

* in moving from MPL to GPL we have simply added many-place
    predicates.
* we need to say what the value of a many-place predicate is.
* the rest of the semantics is just like that of MPL.

---

* in MPL the extensions of one-place predicates were sets.
* why can't we use a set like {Bill, Bob} for the extension of the
    two-place predicate $L^2$?
* because {Bill, Bob} and {Bob, Bill} are the same set and we want to
    be about to say that Bill loves Bob without saying that Bob loves
    Bill.

---

* **extensionality of sets**: If everything in A is in B and vice
    versa then A = B.
*  {1, 2, 3} = {2, 1, 3} and {1, 2} = {1, 1, 2}.

---

* to solve this problem we introduce a new notion which indicates a group
of things *taken in order*.
* $\langle$ 1, 2, 3$\rangle$ $\neq$
    $\langle$ 2, 1, 3$\rangle$ and
    $\langle$ 1, 2$\rangle$ $\neq$
    $\langle$ 1, 1, 2$\rangle$.

---

* an ordered $n$-tuple is an ordered list of things with $n$ positions
    in the list 1st through $n$th.
* there need not be $n$ distinct things involved: the very same object
    might occupy more than one place in the list.
* an ordered 2-tuple is called an ordered pair and an ordered 3-tuple is
    called an ordered triple.

---

* the **extension** of an $n$-place predicate is a set of ordered $n$-tuples of members of the domain
* our new semantic clause looks like this:

1.  $\underline{P^{n}a_{1}} \ldots \underline{a_n}$ is true in
    $\mathcal{M}$ iff the ordered *n*-tuple consisting of the referents
    in $\mathcal{M}$ of $\underline{a_{1}}$ through $\underline{a_{n}}$
    in that order is in the extension in $\mathcal{M}$ of
    $\underline{P^{n}}$.

---

* let's work through some examples to get a feel for the semantics of GPL

---

* our model:
   * domain: {Alice, Bob, Carol, Dave, Edwina}\
   * referents: $a$: Alice, $b$: Bob, $c$: Carol, $d$: Dave, $e$: Edwina\
   * extensions: $M$: {Bob, Dave}, $F$: {Alice, Carol, Edwina}, $T$: {$\langle$Alice, Bob$\rangle$, $\langle$Alice, Carol$\rangle$, $\langle$Alice, Dave$\rangle$, $\langle$Alice, Edwina$\rangle$, $\langle$Bob, Carol$\rangle$, $\langle$ Bob, Dave$\rangle$, $\langle$Bob, Edwina$\rangle$, $\langle$Carol, Dave$\rangle$, $\langle$Carol, Edwina$\rangle$, $\langle$Dave, Edwina$\rangle$}
* are the following formulas true or false in this model?
* $Tab$
   * true. the referent of $a$, namely Alice, and the referent of $b$, namely Bob, taken in that order, are in the extension of $T$.
* $Tba$
   * false. the referent of $a$, namely Alice, and the referent of $b$, namely Bob, taken in that order, are not in the extension of $T$.
* $Tac$
   * true. the referent of $a$, namely Alice, and the referent of $c$, namely Carol, taken in that order, are in the extension of $T$.
* $Tce$
   * true. the referent of $c$, namely Carol, and the referent of $e$, namely Edwina, taken in that order, are in the extension of $T$.
* $Taa$
   * false. the referent of $a$, namely Alice, and the referent of $a$, namely Alice, taken in that order, are not in the extension of $T$.
* $Tee$
   * false. the referent of $e$, namely Edwina, and the referent of $e$, namely Edwina, taken in that order, are not in the extension of $T$.
* $Tbe$
   * true. the referent of $b$, namely Bob, and the referent of $e$, namely Edwina, taken in that order, are in the extension of $T$.

# trees for GPL

## trees for GPL

* in moving from MPL to GPL, we did not add any logical operators---so
    there are no new tree rules.
* the only change was that we added $n$-place predicates---and in the
    semantics, we added extensions for these (sets of $n$-tuples).
* so now all we need to do is see how to read off the extension of a
    many-place predicate from an open (saturated) path.

---

``` prooftree

\begin{prooftree}
{line numbering=true}
[Fa [\lnot Fb [Gc [Ga]]]]
\end{prooftree}

```

* domain: {1, 2, 3}
* referents: a: 1, b: 2, c: 3
* extensions: F: {1}, G: {1, 3}

---

``` prooftree

\begin{prooftree}
{line numbering=true}
[Taa [\lnot Tbc [Tab]]]
\end{prooftree}

```

* domain: {1, 2, 3}\
* referents: a: 1, b: 2, c: 3\
* extensions: T: {$\langle$ 1,1 $\rangle$, $\langle$ 1,2 $\rangle$}

---

``` prooftree

\begin{prooftree}
{line numbering=true}
[Babc [\lnot Bccc [Bbcd [Baaa]]]]
\end{prooftree}

```

* domain: {1, 2, 3, 4}\
* referents: a: 1, b: 2, c: 3, d: 4\
* extensions: B: {$\langle$ 1, 2, 3 $\rangle$, $\langle$ 2, 3, 4 $\rangle$, $\langle$ 1, 1, 1 $\rangle$}

## example 1

---

``` prooftree

\begin{prooftree}
{line numbering=false, to prove={$To prove: whether $ \exists x \forall y Lxy \therefore \forall y \exists x Lxy  $ is valid.$}}
[]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists x \forall y Lxy \therefore \forall y \exists x Lxy  $ is valid.$}}
[\exists x \forall y Lxy [\lnot \forall y \exists x Lxy]]
\end{prooftree}

```

---

``` prooftree


\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists x \forall y Lxy \therefore \forall y \exists x Lxy  $ is valid.$}}
[\exists x \forall y Lxy [\lnot \forall y \exists x Lxy, checked [\exists y \lnot \exists x Lxy]]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists x \forall y Lxy \therefore \forall y \exists x Lxy  $ is valid.$}}
[\exists x \forall y Lxy, checked=a [\lnot \forall y \exists x Lxy, checked [\exists y \lnot \exists x Lxy [\forall y Lay ]]]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists x \forall y Lxy \therefore \forall y \exists x Lxy  $ is valid.$}}
[\exists x \forall y Lxy, checked=a [\lnot \forall y \exists x Lxy [\exists y \lnot \exists x Lxy, checked=b [\forall y Lay [\lnot \exists y Lxb ]]]]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists x \forall y Lxy \therefore \forall y \exists x Lxy  $ is valid.$}}
[\exists x \forall y Lxy, checked=a [\lnot \forall y \exists x Lxy, checked [\exists y \lnot \exists x Lxy, checked=b [\forall y Lay [\lnot \exists y Lxb, checked [\forall x \lnot Lxb]]]]]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists x \forall y Lxy \therefore \forall y \exists x Lxy  $ is valid.$}}
[\exists x \forall y Lxy, checked=a [\lnot \forall y \exists x Lxy, checked [\exists y \lnot \exists x Lxy, checked=b [\forall y Lay, subs=b [\lnot \exists y Lxb, checked [\forall x \lnot Lxb [Lab]]]]]]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists x \forall y Lxy \therefore \forall y \exists x Lxy  $ is valid.$}}
[\exists x \forall y Lxy, checked=a [\lnot \forall y \exists x Lxy, checked [\exists y \lnot \exists x Lxy, checked=b [\forall x Lay, subs=b [\lnot \exists y Lxb, checked [\forall x \lnot Lxb, subs=a [Lab [\lnot Lab]]]]]]]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists x \forall y Lxy \therefore \forall y \exists x Lxy  $ is valid.$}}
[\exists x \forall y Lxy, checked=a [\lnot \forall y \exists x Lxy, checked [\exists y \lnot \exists x Lxy, checked=b [\forall x Lay, subs=b [\lnot \exists y Lxb, checked [\forall x \lnot Lxb, subs=a [Lab [\lnot Lab, close]]]]]]]]
\end{prooftree}

```

## example 2

---

``` prooftree

\begin{prooftree}
{line numbering=false, to prove={$To prove: whether $ \exists y \forall x Lxy \therefore \forall x \exists y Lxy  $ is valid.$}}
[]
\end{prooftree}

```
---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists y \forall x Lxy \therefore \forall x \exists y Lxy  $ is valid.$}}
[\exists y \forall x Lxy [\lnot \forall x \exists y Lxy]]
\end{prooftree}

```
---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists y \forall x Lxy \therefore \forall x \exists y Lxy  $ is valid.$}}
[\exists y \forall x Lxy [\lnot \forall x \exists y Lxy, checked [\exists x \lnot \exists y Lxy]]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists y \forall x Lxy \therefore \forall x \exists y Lxy  $ is valid.$}}
[\exists y \forall x Lxy, checked=a [\lnot \forall x \exists y Lxy, checked [\exists x \lnot \exists y Lxy [\forall x Lxa]]]]
\end{prooftree}

```
---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists y \forall x Lxy \therefore \forall x \exists y Lxy  $ is valid.$}}
[\exists y \forall x Lxy, checked=a [\lnot \forall x \exists y Lxy, checked [\exists x \lnot \exists y Lxy, checked=b [\forall x Lxa [\lnot \exists y Lby]]]]]]
\end{prooftree}

```
---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists y \forall x Lxy \therefore \forall x \exists y Lxy  $ is valid.$}}
[\exists y \forall x Lxy, checked=a [\lnot \forall x \exists y Lxy, checked [\exists x \lnot \exists y Lxy, checked=b [\forall x Lxa [\lnot \exists y Lby, checked [\forall y \lnot Lby]]]]]]
\end{prooftree}

```
---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists y \forall x Lxy \therefore \forall x \exists y Lxy  $ is valid.$}}
[\exists y \forall x Lxy, checked=a [\lnot \forall x \exists y Lxy, checked [\exists x \lnot \exists y Lxy, checked=b [\forall x Lxa, subs=b [\lnot \exists y Lby, checked [\forall y \lnot Lby [Lba ]]]]]]]
\end{prooftree}

```
---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists y \forall x Lxy \therefore \forall x \exists y Lxy  $ is valid.$}}
[\exists y \forall x Lxy, checked=a [\lnot \forall x \exists y Lxy, checked [\exists x \lnot \exists y Lxy, checked=b [\forall x Lxa, subs=b [\lnot \exists y Lby, checked [\forall y \lnot Lby, subs=a [Lba [\lnot Lba]]]]]]]]
\end{prooftree}

```
---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists y \forall x Lxy \therefore \forall x \exists y Lxy  $ is valid.$}}
[\exists y \forall x Lxy, checked=a [\lnot \forall x \exists y Lxy, checked [\exists x \lnot \exists y Lxy, checked=b [\forall x Lxa, subs=b [\lnot \exists y Lby, checked [\forall y \lnot Lby, subs=a [Lba [\lnot Lba, close]]]]]]]]
\end{prooftree}

```

## example 3

---

``` prooftree

\begin{prooftree}
{line numbering=false, to prove={$To prove: whether $ \exists x (Hx \land Tax) \rightarrow \exists x (Ax \land Tax) $ a tautology.$}}
[]
\end{prooftree}

```
---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists x (Hx \land Tax) \rightarrow \exists x (Ax \land Tax) $ a tautology.$}}
[\lnot ( \exists x (Hx \land Tax) \rightarrow \exists x (Ax \land Tax))]
\end{prooftree}

```
---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists x (Hx \land Tax) \rightarrow \exists x (Ax \land Tax) $ a tautology.$}}
[\lnot ( \exists x (Hx \land Tax) \rightarrow \exists x (Ax \land Tax)), checked [\exists x (Hx \land Tax) [\lnot \exists x (Ax \land Tax)]]]
\end{prooftree}

```
---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists x (Hx \land Tax) \rightarrow \exists x (Ax \land Tax) $ a tautology.$}}
[\lnot ( \exists x (Hx \land Tax) \rightarrow \exists x (Ax \land Tax)), checked [\exists x (Hx \land Tax) [\lnot \exists x (Ax \land Tax), checked [\forall x \lnot (Ax \land Tax)]]]]
\end{prooftree}

```
---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists x (Hx \land Tax) \rightarrow \exists x (Ax \land Tax) $ a tautology.$}}
[\lnot ( \exists x (Hx \land Tax) \rightarrow \exists x (Ax \land Tax)), checked [\exists x (Hx \land Tax), checked=b [\lnot \exists x (Ax \land Tax), checked [\forall x \lnot (Ax \land Tax) [Hb \land Tab]]]]]
\end{prooftree}

```
---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists x (Hx \land Tax) \rightarrow \exists x (Ax \land Tax) $ a tautology.$}}
[\lnot ( \exists x (Hx \land Tax) \rightarrow \exists x (Ax \land Tax)), checked [\exists x (Hx \land Tax), checked=b [\lnot \exists x (Ax \land Tax), checked [\forall x \lnot (Ax \land Tax) [Hb \land Tab, checked [Hb [Tab]]]]]]]
\end{prooftree}

```
---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists x (Hx \land Tax) \rightarrow \exists x (Ax \land Tax) $ a tautology.$}}
[\lnot ( \exists x (Hx \land Tax) \rightarrow \exists x (Ax \land Tax)), checked [\exists x (Hx \land Tax), checked=b [\lnot \exists x (Ax \land Tax), checked [\forall x \lnot (Ax \land Tax), subs={b} [Hb \land Tab, checked [Hb [Tab [\lnot (Ab \land Tab)]]]]]]]]
\end{prooftree}

```
---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists x (Hx \land Tax) \rightarrow \exists x (Ax \land Tax) $ a tautology.$}}
[\lnot ( \exists x (Hx \land Tax) \rightarrow \exists x (Ax \land Tax)), checked [\exists x (Hx \land Tax), checked=b [\lnot \exists x (Ax \land Tax), checked [\forall x \lnot (Ax \land Tax), subs={b} [Hb \land Tab, checked [Hb [Tab [\lnot (Ab \land Tab), checked [\lnot Ab][\lnot Tab]]]]]]]]]
\end{prooftree}

```
---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists x (Hx \land Tax) \rightarrow \exists x (Ax \land Tax) $ a tautology.$}}
[\lnot ( \exists x (Hx \land Tax) \rightarrow \exists x (Ax \land Tax)), checked [\exists x (Hx \land Tax), checked=b [\lnot \exists x (Ax \land Tax), checked [\forall x \lnot (Ax \land Tax), subs={b} [Hb \land Tab, checked [Hb [Tab [\lnot (Ab \land Tab), checked [\lnot Ab][\lnot Tab, close]]]]]]]]]
\end{prooftree}

```
---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists x (Hx \land Tax) \rightarrow \exists x (Ax \land Tax) $ a tautology.$}}
[\lnot ( \exists x (Hx \land Tax) \rightarrow \exists x (Ax \land Tax)), checked [\exists x (Hx \land Tax), checked=b [\lnot \exists x (Ax \land Tax), checked [\forall x \lnot (Ax \land Tax), subs={b, a} [Hb \land Tab, checked [Hb [Tab [\lnot (Ab \land Tab), checked [\lnot Ab [\lnot(Aa \land Taa)]][\lnot Tab, close]]]]]]]]]
\end{prooftree}

```
---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists x (Hx \land Tax) \rightarrow \exists x (Ax \land Tax) $ a tautology.$}}
[\lnot ( \exists x (Hx \land Tax) \rightarrow \exists x (Ax \land Tax)), checked [\exists x (Hx \land Tax), checked=b [\lnot \exists x (Ax \land Tax), checked [\forall x \lnot (Ax \land Tax), subs={b, a} [Hb \land Tab, checked [Hb [Tab [\lnot (Ab \land Tab), checked [\lnot Ab [\lnot(Aa \land Taa), checked [\lnot Aa][\lnot Taa]]][\lnot Tab, close]]]]]]]]]
\end{prooftree}

```

* domain:
* referents:
* extensions:

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists x (Hx \land Tax) \rightarrow \exists x (Ax \land Tax) $ a tautology.$}}
[\lnot ( \exists x (Hx \land Tax) \rightarrow \exists x (Ax \land Tax)), checked [\exists x (Hx \land Tax), checked=b [\lnot \exists x (Ax \land Tax), checked [\forall x \lnot (Ax \land Tax), subs={b, a} [Hb \land Tab, checked [Hb [Tab [\lnot (Ab \land Tab), checked [\lnot Ab [\lnot(Aa \land Taa), checked [\lnot Aa][\lnot Taa]]][\lnot Tab, close]]]]]]]]]
\end{prooftree}

```

* domain: \{1, 2\}
* referents: $a$: 1, $b$:2
* extensions:

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $ \exists x (Hx \land Tax) \rightarrow \exists x (Ax \land Tax) $ a tautology.$}}
[\lnot ( \exists x (Hx \land Tax) \rightarrow \exists x (Ax \land Tax)), checked [\exists x (Hx \land Tax), checked=b [\lnot \exists x (Ax \land Tax), checked [\forall x \lnot (Ax \land Tax), subs={b, a} [Hb \land Tab, checked [Hb, highlight wff [Tab, highlight wff [\lnot (Ab \land Tab), checked [\lnot Ab [\lnot(Aa \land Taa), checked [\lnot Aa][\lnot Taa]]][\lnot Tab, close]]]]]]]]]
\end{prooftree}

```

* domain: \{1, 2\}
* referents: $a$: 1, $b$:2
* extensions: $H$: \{2\}, $T$: \{ $\langle$ 1, 2 $\rangle$ \}, $A$: \{\}

* note: this handout contains a correction from the lecture regarding the extension of $A$

# wrapping up

## this lecture

* trees for GPL
* reading models off open paths

## next lecture

* [lecture 20, the formal language GPLI](20_the_formal_language_GPLI.html)
