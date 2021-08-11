---
layout: article
title: First Post
date: 2021-08-16 12:00:00 -0400
mathjax: true
---
# Olym 1A. Equations and Formulae

<a href="https://ramaniumx.github.io/phantom-jekyll-theme/">Olymplex</a> > <a href="https://ramaniumx.github.io/phantom-jekyll-theme/mathematical-olympiads/">Mathematical Olympiads</a> > <a href="https://ramaniumx.github.io/phantom-jekyll-theme/mathematical-olympiads/algebra/">Algebra</a> > <a href="https://ramaniumx.github.io/phantom-jekyll-theme/mathematical-olympiads/algebra/olym-1a/">Olym 1A</a> > <a href="https://ramaniumx.github.io/phantom-jekyll-theme/mathematical-olympiads/algebra/olym-1a/practice-problems/">Practice Problems</a>

The 62nd International Mathematical Olympiad (namely the IMO) was held remotely on July 21-22, 2021. As a former IMO participant, I thought it would be fun (and somehow educational) to have former Korean IMO participants attempting this year's IMO problems and livestream it, and we [did that at Twitch][twitch-link] (unfortunately we didn't record it, but you can look at some clips!).

Our livestreaming team consisted of six people who participated in one (or two) of IMO 2018, 2019, and 2020. Here, I am going to share the solutions that we came up with, along with some additional notes on each problem.

## Problem 1. Easy cards

<bluebox>Let $n \geqslant 100$ be an integer. Ivan writes the numbers $n, n+1, \ldots, 2n$ each on different cards. He then shuffles these $n+1$ cards, and divides them into two piles. Prove that at least one of the piles contains two cards such that the sum of their numbers is a perfect square. </bluebox>

_Proof._ It suffices to prove that there are three integers $n \le a<b<c \le 2n$ such that $a+b, b+c, c+a$ are perfect squares.

To accomplish this, we will set $a = 2i^2 - 4i, b= 2i^2+1, c= 2i^2+4i$ for some integer $i$. Then it follows that $a+b = (2i-1)^2, a+c=(2i)^2, b+c=(2i+1)^2,$ so we only need

\[ 2i^2-4i \ge n ,2i^2+4i \le 2n \iff (i-1)^2 \ge \frac{n}{2}+1 , (i+1)^2 \le n+1 \]

for some integer $i$. This is equivalent to $\lfloor \sqrt{n+1} \rfloor - \lceil \sqrt{\frac{n}{2}+1} \rceil \ge 2$, which can be verified easily.

## Problem 2. New n-var ineq

<bluebox> Show that the inequality
$$ \sum_{i=1}^{n} \sum_{j=1}^{n} \sqrt{ \lvert x_i - x_j \rvert} \le \sum_{i=1}^{n} \sum_{j=1}^{n} \sqrt{\lvert x_i + x_j \rvert} $$
holds for all reals $x_1, x_2, \cdots, x_n.$ </bluebox>

_Proof._ We will prove the problem with strong induction on $n$. The base cases in which $n \le 2$ are trivial.

<greenbox> **Lemma.** For any real $x \neq 0$ and $0 < \epsilon < 2\|x\|,$ we have
$$ \sqrt{\lvert x-\epsilon/2 \rvert}+\sqrt{\lvert x+\epsilon/2 \rvert} < 2\sqrt{\lvert x \rvert}. $$ </greenbox>

_Proof._ This directly follows from Jensen as both $\sqrt{x}$ and $\sqrt{-x}$ are concave on their domains. $\square$

Note that the left-hand side remains constant under translation of the variables ($x_j \leftarrow x_j + \frac{C}{2}$), so it is sufficient to consider the case where the right-hand side is minimized under translation.
Accordingly, let $f(C):= \sum_{i, j} \sqrt{|x_i + x_j + C|}.$ Then $f(C)$ is continuous on $\mathbb{R}$ and bounded below; thus $f$ attains a minimum.
Let $f(C)$ be that minimum, and suppose $x_i+x_j+C \neq 0$ for every indices $1 \le i, j \le n.$

By the lemma, for all sufficiently small $\epsilon$ we have

$ \sum_{i, j} \sqrt{\lvert x_i + x_j + C + \epsilon \rvert} + \sum_{i, j} \sqrt{\lvert x_i + x_j + C - \epsilon \rvert} < \sum_{i, j} 2\sqrt{\lvert x_i+x_j+C \rvert}, $

