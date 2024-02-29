[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/wM4-KOzy)
# Little-o

In addition to the big-O, big-$\Omega$, and big-$\Theta$ notation that
we covered at the beginning of this class, a few other notations are sometimes
used in asymptotic analysis.  For example, "little-$o$" notation.

Prove (i.e.\ give a formal mathematical proof) that $f(n)\in o(g(n))$ implies
that $f(n)\in O(g(n))$.

Hint: The proof will be *very* short and *very* easy. You can start by
identifying the differences between the definitions of O and o.

I have started with the formal definition of $o$ below. Add your answer to this
markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

### Proof

__Given Definitions__: <br>
$f(n)\in o(g(n)) \iff \forall c>0, \exists n_0: f(n) \leq c g(n) \forall n\ge n_0$<br>
$f(n)\in O(g(n)) \iff \exists c>0, \exists n_0 : f(n) \leq c g(n) \forall n\ge n_0$<br>

__Proof__:<br>
$f(n)\in o(g(n)) \implies f(n)\in O(g(n))$<br>
$\implies (\forall c>0, \exists n_0: f(n) \leq c g(n) (\forall n\ge n_0) \implies f(n)\in O(g(n)))$ {definition of $f(n)\in o(g(n))$}<br>
$\implies (\forall c>0, \exists n_0: f(n) \leq c g(n) (\forall n\ge n_0) \implies \exists c>0, \exists n_0 : f(n) \leq c g(n) (\forall n\ge n_0))$ {definition of $f(n)\in O(g(n))$}<br>

$\implies True$ {Predicate and propositional logic}<br>

Q.E.D.

The reason why we can say this is that the definitions differ  in $c$: Little-O must be true for all $c$, but Big-O must be true for some $c$. However, the conditions remain the same for $n$, $f(n)$, and $g(n)$ for each definition. Therefore, we can conclude with propositional reasoning that if $f(n)$ is in $o(n)$ with all $c$, it _must_ be true that $f(n)$ is in $O(n)$ as there exists a $c$ where all $c > 0$ meets the conditions in $O(n)$.

# Sources:
- https://github.com/COSC3020/little-o-proof-egkallas - I worked with Evan Kallas with this review.
