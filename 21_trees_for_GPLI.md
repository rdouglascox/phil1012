---
title: "lecture 21, trees for GPLI"
subtitle: phil1012 introductory logic
---

# overview

## this lecture

* trees for GPLI
* two new tree rules
    * the closure rule
    * substitution of identicals
* finished trees and saturated paths
    * new definition of saturation
* reading models off open paths
    * provisional domains and assignments of referents
    * trimming domains and assignments of referents

## learning outcomes

* after doing the relevant reading for this lecture, listening to the lecture, and attending the relevant tutorial, you will be able to:
    *  explain what it is for a GPLI tree to be finished and a path to be saturated
    * construct GPLI trees
    * read models off open paths of GPLI trees

## required reading

* section 13.7 of chapter 13

# tree rules for gpli

## tree rules for gpli

* as in the transition from MPL to GPL we will build on our pre-existing tree rules
* since $=$ is part of the logical vocabulary, we need to say something
about the tree rules for it

## the closure rule

* the first new rule is called the **closure rule**

. . .

``` prooftree

\begin{prooftree}
{line numbering=false}
[\underline{a}\neq\underline{a}, close]
\end{prooftree}

```

* this basically says that you can close a path if there is a proposition on it which asserts that something is not identical to itself!
* the motivation for this rule should be obvious

## new notation explained

* recall that $\alpha(\underline{x})$ stands for any arbitrary wff that has
no free variables other than $\underline{x}$ and that
$\alpha(\underline{a}/\underline{x})$ stands for the wff that results from
$\alpha(\underline{x})$ by replacing *all* free occurrences of
$\underline{x}$ in $\alpha(\underline{x})$ with the name $\underline{a}$
* we use $\alpha(\underline{a})$ to stand for any arbitrary wff in which the
name $\underline{a}$ occurs (one or more times)
* we then use $\alpha(\underline{b}//\underline{a})$ to stand
for any wff which results from $\alpha(\underline{a})$ by replacing *some*
occurrences of $\underline{a}$ with the name $\underline{b}$

## some examples using the new notation

* if $\alpha(a)$ is $Ga$, then $\alpha(b//a)$ is $Gb$ and
$\alpha(c//a)$ is $Gc$
* if $\alpha(a)$ is $Rab$, then $\alpha(b//a)$ is $Rbb$ and
$\alpha(c//a)$ is $Rcb$
* if $\alpha(a)$ is $(Ga \lor Rab)$, then $\alpha(c//a)$ is
$(Gc \lor Rab)$ or $(Ga \lor Rcb)$ or $(Gc \lor Rcb)$
* if $\alpha(a)$ is $(Ga \rightarrow Rbb)$, then $\alpha(a//b)$
is $(Ga \rightarrow Rab)$ or $(Ga \rightarrow Rba)$ or $(Ga \rightarrow
Raa)$

## substitution of identicals

* the second new rule is called the **substitution of identicals** rule

. . .

``` prooftree

\begin{prooftree}
{line numbering=false}
[\alpha(\underline{a}) [{\underline{a}=\underline{b}}, just=(or {$\underline{b}=\underline{a}$}) [\alpha(\underline{b}/\hspace{-4pt}/\underline{a})]]]
\end{prooftree}

```

---

* let's run through an example . . .

---

``` prooftree

\begin{prooftree}
{line numbering=false, to prove={$To prove: whether $\forall x Lxr \land \forall y(Lry \rightarrow I^2ym) \therefore I^2mr $ is valid.$}}
[]
\end{prooftree}

```
---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $\forall x Lxr \land \forall y(Lry \rightarrow I^2ym) \therefore I^2mr $ is valid.$}}
[\forall x Lxr \land \forall y(Lry \rightarrow I^2ym) [\lnot I^2mr ]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $\forall x Lxr \land \forall y(Lry \rightarrow I^2ym) \therefore I^2mr $ is valid.$}}
[\forall x Lxr \land \forall y(Lry \rightarrow I^2ym) [\lnot I^2mr ]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $\forall x Lxr \land \forall y(Lry \rightarrow I^2ym) \therefore I^2mr $ is valid.$}}
[\forall x Lxr \land \forall y(Lry \rightarrow I^2ym), checked [\lnot I^2mr [\forall x Lxr [\forall y(Lry \rightarrow I^2ym)]]]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $\forall x Lxr \land \forall y(Lry \rightarrow I^2ym) \therefore I^2mr $ is valid.$}}
[\forall x Lxr \land \forall y(Lry \rightarrow I^2ym), checked [\lnot I^2mr [\forall x Lxr, subs=r [\forall y(Lry \rightarrow I^2ym), subs=r [Lrr [Lrr \rightarrow I^2rm]]]]]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $\forall x Lxr \land \forall y(Lry \rightarrow I^2ym) \therefore I^2mr $ is valid.$}}
[\forall x Lxr \land \forall y(Lry \rightarrow I^2ym), checked [\lnot I^2mr [\forall x Lxr, subs=r [\forall y(Lry \rightarrow I^2ym), subs=r [Lrr [Lrr \rightarrow I^2rm, checked [\lnot Lrr][I^2rm]]]]]]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $\forall x Lxr \land \forall y(Lry \rightarrow I^2ym) \therefore I^2mr $ is valid.$}}
[\forall x Lxr \land \forall y(Lry \rightarrow I^2ym), checked [\lnot I^2mr [\forall x Lxr, subs=r [\forall y(Lry \rightarrow I^2ym), subs=r [Lrr [Lrr \rightarrow I^2rm, checked [\lnot Lrr, close][I^2rm]]]]]]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $\forall x Lxr \land \forall y(Lry \rightarrow I^2ym) \therefore I^2mr $ is valid.$}}
[\forall x Lxr \land \forall y(Lry \rightarrow I^2ym), checked [\lnot I^2mr [\forall x Lxr, subs=r [\forall y(Lry \rightarrow I^2ym), subs=r [Lrr [Lrr \rightarrow I^2rm, checked [\lnot Lrr, close][I^2rm, close]]]]]]]
\end{prooftree}

