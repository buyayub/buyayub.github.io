---
title: A Note on the Entscheidungsproblem by Alonzo Church
author: Alonzo Church
excerpt: Digitization of Alonzo Church's A Note on the Entscheidungsproblem. 
katex: true
---

<details markdown="block" class="pn_note">
<summary markdown="span"> Preliminaries</summary>

MathML doesn't work on chromium-based browsers, so you won't see the proper markup unless you have an extension installed, switch to firefox/safari, or wait [until 109 is released (should be in Dec 2022)](https://chromestatus.com/feature/5240822173794304). 

If you notice any typos or anything like that, send me an email. I'd appreciate it.

</details>

In a recent paper[^1] the author has proposed a definition of the commonly used term "effectively calculable" and has shown on the basis of this definition that the general case of the Entscheidungsproblem is unsolvable in any system of symbolic logic which is adequate to a certain portion of arithmetic and is $$\omega$$-consistent. The purpose of the present note is to outline an extension of this result to the engere Funktionenkalkül of Hilbert and Ackermann.[^2]

In the author's cited paper it is pointed out that there can be associated recursively with every well-formed formula[^3] a recursive enumeration of the formulas into which it is convertible.[^3] This means the existence of a recursively defined function $$a$$ of two positive integers such that, if $$y$$ is the Gödel representation of a well-formed fomula $$Y$$ then $$a(x, y)$$ is the Gödel representation of the $$x$$th formula in the enumeration of the formulas into which $$Y$$ is convertible.

Consider the system L of symbolic logic which arises from the engere Fucktionenkalkül by adding to it: as additional undefined symbols, a symbol $$1$$ for the number $$1$$ (regarded as an individual), a symbol $$=$$ for the propositional function $$=$$ (equality of indivduals), a symbol $$=$$ for the propositional function $$=$$ (equality of individuals), a symbol $$s$$ for the arithmetic function $$x + 1$$, a symbol $$a$$ for the arithmetic function $$a$$ described in the preceding paragraph, and symbols $$b_1,b_2,b_3,\cdots,b_k$$ for the auxiliary arithmetic functions which are employed in the recursive definition of $$a$$; and as additional axioms, the recursion equations for the functions $$a, b_1, b_2, \cdots , b_k$$ (expressed with free individual variables, the class of individuals being taken as identical with the class of positive integers), and two axioms of equality, $$x=x$$, and $$x=y \rightarrow [F(x) \rightarrow F(y)]$$.

The consistency of the system L follows by the methods of existing proofs.[^4] The $$\omega$$-consistency of $$\text{L}$$ is a matter of more difficulty, but for our present purpose the following weaker property of $$\text{L}$$ is sufficient: if $$\text{P}$$ contains no quantifiers and ($$Ex$$)$$\text{P}$$ is provable in L then not all of $$\overline{\text{P}}_1, \overline{\text{P}}_2, \overline{\text{P}}_3, \cdots $$ are provable in L (where $$\text{P}_1, \text{P}_2, \text{P}_3, \cdots $$ are respectively the results of substituting $$\text{1, 2, 3, }\cdots$$ for $$x$$ throughout $$\textrm{P}$$). This property has been proved by Paul Bernays[^5] for any one of a class of systems of which $$\text{L}$$ is one. Hence, by the argument of the author's cited paper, follows:

*The general case of the Entscheidungsproblem[^6] of the system $$\text{L}$$ is unsolvable.*

Now by a device which is well known, it is possible to replace the system $$\text{L}$$ by an equivalent system $$\text{L}'$$ which contains no symbols for arithmetic functions. This is done by replacing $$s, a, b_1, b_2, \cdots , b_k$$ by the symbols $$S, A, B_1, B_2, \cdots , B_k$$ for the propositional functions $$x=s(y), x=a(y,z),$$ etc., and making corresponding alterations in the formal axioms of $$\text{L}$$.

The system $$\text{L}'$$ differs from the engere Funktionenkalkül by the additional undefined terms $$1, =, S, A, B_1, B_2, \cdots , B_k$$ and a number of formal expressions introduced as additional axioms. Let $$\text{T}$$ be the logical product of these additional axioms, let $$z$$ be an individual variable which does not occur in any of the formal axioms of $$\text{L}'$$, and let $$G_1, G_2, \cdots, G_{k+3}$$ for the symbols, $$1, =, S, A, B_1, B_2, \cdots, B_k$$ respectively.

Let $$\text{Q}$$ be a formal expression in the notation of $$\text{L}'$$. We may suppose without loss of generality that $$\text{Q}$$ contains none of the variables $$z, G_1, G_2, \cdots , G_{k+3}$$. Let $$\text{R}$$ be the result of substituting throughout $$\text{Q}$$ the symbols $$z, G_1, G_2, \cdots, G_{k+3}$$ for the symbols $$1, =, S, A, B_1, B_2, \cdots , B_k$$ respectively. Then $$\text{Q}$$ is provable in $$\text{L}'$$ if and only if $$\text{U} \rightarrow \text{R}$$ is provable in the engere Funktionenkalkül.

Thus a solution of the general case of the Entscheidungsproblem of the engere Funktionenkalkül would lead to a solution of the general case of the Entscheidungsproblem of $$\text{L}'$$ and hence of $$\text{L}$$. Therefore:
	
*The general case of the Entscheidungsproblem of the engere Funktionenkalkül is unsolvable.*[^7]

---

[^1]: [An unsolvable problem of elementary number theory, American journal of mathematics, vol.58 (1936).](https://philpapers.org/rec/CHUAUP)

[^2]: [Grundziige der theoretischen Logik, Berlin 1928](https://link.springer.com/book/10.1007/978-3-662-41928-1)
	
	[translation](https://books.google.ca/books/about/Principles_of_Mathematical_Logic.html?id=45ZGMjV9vfcC&redir_esc=y)

[^3]: Definitions of the terms well-formed jormula and convertible are given in the cited paper.

[^4]:  Cf. Wilhelm Ackermann, Begrüdung des "tertium non datur" mittels der Hilbertschen Theorie der Widerspruchsfreiheit, Mathematische Annalen, vol. 93 (1924-5), pp. 1-136; 
	J. v. Neumann, Zur Hilbertschen Beweishtheorie, Mathematische Zeitschrift, vol. 26 (1927), pp. 1-46; 
	Jacques Herbrand, Sur la non-contradiction de'arithmetique, Journal für die reine und angewandte Mathematik, vol. 166 (1931-2), pp. 1-8.

[^5]: In lectures at Princeton, N. J., 1936. The methods are those of existing consistency proofs.

[^6]: By the Entscheidungsproblem of a system of symbolic logic is here understood the problem to find an effective method by which, given any expression Q in the notation of the system, it can be determined whether or not Q is provable in the system. Hilbert and Ackermann (loc. cit.) understand the Entscheidungsproblem of the engere Funktionenkalkül in a slightly different sense. But the two senses are equivalent in view of the proof by Kurt Gödel of the completeness of the engere Funktionenkalkül (Monatshefte für Mathematik und Physik, vol. 37 (1930), pp. 349-360).

[^7]: From this follows the further unsolvability of the particular case of the Enscheidungsproblem of the engere Functionenkalkül which concerns the provability of expressions of the form $$(Ex_1)(Ex_2)(Ex_3)(y_1)(y_2) \cdots (y_n) \text{P}$$ where $$\text{P}$$ contains no quantifiers and no individual variables except $$x_1, x_2, x_3, y_1, y_2, \cdots , y_n$$. Cf. Kurt Gödel, Zum Entscheidungsproblem des logischen Fuktionenkalküls, Monatshefte für Mathematik und Physik, vol 40 (1933), pp. 443-443.
