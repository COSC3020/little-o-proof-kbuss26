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
$f(n)\in o(g(n)) \iff \forall c>0, \exists n_0, \forall n\ge n_0: f(n) < c g(n)$<br>
$f(n)\in O(g(n)) \iff \exists c>0, \exists n_0, \forall n\ge n_0: f(n) < c g(n)$<br>

__Proof__:<br>
$f(n)\in o(g(n)) \implies f(n)\in O(g(n))$<br>
$\implies \forall c>0, \exists n_0, \forall n\ge n_0: f(n) < c g(n) \implies f(n)\in O(g(n))$ {definition of $f(n)\in o(g(n))$}<br>
$\implies (\forall c>0, \exists n_0, \forall n\ge n_0: f(n) < c g(n)) \implies (\exists c>0, \exists n_0, \forall n\ge n_0: f(n) < c g(n))$ {definition of $f(n)\in O(g(n))$}<br>
$\implies (\forall c>0, \exists n_0, \forall n\ge n_0: f(n) < c g(n)) \implies (\exists c_1>0, \exists n_2, \forall n_1\ge n_2: f(n_1) < c_1 g(n_1))$ {rename duplicate variables}

$\implies \forall n_0, \exists c_1>0, \exists c>0, \exists n_2, \exists n\ge n_0, \forall n_1\ge n_2: (f(n) < c_1 g(n) \implies f(n_1) < c_1 g(n_1))$ {migrate variables}<br>
$\implies \exists n_2, \exists n\ge n_c, \forall n_1\ge n_2: (f(n) < 1 * g(n) \implies f(n_1) < 1 * g(n_1))$ {remove $n_0 = n_c, c_1 = c, c = 1$}<br>
$\implies \forall n_1\ge n_c: (f(n_1) < g(n_1) \implies f(n_1) < g(n_1))$ {remove $n_2 = n_c, n = (n_1 | n\ge n_c$)}<br>
$\implies (f(n_g) < g(n_g) \implies f(n_g) < g(n_g))$ {remove $n_1 = (n_g | n_g\ge n_c)$}<br>
$\implies True$ {self-implication}<br>

Q.E.D.