```

* wrong!
* why? neither the closure rule nor the ordinary rule for closing a path applies here

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $\forall x Lxr \land \forall y(Lry \rightarrow I^2ym) \therefore I^2mr $ is valid.$}}
[\forall x Lxr \land \forall y(Lry \rightarrow I^2ym), checked [\lnot I^2mr [\forall x Lxr, subs=r [\forall y(Lry \rightarrow I^2ym), subs=r [Lrr [Lrr \rightarrow I^2rm, checked [\lnot Lrr][I^2rm [\lnot I^2 mm, just={2,7 SI}, close]]]]]]]]
\end{prooftree}

```

* right!

# finished trees, closed and saturated paths

## finished trees, closed and saturated paths

* a tree is finished when all paths are closed or saturated
* a tree is saturated when no more rules can be applied to it
* recall the qualification for the rule for the universal quantifier
* we add the following qualification for saturation

## saturation

* **saturation**: a path is not saturated unless every application of SI
that could be made on that path and that would result in the addition to the
path of a formula that does not already appear on the path has been made

---

* let's consider another example . . .

---

``` prooftree

\begin{prooftree}
{line numbering=true}
[Rab [I^2 ab ]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true}
[Rab [I^2 ab [Raa, just={1,2, SI 1=$\alpha(b)$} ]]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true}
[Rab [I^2 ab [Raa, just={1,2, SI 1=$\alpha(b)$} [Rbb, just={1,2, SI 1=$\alpha(a)$} ]]]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true}
[Rab [I^2 ab [Raa, just={1,2, SI 1=$\alpha(b)$} [Rbb, just={1,2, SI 1=$\alpha(a)$} [Rba, just={4,2, SI 4=$\alpha(b)$} ]]]]]
\end{prooftree}

```