so $\min \\{f(C-\epsilon), f(C+\epsilon)\\} < f(C).$ This contradicts the minimality of $f(C).$ Hence there are indices $i, j$ such that $x_i+x_j+C=0.$

Now by the translation $x_j \leftarrow x_j + \frac{C}{2}$ we have $x_i+x_j=0$ for some $i, j.$ WLOG assume $i=j=n$ or $i=n-1, j=n,$ then the inequality reduces to the following two inequalities, which holds by the induction hypothesis.

\[ \sum\_{i=1}^{n-1} \sum\_{j=1}^{n-1} \sqrt{ \lvert x_i - x_j \rvert} \le \sum\_{i=1}^{n-1} \sum\_{j=1}^{n-1} \sqrt{\lvert x_i + x_j \rvert} \]

\[ \sum\_{i=1}^{n-2} \sum\_{j=1}^{n-2} \sqrt{ \lvert x_i - x_j \rvert} \le \sum\_{i=1}^{n-2} \sum\_{j=1}^{n-2} \sqrt{\lvert x_i + x_j \rvert} \]

Note that equality holds iff the $x_i$s are symmetric with respect to the origin, i.e. the multiset $\\{x_1, x_2, \cdots, x_n \\}$ can be partitioned into groups of size at most two so that each group has sum $0.$

## Problem 3. Classical Triangle Geo

<bluebox> Let $D$ be an interior point of the acute triangle $ABC$ with $AB > AC$ so that $\angle DAB = \angle CAD.$ The point $E$ on the segment $AC$ satisfies $\angle ADE =\angle BCD,$ the point $F$ on the segment $AB$ satisfies $\angle FDA =\angle DBC,$ and the point $X$ on the line $AC$ satisfies $BX = CX.$ Let $O_1$ and $O_2$ be the circumcenters of the triangles $ADC$ and $EXD,$ respectively. Prove that the lines $BC, EF,$ and $O_1O_2$ are concurrent. </bluebox>

_Proof._

<p align="center">
    <img width="700" src="/assets/images/posts/imo3fig.jpg">
</p>

_Step 1._ Let $D'$ denote the isogonal conjugate of $D$ with respect to $\triangle ABC.$ Then the given angle condition implies

\[ \angle FDB' = \angle DBC = \angle FDD', \]

so $(BFDD'),(DD'CE)$ are cyclic. Hence by PoP,

