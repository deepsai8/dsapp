# Probability Theory

## A little bit of History
The modern mathematical theory of probability has its roots in attempts to analyze games of chance by Gerolamo Cardano in the sixteenth century, and by Pierre de Fermat and Blaise Pascal in the seventeenth century (for example the "problem of points"). Christiaan Huygens published a book on the subject in 1657. In the 19th century, what is considered the classical definition of probability was completed by Pierre Laplace [^1]

## Probability
In science, the probability of an event is a number that indicates how likely the event is to occur. It is expressed as a number in the range from 0 and 1, or, using percentage notation, in the range from 0% to 100%. The more likely it is that the event will occur, the higher its probability.

## Aximoatic Theory

### Definitions

#### Deterministic System
In mathematics, computer science and physics, a deterministic system is a system in which no randomness is involved in the development of future states of the system. A deterministic model will thus always produce the same output from a given starting condition or initial state.[^1a]

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
The Kolmogorov axioms are the foundations of probability theory introduced by Russian mathematician Andrey Kolmogorov in 1933 [^2]. These axioms remain central and have direct contributions to mathematics, the physical sciences, and real-world probability cases. An alternative approach to formalising probability, favoured by some Bayesians, is given by Cox's theorem

* Framework: 
    - let S be a sample space for some Random Experiment
    - let P be a function from P : P(S) -> R
    - here, P(S) = Power set = {set of all subsets of S}
    - we say that P is a probabilty measure ans (S, P) is a probabilty space, if the following 3 axioms are satisfied:

#### Axioms
* $P(A)\geq0$, for any event $A \subseteq S$
    - aka Non-Negativity
* P(S) = 1
    - aka Unitarity or Unity
* If $A_{1}, A_{2}, ...$ is a sequence of Mutually Exclusive events, then
$P\left(\bigcup _{i=1}^{\infty }A_{i}\right)=\sum _{i=1}^{\infty }P(A_{i})$
    - aka $\sigma$-Additivity


[^1]: <a target="_blank" rel="noopener noreferrer" href = "https://dx.doi.org/10.1016/0315-0860%2880%2990025-7">Probabilistic Expectation</a>
[^1a]: <a target="_blank" rel="noopener noreferrer" href = "https://en.wikipedia.org/wiki/Deterministic_system">Deterministic System wikipedia</a>
[^2]: <a target="_blank" rel="noopener noreferrer" href = "https://archive.org/details/foundationsofthe00kolm/page/n7/mode/2up">Foundations of the theory of probability</a>
[^3]: <a target="_blank" rel="noopener noreferrer" href = "https://commons.wikimedia.org/wiki/File:Dice_Distribution_(bar).svg">By Tim Stellmach - Own work using Inkscape and Open Office Draw software., Public Domain, https://commons.wikimedia.org/w/index.php?curid=1220091</a>

