# The provers proof #

## Instead of introduction ##

To made up the actual data with the actual list of competitive provers I used the [CADE](http://www.cadeinc.org/)'s data in 2018.
The [CADE](http://www.cadeinc.org/) and [IJCAR](http://ijcar.org/) conferences are the major forums for the presentation of new research in all aspects of automated deduction.
In order to stimulate [ATP](https://en.wikipedia.org/wiki/Automated_theorem_proving) research and system development, and to expose [ATP](https://en.wikipedia.org/wiki/Automated_theorem_proving) systems within and beyond the ATP community,
the [CADE](http://www.cadeinc.org/) [ATP](https://en.wikipedia.org/wiki/Automated_theorem_proving) System Competition ([CASC](http://tptp.cs.miami.edu/~tptp/CASC/J9/)) is held at each [CADE](http://www.cadeinc.org/) and [IJCAR](http://ijcar.org/) conference. [CASC-J9](http://tptp.cs.miami.edu/~tptp/CASC/J9/) had been held on 14th July 2018,
during the 9th International Joint Conference on Automated Reasoning ([IJCAR](http://ijcar.org/), which incorporates [CADE](http://www.cadeinc.org/)).

CASC evaluates the performance of sound, fully automatic, ATP systems. The evaluation is in terms of:
* the number of problems solved,  
* the number of problems solved with a solution output, and  
* the average runtime for problems solved;

The first part contains overview and analysis, the second - the detailed results of the CASC_J9 with the detailed provers descriptions. At the end of this article the is a list of other provers.

## Introduction ##

Automated theorem proving (also known as ATP or automated deduction) is a subfield of automated reasoning and mathematical logic dealing with proving mathematical theorems by computer programs. 
Automated reasoning over mathematical proof was a major impetus for the development of computer science.

A simpler, but related, problem is proof verification, where an existing proof for a theorem is certified valid. For this, it is generally required that each individual proof step can be verified by a primitive recursive function or program, and hence the problem is always decidable.
Since the proofs generated by automated theorem provers are typically very large, the problem of proof compression is crucial and various techniques aiming at making the prover's output smaller, and consequently more easily understandable and checkable, have been developed.
Proof assistants require a human user to give hints to the system. Depending on the degree of automation, the prover can essentially be reduced to a proof checker, with the user providing the proof in a formal way, or significant proof tasks can be performed automatically. 
Interactive provers are used for a variety of tasks, but even fully automatic systems have proved a number of interesting and hard theorems, including at least one that has eluded human mathematicians for a long time, namely the Robbins conjecture.[7][8] 
However, these successes are sporadic, and work on hard problems usually requires a proficient user.

The quality of implemented systems has benefited from the existence of a large library of standard benchmark examples — the Thousands of Problems for Theorem Provers (TPTP) Problem Library[9] — as well as from the CADE ATP System Competition (CASC), 
a yearly competition of first-order systems for many important classes of first-order problems.

## Analysis ##

The results for the 2015 can be found [here](http://tptp.cs.miami.edu/CASC/25/WWWFiles/DivisionSummary1.html), for the 2018, [here](http://tptp.cs.miami.edu/~tptp/CASC/J9/WWWFiles/DivisionSummary1.html).

Mostly, the proves use tableu or resolution method with some modifications. An analytic tableau is a tree structure computed for a logical formula, having at each node a subformula of the original formula to be proved or refuted. 
Computation constructs this tree and uses it to prove or refute the whole formula[10]. Resolution is a rule of inference leading to a refutation theorem-proving technique for sentences in propositional logic and first-order logic.
In other words, iteratively applying the resolution rule in a suitable way allows for telling whether a propositional formula is satisfiable and for proving that a first-order formula is unsatisfiable[11].
The one has some new idea - it's MaLARea which tries to analyze symbols and calculate some (AI-like) statistics and use in the consequent processing.

In fact, there is no prover based on Maslov's inverse method.
To compare with the 2015 year's result see the table below


| Topic | Old Result | New Result | Old winner | New winner |
| --- | --- | --- | --- | --- |
| Higher-order Theorems | 271/400 (68%) | 406/500 (81%) | Satallax 2.8 | Satallax 3.2 |
| Typed First-order Theorems +*-/ | 172/200 (86%) | 163/200 (81%) | VampireZ3 1.0 | Vampire 4.3 |
| First-order Theorems | 380/400 (95%) | 461/500 (92%) | Vampire 4.0 | Vampire 4.3 |
| First-order Non-theorems | 195/200 (98%) | 191/200 (95%) | Vampire SAT‑4.0 | Vampire SAT‑4.3 |
| Effectively Propositional CNF | 192/200 (96%) | 133/150 (89%) | Vampire 4.0 | iProver 2.8 |
| Large Theory Batch Problems | 1208/1600 (76%) | 876/5000 (17%) | Vampire  4.0‑LTB | MaLARea 0.6 |

### [CASC‑J9](http://tptp.cs.miami.edu/~tptp/CASC/J9/) (2018) results ###

| Higher-order Theorems | Satallax 3.2 | Satallax 3.3 | Leo‑III 1.3 | LEO‑II 1.7.0 |
| --- | --- | --- | --- | --- |
| Solved/500 | 406/500 | 401/500 | 355/500 | 213/500 |
| Solutions | 406 81% | 401 80% | 355 71% | 209 41% |
| Typed First-order Theorems +*-/ | Vampire 4.3 | Vampire 4.1 | CVC4 1.6pre | Princess 170717 |
| Solved/200 | 163/200 | 162/200 | 157/200 | 105/200 |
| Solutions | 163 81% | 162 81% | 157 78% | 92 46% |

| First-order Theorems | Vampire 4.3 | Vampire 4.2 | CSE_E 1.0 | E 2.2pre | CVC4 1.6pre | Leo‑III 1.3 |
| --- | --- | --- | --- | --- | --- | --- |
| Solved/500 | 461/500 | 454/500 | 363/500 | 350/500 | 298/500 | 256/500 |
| Solutions | 461 92% | 454 90% | 362 72% | 350 70% | 298 59% | 256 51% |

| First-order Non-theorems | Vampire SAT‑4.3 | Vampire SAT‑4.1 | iProver SAT‑2.8 | CVC4 SAT‑1.6pre|
| --- | --- | --- | --- | --- |
| Solved/200 | 191/200 | 188/200 | 137/200 | 116/200 |
| Solutions | 191 95% | 186 93% | 137 68% | 116 58% |

| Effectively Propositional CNF | iProver 2.8 | Vampire 4.3 | iProver 2.6 | E 2.2pre | Leo‑III 1.3 |
| --- | --- | --- | --- | --- | --- |
| Solved/150 | 133/150 | 128/150 | 126/150 | 27/150 | 17/150 |

| Large Theory Batch Problems | MaLARea 0.6 | Vampire LTB‑4.0 | Vampire LTB‑4.3 | iProver LTB‑2.8 |
| --- | --- | --- | --- | --- |
| Solved/5000 | 876/5000 | 594/3553 | 757/5000 | 613/4999 |
| Solutions | 876 17% | 594 16% | 757 15% | 613 12% |

### CASC-J9 participants details ###

#### Hi order theorems [1] ####

The first place took Stallax 3.2 with 406/500 solved tasks. Satallax 3.2 is an automated theorem prover for higher-order logic. 
The particular form of higher-order logic supported by Satallax is Church's simple type theory with extensionality and choice operators.
The SAT solver MiniSat is responsible for much of the proof search. The theoretical basis of search is a complete ground tableau calculus for higher-order logic with a choice operator.
The second place took Stalax 3.3 with 401/500 solved tasks, where was added support for Mizar style soft types - typing mechanisms which concerned with providing a treatment of the concepts,
once the particular relations have been established in the underlying logic [2].

The second place took Leo-III with 355/500 solved tasks. Leo-III, the successor of LEO-II, 
is a higher-order ATP system based on extensional higher-order paramodulation with inference restrictions using a higher-order term ordering. 
The calculus is augmented with dedicated extensionality rules and equational simplification routines that have their intellectual roots in first-order superposition-based theorem proving.
Although Leo-III is originally designed as an agent-based reasoning system, its current version utilizes one sequential saturation algorithm only. 
The saturation algorithm itself is a variant of the given clause loop procedure. Leo-III heavily relies on cooperation with external (first-order) ATPs that are called asynchronously during proof search.
At the moment, first-order cooperation focuses on typed first-order (TFF) systems, where CVC4 and E are used as default external systems. Nevertheless, cooperation is not limited to first-order systems. 
Further TPTP/TSTP-compliant external systems (such as higher-order ATPs or counter model generators) may be included using simple command-line arguments.
If the saturation procedure loop (or one of the external provers) finds a proof, the system stops, generates the proof certificate and returns the result.

The third place took LEO-II with 213/500 solved tasks. LEO-II, the successor of LEO, is a higher-order ATP system based on extensional higher-order resolution.
More precisely, LEO-II employs a refinement of extensional higher-order RUE resolution. LEO-II is designed to cooperate with specialist systems for fragments of higher-order logic. 
By default, LEO-II cooperates with the first-order ATP system E. LEO-II is often too weak to find a refutation amongst the steadily growing set of clauses on its own.
However, some of the clauses in LEO-II's search space attain a special status: they are first-order clauses modulo the application of an appropriate transformation function. 
Therefore, LEO-II launches a cooperating first-order ATP system every n iterations of its (standard) resolution proof search loop (e.g., 10). 
If the first-order ATP system finds a refutation, it communicates its success to LEO-II in the standard SZS format.
Communication between LEO-II and the cooperating first-order ATP system uses the TPTP language and standards.

#### Typed First-order Theorems ####

The first place took Vampire 4.3 with 163/200 solved tasks. Vampire 4.3 is an automatic theorem prover for first-order logic.
Vampire implements the calculi of ordered binary resolution and superposition for handling equality.
It also implements the Inst-gen calculus and a MACE-style finite model builder.
Splitting in resolution-based proof search is controlled by the AVATAR architecture which uses a SAT or SMT solver to make splitting decisions.
Both resolution and instantiation based proof search make use of global subsumption.
A number of standard redundancy criteria and simplification techniques are used for pruning the search space: subsumption, tautology deletion,
subsumption resolution and rewriting by ordered unit equalities. The reduction ordering is the Knuth-Bendix Ordering.
Substitution tree and code tree indexes are used to implement all major operations on sets of terms, literals and clauses.
Internally, Vampire works only with clausal normal form. Problems in the full first-order logic syntax are classified during preprocessing.
Vampire implements many useful preprocessing transformations including the SinE axiom selection algorithm. When a theorem is proved, 
the system produces a verifiable proof, which validates both the classification phase and the refutation of the CNF.

The second place took Vampire 4.2 with 162/200 solved tasks. 
The difference between 4.3 and 4.2 versions is 4.3's specializing theory instantiation and unification.

The third place took CVC4 1.6 with 157/200 solved tasks. 
CVC4 is an SMT solver based on the DPLL(T) architecture that includes built-in support for many theories, 
including linear arithmetic, arrays, bit vectors, datatypes, finite sets and strings. 
It incorporates approaches for handling universally quantified formulas. For problems involving free function and predicate symbols,
CVC4 primarily uses heuristic approaches based on E-matching for theorems, and finite model finding approaches for non-theorems. 
For problems in pure arithmetic, CVC4 uses techniques for counterexample-guided quantifier instantiation. 
Like other SMT solvers, CVC4 treats quantified formulas using a two-tiered approach. 
First, quantified formulas are replaced by fresh Boolean predicates and the ground theory solver(s) are used in conjunction with the underlying SAT solver to determine satisfiability.
If the problem is unsatisfiable at the ground level, then the solver answers "unsatisfiable". Otherwise, the quantifier instantiation module is invoked, and will either add instances of quantified formulas to the problem, answer "satisfiable", or return unknown.
Finite model finding in CVC4 targets problems containing background theories whose quantification is limited to finite and uninterpreted sorts. 
In finite model finding mode, CVC4 uses a ground theory of finite cardinality constraints that minimizes the number of ground equivalence classes, as described in. 
When the problem is satisfiable at the ground level, a candidate model is constructed that contains complete interpretations for all predicate and function symbols.
It then adds instances of quantified formulas that are in conflict with the candidate model, as described in. If no instances are added, it reports "satisfiable".

Princess took forth place with 105/200 solved tasks. Princess is a theorem prover for first-order logic modulo linear integer arithmetic.
The prover uses a combination of techniques from the areas of first-order reasoning and SMT solving. The main underlying calculus is a free-variable tableau calculus, 
which is extended with constraints to enable backtracking-free proof expansion, and positive unit hyper-resolution for lightweight instantiation of quantified formulae. 
Linear integer arithmetic is handled using a set of built-in proof rules resembling the Omega test, which altogether yields a calculus that is complete for full Presburger arithmetic, for first-order logic, and for a number of further fragments. 
In addition, some built-in procedures for nonlinear integer arithmetic are available. The internal calculus of Princess only supports uninterpreted predicates; uninterpreted functions are encoded as predicates, together with the usual axioms.
Through appropriate translation of quantified formulae with functions, the e-matching technique common in SMT solvers can be simulated; triggers in quantified formulae are chosen based on heuristics similar to those in the Simplify prover.

#### First-order Theorems ####

The first two places taken by the Vampire 4.3 and 4.2 with 461/500 and 454/500 appropriately.

Third place took CSE E with 363/500 solved tasks. CSE_E 1.0 is an automated theorem prover for first-order logic by combining CSE 1.1 and E 2.1, 
where CSE is based on the Contradiction Separation Based Dynamic Multi-Clause Synergized Automated Deduction (S-CS) and E is based on superposition. 
The combination mechanism is like this: E and CSE are applied to the given problem sequentially. If either prover solves the problem, then the proof process completes.
If neither CSE nor E can solve the problem, some inferred clauses, especially unit clauses, by CSE will be fed to E as lemmas, along with the original clauses, for further proof search. 
This kind of combination is expected to take advantage of both CSE and E, and produce a better performance. Concretely, CSE is able to generate a good number of unit clauses, 
based on the fact that unit clauses are helpful for proof search and equality handling. On the other hand, E has a good ability on equality handling.

Forth position is E's with 350/500 solved tasks. E 2.1  is a purely equational theorem prover for many-sorted first-order logic with equality.
It consists of an (optional) classifier for pre-processing full first-order formulae into clausal form, and a saturation algorithm implementing an instance of the superposition calculus with negative literal selection and a number of redundancy elimination techniques.
E is based on the DISCOUNT-loop variant of the given-clause algorithm, i.e., a strict separation of active and passive facts. No special rules for non-equational literals have been implemented. Resolution is effectively simulated by paramodulation and equality resolution.
However, as of E 2.1, PicoSAT can be used to periodically check the (on-the-fly grounded) proof state for propositional not satisfiable.

For LTB division, a control program uses a SInE-like analysis to extract reduced axiomatizations that are handed to several instances of E. E will probably not use on-the-fly learning this year.
 
CVC 4 and Leo-III are on the 5th and 6th position with 298/500 and 256/500 solved tasks accordingly.

iProver on the 7th place and leanCoP 2.2 on the 8th with 248/500 and 143/500 solved tasks accordingly. 
leanCoP is an automated theorem prover for classical first-order logic with equality. 
It is a very compact implementation of the connection (tableau) calculus.

nanoCoP is the next with 133/500 solved tasks. nanoCoP is an automated theorem prover for classical first-order logic with equality. 
It is a very compact implementation of the non-clausal connection calculus.

CSE 1.1 and CSE 1.0 are the next ones with 126/500 and 123/500 solved tasks. 
The basic inference mechanism of CSE 1.1 is similar to CSE 1.0, i.e., it is an automated theorem prover for first-order logic without equality mainly based on a novel inference mechanism,
called as Contradiction Separation Based Dynamic Multi-Clause Synergized Automated Deduction (S-CS), which is able to handle multiple (two or more) clauses dynamically in a synergized way in one deduction step,
while binary resolution is its special case. The difference between CSE 1.0 and CSE 1.1 is that there are two S-CS deduction mechanisms in CSE 1.1, where one is called from left to right,
which refers the clauses that are not in the contradiction under construction, and another is named from right to left, which considers the clauses that are already in the contradiction under construction.
In addition, it supports the repeat usage of the same clause in one deduction step. These characteristics make the S-CS deduction be able to produce more unit clauses.

CSE 1.1 adopts conventional factoring, equality resolution, and variable renaming. 
Some pre-processing techniques, including pure literal deletion and simplification based on the distance to the goal clause, 
and a number of standard redundancy criteria for pruning the search space: tautology deletion, subsumption (forward and backward) are applied as well.

Internally, CSE 1.1 works only with clausal normal form. E prover is adopted with thanks for classification of full first-order logic problems during preprocessing.

Strategies CSE 1.1 inherited most of the clause/literal selection strategy selection, while the crucial difference comes from the multiple strategy mode and some heuristic strategies. 
The multiple strategy mode allows CSE 1.1 to solve the problem by trying different combination of strategies. 
Besides the strategies used in CSE 1.0, e.g., clause selection, literal selection, and weight strategy, there are some different strategies:

Deduction framework. This provides two overall options for S-CS deduction: integrity deduction mode, which takes all the clauses into consideration during deduction process, and contradiction separation clause deduction mode, which considers only a subset of clauses. 
Repeat usage of clause. This strategy provides two strategies: repeat usage of axiom and repeat usage of clause.

Contradiction separation clause strategy. Besides the CSC strategies in CSE 1.0, CSE 1.1 allows the usage of the medium CSCs during the contradiction construction process.

CSE 1.1 is implemented mainly in C++, and JAVA is used for batch problem running implementation. 
Shared data structure is used for constants and shared variables storage. In addition, special data structure is designed for property description of clause, 
literal and term, so that it can support the multiple strategy mode. E prover is used for classification of FOF problems, and then TPTP2X is applied to convert the CNF format into TPTP format.

The Prover9  is the second participant with the 122/500 solved tasks. Prover9, Version 2009-11A, is a resolution/paramodulation prover for first-order logic with equality. 
Its overall architecture is very similar to that of Otter-3.3. It uses the "given clause algorithm", in which not-yet-given clauses are available for rewriting and for other inference operations (sometimes called the "Otter loop").

Prover9 has available positive ordered (and nonordered) resolution and paramodulation, negative ordered (and nonordered) resolution, factoring, positive and negative hyperresolution, UR-resolution, and demodulation (term rewriting). 
Terms can be ordered with LPO, RPO, or KBO. Selection of the "given clause" is by an age-weight ratio. Proofs can be given at two levels of detail: (1) standard, in which each line of the proof is a stored clause with detailed justification, 
and (2) expanded, with a separate line for each operation. When FOF problems are input, proof of transformation to clauses is not given.

The next is Twee 2.2 with the 74/500 solved tasks. Twee 2.2 is an equational prover based on unfailing completion. It features ground joinability testing and a connectedness test, which together eliminate many redundant inferences in the presence of unorientable equations.

Twee's implementation of ground joinability testing performs case splits on the order of variables, in the style of, and discharges individual cases by rewriting modulo a variable ordering. 
It is able to pick only useful case splits and to case split on a subset of the variables, which makes it efficient enough to be switched on unconditionally.

Geo-III is the next with 50/500 solved tasks. Geo III is a theorem prover for Partial Classical Logic, based on reduction to Kleene Logic. Currently, only Chapters 4 and 5 are implemented. 
Since Kleene logic generalizes 2-valued logic, Geo III can take part in CASC. Apart from being 3-valued, the main differences with earlier versions of Geo are the following: 
The Geo family of provers uses exhaustive backtracking, in combination with learning after failure. Earlier versions (before 2016) learned only conflict formulas. Geo III learns disjunctions of arbitrary width.

#### First-order Non-theorems ####

The results distributed as: Vampire 4.3 with 191/200, Vampire 4.1 with 188/200, iProver 2.8 with 137/200, CVC4 with 116/200, E with 38/200, Geo-III with 38/200 solved tasks accordingly.

#### Effectively Propositional CNF [3] ####

The results distributed as: iProver 2.8 with 133/150, Vampire 4.3 with 128/150, iProver 2.6 with 126/150, E 2.2 with 27/150, Leo-III with 17/150, Geo-III with 10/150 solved tasks accordingly.

#### Large Theory Batch Problems [4] ####

The first place took MaLARea 0.6 with 876/5000 solved tasks. MaLARea 0.6 is a metasystem for ATP in large theories where symbol and formula names are used consistently. 
It uses several deductive systems (now E, SPASS, Vampire, Paradox, Mace), as well as complementary AI techniques like machine learning (the SNoW system) based on symbol-based similarity, 
model-based similarity, term-based similarity, and obviously previous successful proofs. The version for CASC-J9 will use the E prover with the BliStr(Tune)  large-theory strategies, possibly also Prover9, Mace and Paradox. 
The premise selection methods will likely also use the distance-weighted k-nearest neighbor and E's implementation of SInE.

The next are: Vampire 4.0 with 594/3553, Vampire 4.3 with 757/5000, iProver 2.8 with 613/4999, E 2.2 with 458/4999 accordingly.

Grakle 0.1 with 379/4893 solved tasks. Grackle is a bird species found in large numbers through much of North America. 
Different subspecies of the grackle family evolved a different bill length. This has the effect that different subspecies feed on different nutriment and do not compete with each other. 
This motivates the Grackle system. Grackle 0.1 is a generalization of BliStrTune, a system for invention of complementary E prover strategies, based on ParamILS system. 
BliStrTune was previously extended to invent Vampire strategies but this is not used here. Grackle is a next step in this direction of generalization, and it is able to develop complementary strategies of an arbitrary parametrized algorithm, not only E or Vampire. 
In CASC-J9, however, Grackle is used only to develop E strategies and the main difference from BliStrTune is a separate invention of SinE parameters for E prover.

## Provers summary with the references ##

| Name | Area | Method | Website |
| --- | --- | --- | --- |
| Stallax 3.2 | Hight order theorems (HOL high order logic) | Complete ground tableau calculus for higher-order logic | http://satallaxprover.org/ |
| Leo-III | Hight order theorems (HOL high order logic) | https://github.com/leoprover/Leo-III |
| LEO-II | Hight order theorems (HOL high order logic) | extensional higher-order resolution | www.leoprover.org / https://github.com/leoprover/LEO-II |
| Vampire | (Typed) First-order Theorems | implements the calculi of ordered binary resolution and superposition for handling equality	http://vprover.org/ |
| CVC4 | (Typed) First-order Theorems | based on E-matching [5] for theorems, and finite model finding approaches for non-theorems	https://github.com/CVC4 |
| Princess | (Typed) First-order Theorems | free-variable tableau calculus | http://www.philipp.ruemmer.org/princess.shtml |
| E	| First-order Theorems | resolution | https://wwwlehre.dhbw-stuttgart.de/~sschulz/E/E.html |
| leanCoP 2.2	| First-order Theorems | connection (tableau) calculus | http://www.leancop.de/ |
| nanoCoP | First-order Theorems | non-clausal connection calculus | http://www.leancop.de/nanocop/ |
| CSE | First-order Theorems | Custom binary resolution | |
| Prover9 | First-order Theorems | resolution/paramodulation prover for first-order logic with equality | https://www.cs.unm.edu/~mccune/prover9/ |
| Twee | First-order Theorems | resolution | http://nick8325.github.io/twee/ |
| Geo-III | First-order Theorems | reduction to Kleene Logic | https://cs-sst.github.io/faculty/nivelle/implementation/index |
| MaLARea | Large Theory Batch Problems | Mixed system complementary with AI techniques | https://github.com/JUrban/MPTP2 |
| Grakle | Large Theory Batch Problems | https://github.com/ai4reason/atpy |

#### Some additions provers [6] ####

| Name | Method | Website |
| --- | --- | --- |
| Gandalf | Maslov's inverse method | http://deepthought.ttu.ee/it/gandalf/ |
| JProver | non-clausal connection calculus | https://github.com/coqcontribs/jprover/, http://metaprl.org/install.html |
| ileanCoP | clausal connection calculus | http://www.leancop.de/ileancop/ |
| ileanTaP | Semantic tableau method | http://www.leancop.de/ileancop/ |
| ileanSeP | Analytical tableau method modification | http://www.leancop.de/ileancop/ |
| Imogen | Maslov's inverse method | https://github.com/seanmcl/imogen |
| nanoCoP-i | non-clausal connection calculus | http://www.leancop.de/nanocop-i/index.html |

## References ##

* [1] Hi order automated theorem prover [http://page.mi.fu-berlin.de/cbenzmueller/papers/B14.pdf](http://page.mi.fu-berlin.de/cbenzmueller/papers/B14.pdf)
* [2] A Guide to the Mizar Soft Type System [https://pdfs.semanticscholar.org/82f2/dfa4437b79a35aaf72ce71e85a919103b88f.pdf](https://pdfs.semanticscholar.org/82f2/dfa4437b79a35aaf72ce71e85a919103b88f.pdf)
* [3] Conjunctive normal form [https://en.wikipedia.org/wiki/Conjunctive_normal_form](https://en.wikipedia.org/wiki/Conjunctive_normal_form)
* [4] Automated Reasoning and Mathematics: Essays in Memory of William W. McCune, page 250 [https://books.google.ru/books](https://books.google.ru/books?id=Ywa7BQAAQBAJ&pg=PA250&lpg=PA250&dq=Large+Theory+Batch+Problems&source=bl&ots=OoiDUuQQ2e&sig=p6IvNymJr_MyY5iXpAtY2k9NmWk&hl=ru&sa=X&ved=2ahUKEwjNlMOC19XdAhWDWSwKHUfoAOUQ6AEwBHoECAYQAQ#v=onepage&q=Large%20Theory%20Batch%20Problems&f=false)
* [5] E-Matching with Free Variables [https://pdfs.semanticscholar.org/d88d/8cf28494ce101e0b69113f63febee62ce64a.pdf](https://pdfs.semanticscholar.org/d88d/8cf28494ce101e0b69113f63febee62ce64a.pdf)
* [6] [https://disser.spbu.ru/files/disser2/disser/LKfkdgQnht.pdf](https://disser.spbu.ru/files/disser2/disser/LKfkdgQnht.pdf) page 27
* [7] W.W. McCune (1997). "Solution of the Robbins Problem". Journal of Automated Reasoning. 19 (3). [http://www.springerlink.com/content/h77246751668616h/](http://www.springerlink.com/content/h77246751668616h/)
* [8] Gina Kolata (December 10, 1996). "Computer Math Proof Shows Reasoning Power". The New York Times. Retrieved 2008-10-11. [https://www.nytimes.com/library/cyber/week/1210math.html](https://www.nytimes.com/library/cyber/week/1210math.html)
* [9] Sutcliffe, Geoff. "The TPTP Problem Library for Automated Theorem Proving". Retrieved 8 September 2012. [http://www.cs.miami.edu/~tptp/](http://www.cs.miami.edu/~tptp/)
* [10] Method of analytic tableaux [https://en.wikipedia.org/wiki/Method_of_analytic_tableaux](https://en.wikipedia.org/wiki/Method_of_analytic_tableaux)
* [11] Resolution (logic) [https://en.wikipedia.org/wiki/Resolution_(logic)](https://en.wikipedia.org/wiki/Resolution_(logic))
* [http://www.cadeinc.org/](http://www.cadeinc.org/)
* [http://ijcar.org/](http://ijcar.org/)
* [https://en.wikipedia.org/wiki/Automated_theorem_proving](https://en.wikipedia.org/wiki/Automated_theorem_proving)

### Links ###

* [CSE 1.0](http://www.tptp.org/CASC/J9/SystemDescriptions.html#CSE---1.0)
* [CSE 1.1](http://www.tptp.org/CASC/J9/SystemDescriptions.html#CSE---1.1)
* [CSE_E 1.0](http://www.tptp.org/CASC/J9/SystemDescriptions.html#CSE_E---1.0)
* [CVC4 1.6pre](http://www.tptp.org/CASC/J9/SystemDescriptions.html#CVC4---1.6pre)
* [E 2.2pre](http://www.tptp.org/CASC/J9/SystemDescriptions.html#E---2.2pre)
* [Geo-III 2018C](http://www.tptp.org/CASC/J9/SystemDescriptions.html#Geo-III---2018C)
* [Grackle 0.1](http://www.tptp.org/CASC/J9/SystemDescriptions.html#Grackle---0.1)
* [iProver 2.6](http://www.tptp.org/CASC/J9/SystemDescriptions.html#iProver---2.6)
* [iProver 2.8](http://www.tptp.org/CASC/J9/SystemDescriptions.html#iProver---2.8)
* [leanCoP 2.2](http://www.tptp.org/CASC/J9/SystemDescriptions.html#leanCoP---2.2)
* [LEO-II 1.7.0](http://www.tptp.org/CASC/J9/SystemDescriptions.html#LEO-II---1.7.0)
* [Leo-III 1.3](http://www.tptp.org/CASC/J9/SystemDescriptions.html#Leo-III---1.3)
* [MaLARea 0.6](http://www.tptp.org/CASC/J9/SystemDescriptions.html#MaLARea---0.6)
* [nanoCoP 1.1](http://www.tptp.org/CASC/J9/SystemDescriptions.html#nanoCoP---1.1)
* [Princess 170717](http://www.tptp.org/CASC/J9/SystemDescriptions.html#Princess---170717)
* [Prover9 1109a](http://www.tptp.org/CASC/J9/SystemDescriptions.html#Prover9---1109a)
* [Satallax 3.2](http://www.tptp.org/CASC/J9/SystemDescriptions.html#Satallax---3.2)
* [Satallax 3.3](http://www.tptp.org/CASC/J9/SystemDescriptions.html#Satallax---3.3)
* [Twee 2.2](http://www.tptp.org/CASC/J9/SystemDescriptions.html#Twee---2.2)
* [Vampire 4.0](http://www.tptp.org/CASC/J9/SystemDescriptions.html#Vampire---4.0)
* [Vampire 4.1](http://www.tptp.org/CASC/J9/SystemDescriptions.html#Vampire---4.1)
* [Vampire 4.2](http://www.tptp.org/CASC/J9/SystemDescriptions.html#Vampire---4.2)
* [Vampire 4.3](http://www.tptp.org/CASC/J9/SystemDescriptions.html#Vampire---4.3)