* this tree is finished, as we cannot apply the SI rule to generate any new basic propositions (or negations of basic propositions)

# reading models off open paths

## reading models off open paths

* given a saturated open path, we can read off from it a model on which the
proposition(s) at the top of the tree are true
* the process involves three stages
    * stage one: construct a provisional domain and assignment of referents to names
    * stage two: trim the domain and assignments of referents to names to
obtain a final domain and assignment of referents to names
    * stage three: assign extensions to predicates on the trimmed domain and assignments of referents

---

* let's consider an example . . .

---

``` prooftree

\begin{prooftree}
{line numbering=false, to prove={$To prove: whether $Rab, I^2ab, \therefore Rbc $ is valid.$}}
[]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $Rab, I^2ab, \therefore Rbc $ is valid.$}}
[Rab [I^2ab [\lnot Rbc ]]]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $Rab, I^2ab, \therefore Rbc $ is valid.$}}
[Rab [I^2ab [\lnot Rbc [Raa [Rba [Rbb [\lnot Rac]]]]]]]]
\end{prooftree}


```

---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $Rab, I^2ab, \therefore Rbc $ is valid.$}}
[Rab [I^2ab [\lnot Rbc [Raa [Rba [Rbb [\lnot Rac]]]]]]]]
\end{prooftree}

```
* domain:
* referents:
* extensions:


---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $Rab, I^2ab, \therefore Rbc $ is valid.$}}
[Rab [I^2ab [\lnot Rbc [Raa [Rba [Rbb [\lnot Rac]]]]]]]]
\end{prooftree}

```

* domain: \{1, 2, 3\} (provisional)
* referents: $a$:1, $b$:2, $c$: 3 (provisional)
* extensions:


---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $Rab, I^2ab, \therefore Rbc $ is valid.$}}
[Rab [I^2ab, highlight wff [\lnot Rbc [Raa [Rba [Rbb [\lnot Rac]]]]]]]]
\end{prooftree}

```

* domain: \{1, 2, 3\} (provisional)
* referents: $a$:1, $b$:2, $c$: 3 (provisional)
* extensions:


---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $Rab, I^2ab, \therefore Rbc $ is valid.$}}
[Rab [I^2ab, highlight wff [\lnot Rbc [Raa [Rba [Rbb [\lnot Rac]]]]]]]]
\end{prooftree}

```

* domain: \{1, 2, 3\} (provisional)
* referents: $a$:1, $b$:1, $c$: 3 (revised)
* extensions:


---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $Rab, I^2ab, \therefore Rbc $ is valid.$}}
[Rab [I^2ab, highlight wff [\lnot Rbc [Raa [Rba [Rbb [\lnot Rac]]]]]]]]
\end{prooftree}

```

* domain: \{1, 2\} (revised)
* referents: $a$:1, $b$:1, $c$: 2 (revised)
* extensions:


---

``` prooftree

\begin{prooftree}
{line numbering=true, to prove={$To prove: whether $Rab, I^2ab, \therefore Rbc $ is valid.$}}
[Rab, highlight wff [I^2ab [\lnot Rbc [Raa, highlight wff [Rba, highlight wff [Rbb, highlight wff [\lnot Rac]]]]]]]]
\end{prooftree}

```

* domain: \{1, 2\} (revised)
* referents: $a$:1, $b$:1, $c$: 2 (revised)
* extensions: $R$: $\{\langle 1, 1 \rangle \}$

---

* let's consider another example . . .

---

``` prooftree

\begin{prooftree}
{line numbering=false, to prove={$To prove: whether $ \forall x(Fx \rightarrow Gx), \exists  x Fx, I^2ab, \therefore Ga $ is valid.$}}
[]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=false, to prove={$To prove: whether $ \forall x(Fx \rightarrow Gx), \exists  x Fx, I^2ab, \therefore Ga $ is valid.$}}
[\forall x(Fx \rightarrow Gx) [\exists  x Fx [I^2ab [\lnot Ga]]]]
\end{prooftree}