\[ AF\times AB= AD\times AD'= AE\times AC, \]

we obtain that $(BCEF)$ is also cyclic.

Now we recall a well-known lemma used in several IMO/ISLs:

<greenbox> **Lemma.** Let $ABCD$ be a quadrilateral and $X$ be a point in its interior so that $\angle AXB+\angle CXD = \pi$. Then $X$ has an isogonal conjugate with respect to $ABCD$. </greenbox>

_Step 2._ By the above lemma, it follows that $D$ and $D'$ are isogonal conjugates with respect to $\square BCEF$. Hence

\[ \angle BDF = \angle BD'F = \pi - \angle CD'E = \angle D'EC + \angle D'CD = \angle DEF + \angle DBC, \]

which implies that $\odot(DEF)$ and $\odot(DBC)$ are tangent to each other. By the radical axis theorem on $\odot(AEF), \odot(DEF), \odot(DBC)$, the point $T := BC \cap EF$ satisfies $TD^2 = TB \times TC$.

_Step 3._ Let $P$ be the intersection of $\odot(AEF)$ and $\odot(ABC)$. Then $\triangle PBC \sim \triangle PFE$ by the Miquel point property, and

\[ \angle PBX=\angle XBC -\angle PBC=\angle ACB -\angle PFE = \angle AFE- \angle PFE =\angle AFP =\angle XEP. \]

Hence $(XPEB)$ are cyclic.

_Step 4._ Let $PB$ and $AC$ intersect at $I$ and let $\odot(XDE)$ and $\odot(ADC)$ meet again at $G$. Then by PoP

\[ XI\times IE=PI\times IB =AI\times IC, \]

so $I$ lies on the radical axis of $\odot(XDE)$ and $\odot(ADC)$ which is $DG.$ Hence by PoP again, we have

\[ BI\times IP=AI\times IC =DI\times IG \]

so $(BDPG)$ are cyclic.

_Step 5._
To finish, consider the inversion centered at $T$ with radius $TD$. By _Step 2_ we have $TD^2 =TB\times TC=TP\times TA$, and thus $G = \odot(ADC) \cap \odot(BDP)$ is fixed under this inversion (as the two circles swap to each other). Hence $TG=TD$, and $T$ lies on the perpendicular bisector of $DG$, which is $O_1 O_2.$ This concludes the proof.

## Problem 4. Cute length chasing

<bluebox>Let $\Gamma$ be a circle with centre $I$, and $A B C D$ a convex quadrilateral such that each of the segments $A B, B C, C D$ and $D A$ is tangent to $\Gamma$. Let $\Omega$ be the circumcircle of the triangle $AIC$. The extension of $BA$ beyond $A$ meets $\Omega$ at $X$, and the extension of $B C$ beyond $C$ meets $\Omega$ at $Z.$ The extensions of $A D$ and $C D$ beyond $D$ meet $\Omega$ at $Y$ and $T$, respectively. Prove that
\[A D+D T+T X+X A=C D+D Y+Y Z+ZC.\]
</bluebox>

_Proof._ The following claim kills the problem: Let $\gamma$ be a circle and $X, Y$ be two points outside the circle so that the angle between the two tangent lines from $X$ to $\gamma$ and $Y$ to $\gamma$ is the same. Then the distance of the $X$ and the tangency point is same as that of $Y$.

For the main problem, observe that $\overline{XT}=\overline{YZ}$ as $\triangle IXT \equiv \triangle IYZ$, and $\angle ITC = \angle IZC$ implies that the length of the tangent from $T$ and $Z$ to the incircle are the same. Applying the same fact to $X$ and $Y$ will imply the desired result.

## Problem 5. Walnuts

<bluebox>Two squirrels, Bushy and Jumpy, have collected 2021 walnuts for the winter. Jumpy numbers the walnuts from 1 through 2021, and digs 2021 little holes in a circular pattern in the ground around their favourite tree. The next morning Jumpy notices that Bushy had placed one walnut into each hole, but had paid no attention to the numbering. Unhappy, Jumpy decides to reorder the walnuts by performing a sequence of 2021 moves. In the $k$-th move, Jumpy swaps the positions of the two walnuts adjacent to walnut $k$.\
Prove that there exists a value of $k$ such that, on the $k$-th move, Jumpy swaps some walnuts $a$ and $b$ such that $a<k<b.$ </bluebox>

_Proof._ Suppose otherwise. Suppose initially all walnuts are white and we are coloring the walnut $k$ black on the $k$-th move. Then on the $k$-th move the two numbers adjacent to $k$ must have the same color. Hence the number of adjacent (black, black) pairs does not change upon $\pmod 2,$ but it should change from $0$ to $2021,$ contradiction.

## Problem 6. Sets, Sums, Integers

<bluebox>Let $m \ge 2$ be an integer, $A$ a finite set of integers (not necessarily positive) and $B_1,B_2,...,B_m$ subsets of $A$. Suppose that, for every $k=1,2,...,m$, the sum of the elements of $B_k$ is $m^k$. Prove that $A$ contains at least $m/2$ elements.</bluebox>

_Proof._ Let $A=\\{a_1, a_2, \cdots, a_k \\},$ and consider the following two sets:

- $X = \\{ \lambda_1a_1+\lambda_2a_2+\cdots+\lambda_ka_k : 0 \le \lambda_i \le m^2-1 \\},$

- $Y = \\{ \lambda_1m^1+\lambda_2m^2+\cdots+\lambda_mm^m : 0 \le \lambda_i \le m-1 \\}.$

The key observation is the following:

_Claim._ We have $Y \subseteq X$.

_Proof._ Write each $m^j$ as a sum of suitable $a_i$s. Then it follows that every element of $Y$ can be expressed as a (integer-coefficient) linear combination of $a_1, \cdots, a_k$, and that these coefficients are at least $0$ and at most $(m-1) \times m <m^2-1$. Hence every element of $Y$ should be in $X$ as well, implying $Y \subseteq X$. $\square$

Now note that $Y = \\{ 0, m, 2m, \cdots, m^{m+1}-m \\}$ by base $m$ representation, and $\lvert X \rvert \le (m^2)^k.$ Comparing, we have

\[ (m^2)^k \ge \lvert X \rvert \ge \lvert Y \rvert = m^m, \]

and it follows that $k \ge \frac{m}{2}$.

---

[twitch-link]: https://www.twitch.tv/lminsl_solves_imo
