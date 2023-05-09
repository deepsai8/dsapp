# Probability Theory

Here you'll learn all about Probability Theory in a practical manner

## Aximoatic Theory

### Definitions

#### Random Experiment
* It's a process or an outcome that is not deterministic, i.e. it is stoichastic
* e.g. $f(x) = x^{2}$ <br>
    - or fixed input => fixed output, meaning deterministic
* e.g. 
    - Roll a die (6 possibilities)
    - dealing a deck of cards (52! permutations)

#### Sample Space
* A set of all possible outcomes of a random experiment, typically denoted by S or $\Omega$

#### Elements or Outcomes (or Atoms or Singletons)
* These are the outcomes. Usually denoted by small 's' or $\omega$
* e.g. Flip a coin 3 times (order matters), will have these outcomes or elements:
    - HHH, HHT, HTH, HHT, THH, HTT, THT, TTH, TTT
* and set1 = {HHH, HHT, HTH} or set2 = {THH, TTH, TTT} or set3 = {TTT} are the events
* Above entire set of possible outcomes is called a Descrete Random Experiment

#### Event
* Typically denoted by capital letters A, B etc.
* It is sort of a subset of S, that can be passed on to a probability measure
* All set operations can be used to build events

#### Probability Measure
* A notation such as P(A) = P(X>5) is called a probability measure if it satisfies the 3 Axioms of Kolmogorov


### Kolmogorov Axioms
The Kolmogorov axioms are the foundations of probability theory introduced by Russian mathematician Andrey Kolmogorov in 1933 [^1]. These axioms remain central and have direct contributions to mathematics, the physical sciences, and real-world probability cases. An alternative approach to formalising probability, favoured by some Bayesians, is given by Cox's theorem

* Framework: 
    - let S be a sample space for some Random Experiment
    - let P be a function from P : P(S) -> R
    - here, P(S) = Power set = {set of all subsets of S}
    - we say that P is a probabilty measure ans (S, P) is a probabilty space, if the following 3 axioms are satisfied:

#### Axioms
* $P(A)\geq0$, for any event $A \subset S$
    - aka Non-Negativity
* P(S) = 1
    - aka Unity
* If $A_1, A_2, ... $ is a sequence of Mutually Exclusive events, then
$P\left(\bigcup _{i=1}^{\infty }E_{i}\right)=\sum _{i=1}^{\infty }P(E_{i})$

[^1]: [Foundations of the theory of probability](https://archive.org/details/foundationsofthe00kolm/page/n7/mode/2up)