```

---

``` prooftree

\begin{prooftree}
{line numbering=false, to prove={$To prove: whether $ \forall x(Fx \rightarrow Gx), \exists  x Fx, I^2ab, \therefore Ga $ is valid.$}}
[\forall x(Fx \rightarrow Gx), subs={a,b,c} [\exists  x Fx, checked=c [I^2ab [\lnot Ga [Fa [Fa \rightarrow Ga, checked [\lnot Fa [Fb \rightarrow Gb, checked [\lnot Fb [Fc \rightarrow Gc, checked [\lnot Fc, close][Gc [\lnot Gb]]]][Gb [\lnot Gb, close]]]][Ga, close]]]]]]]
\end{prooftree}

```

* domain:
* referents:
* extensions:

---

``` prooftree

\begin{prooftree}
{line numbering=false, to prove={$To prove: whether $ \forall x(Fx \rightarrow Gx), \exists  x Fx, I^2ab, \therefore Ga $ is valid.$}}
[\forall x(Fx \rightarrow Gx), subs={a,b,c} [\exists  x Fx, checked=c [I^2ab [\lnot Ga [Fa [Fa \rightarrow Ga, checked [\lnot Fa [Fb \rightarrow Gb, checked [\lnot Fb [Fc \rightarrow Gc, checked [\lnot Fc, close][Gc [\lnot Gb]]]][Gb [\lnot Gb, close]]]][Ga, close]]]]]]]
\end{prooftree}

```

* domain: \{1, 2, 3\}
* referents: $a$: 1, $b$:2, $c$:3
* extensions:

---

``` prooftree

\begin{prooftree}
{line numbering=false, to prove={$To prove: whether $ \forall x(Fx \rightarrow Gx), \exists  x Fx, I^2ab, \therefore Ga $ is valid.$}}
[\forall x(Fx \rightarrow Gx), subs={a,b,c} [\exists  x Fx, checked=c [I^2ab, highlight wff [\lnot Ga [Fa [Fa \rightarrow Ga, checked [\lnot Fa [Fb \rightarrow Gb, checked [\lnot Fb [Fc \rightarrow Gc, checked [\lnot Fc, close][Gc [\lnot Gb]]]][Gb [\lnot Gb, close]]]][Ga, close]]]]]]]
\end{prooftree}

```

* domain: \{1, 2\}
* referents: $a$: 1, $b$:1, $c$:2
* extensions:

---

``` prooftree

\begin{prooftree}
{line numbering=false, to prove={$To prove: whether $ \forall x(Fx \rightarrow Gx), \exists  x Fx, I^2ab, \therefore Ga $ is valid.$}}
[\forall x(Fx \rightarrow Gx), subs={a,b,c} [\exists  x Fx, checked=c [I^2ab [\lnot Ga [Fc, highlight wff [Fa \rightarrow Ga, checked [\lnot Fa [Fb \rightarrow Gb, checked [\lnot Fb [Fc \rightarrow Gc, checked [\lnot Fc, close][Gc, highlight wff [\lnot Gb]]]][Gb [\lnot Gb, close]]]][Ga, close]]]]]]]
\end{prooftree}

```

* domain: \{1, 2\}
* referents: $a$: 1, $b$:1, $c$:2
* extensions: $F: \{2\}, G: \{2\}$

# wrapping up

## this lecture

* trees for GPLI
* two new tree rules
    * the closure rule
    * substitution of identicals
* finished trees and saturated paths
    * new definition of saturation
* reading models off open paths
    * provisional domains and assignments of referents
    * trimming domains and assignments of referents

## live lecture and tutorials

* you will practice constructing GPLI trees on your own

## next lecture

* [lecture 22, numerical quantifiers and definite descriptions in GPLI](22_numerical_quantifiers_and_definite_descriptions_in_GPLI.html)
