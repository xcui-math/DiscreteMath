## Lecture Information & Schedule

### Lecture 1: Introduction

#### March 5, 2018

This is an introductory lecture aiming on explaning what is Discrete Mathematics, what kind of problems we will encounter and what is the strategy to solve them. Example problems： stable marriage problem and the deferred acceptance algorithm, which is related to the 2012 Nobel Prize in Economics, the [Sierpiński curve](https://en.wikipedia.org/wiki/Sierpi%C5%84ski_curve), the [seven bridges of Königsberg](https://en.wikipedia.org/wiki/Seven_Bridges_of_K%C3%B6nigsberg), and [Kirkman's schoolgirl problem](https://en.wikipedia.org/wiki/Kirkman%27s_schoolgirl_problem). Course syllabus and how to excel in it.

Further recommended reading: 
+ David Austin, [The stable marriage problem and school choice](http://www.ams.org/publicoutreach/feature-column/fc-2015-03). The article is in English and pretty long, but please do not be terrified. I hope that you can enjoy the process of trying to read (even small parts) of it!
+ 如果你喜欢玩旅行青蛙（旅かえる），不妨读一下这篇[技术分析](https://www.zhihu.com/question/68733553/answer/305463907)。以后我们会学到图论和相关算法。

### Lecture 2, 3, 4: Sets, Logic and Boolean Algebras

Lecture notes can be found [here](/Lecture_Notes.pdf): last updated: Mar 16, 2018. 

#### March 9, 2018

An introductory lecture about set theory and propositional logic (unfinished). We started from the relevant definition about sets, various m-nary operations and results about commutativity, associativity and distributivity. The motivation of propositional logic, various m-nary operations on it, and the truth table.

Recommended exercise:
+ Finish the exercises given during the lecture.
+ 阅读教材的相关内容————对同样的内容通过不同的方式（听课，阅读不同版本的文献，查询[Wikipedia](https://en.wikipedia.org/)等等）进行学习可以加深理解，巩固基础。
#### March 12, 2018

Implication and bicondition; statements viewed as "constant" operations and the tree graph to denote compound operations. Boolean algebras, revisiting the example from set theory and propositional logic, and its theoretical importance. Then we moved to the introduction of predicate logic.

#### March 16, 2018

Predicate logic: the quantifiers, their domain and computation rules; Exercises; further applications: Island with inhabitants, logic circuit, and [Sudoku](https://en.wikipedia.org/wiki/Sudoku).

[Problem Set 1, due March 23](/homework_set_1.pdf) —— 请用白色A4至A5大小的白色纸张书写，若多于一页请订起来以免散失。由于课程人数众多，为了批改和收发方便，请一定不要直接上交作业本。多谢理解！

一班的同学：课上关于布尔代数的例题，证明过程中用到的结果补在[讲义](/Lecture_Notes.pdf)第四页下方，抱歉给你们造成的困扰！

### Lecture 5, 6, 7, 8: Proof and Algorithms

Lecture notes can be found [here](/Lecture_Notes_1.pdf): last updated: Mar 30, 2018. 

#### March 19, 2018
This is an introductory lecture about theory of proofs. Firstly we shall introduce the axiomatic formulation of mathematical theories, and give examples. Then, several ways of giving proofs. Lastly, we shall introduce the Well-ordered Principle (WOP), the Mathematical Induction (MI) and the Complete Induction (CI) and show their equivalence.  

Recommended reading:
+ Read about the [common proof strategies](http://www.mathcs.bethel.edu/~gossett/DiscreteMathWithProof/ProofStrategies.pdf) and the [common errors in proof](http://www.mathcs.bethel.edu/~gossett/DiscreteMathWithProof/CommonErrorsInProofs.pdf). Try to come up with more items to the lists if you can.
+ Read Section 1-8 (pp. 40) and 2-7 (pp. 75) of the text book.

#### March 23, 2018

Computability and provability: Sequence, programs, partial functions, Halting problem, Goedel's incompleteness theorems. Some relevant materials of the lecture can be found [here](http://www.math.hawaii.edu/~dale/godel/godel.html).

Further Reading:
+ If you are curious and ambitious, try to read [the AMS notes by Martin Davis](http://www.ams.org/notices/200604/fea-davis.pdf).


#### March 26, 2018

Two ways of encoding finite sequences in natural numbers: prime factorization and Goedel's function (using Chinese Remainder Theorem). Complexity of algorithms and counting critical operations. Then we shall focus on the example of searching and pattern matching problems, the corresponding algorithms involve sequential search, binary searching.

[Problem Set 2, due April 8](/homework_set_2.pdf) —— 请用白色A4至A5大小的白色纸张书写，若多于一页请订起来以免散失。由于课程人数众多，为了批改和收发方便，请一定不要直接上交作业本。多谢理解！

作业提示：有些代码中critical operations可能不止一个，在这种情况下需要针对每一个critical operation计算执行的具体次数。例如，2(c)中第7，8和9行的操作都是critical operation。

#### March 30, 2018

Pattern matching: Knuth-Morris-Pratt --- I loosely follow the notes of Hans Werner Lang, which you can find [here](http://www.inf.fh-flensburg.de/lang/algorithmen/pattern/kmpen.htm). The border is a special repeating structure one can find on a string, or a substring. In our case, we are interested in the borders of preffix of a pattern. The KMP algorithm consists of two parts: the computation of the table b\[m\] and the searching part.

计算b[m]代码的简单解释：假设我们已知b[0]到b[i]的值，也就知道了p[m]中p[i]之前的前缀所含有的最大配边(border)。那么p[0:i]（亦即由p[0], p[1],...,p[i]组成的前缀）的最大配边要么从p[0:(i－1)]的最大配边被p[i]延伸(extend)出来，或者是从p[0:(i－1)]的小一些的配边被p[i]延伸(extend)出来。可以延伸的语句判定就是p[i]==p[j]，而如果最大配边不能延伸，寻找次一级配边的长度，则需要用到j=b[j]语句。

Further readings:
+ [Boyer-Moore algorithm](http://www.inf.fh-flensburg.de/lang/algorithmen/pattern/bmen.htm), which is considered to be the most efficient method. It combines the shift table method as in KMP (although the comparison is right-to-left), as well as the last table. 阅读提示：我们课上没有讲KMP中shift table的计算代码。但在BM算法中bmPreprocess1()和bmPreprocess2()给出了怎样由配边理论得出shift table的代码；这段代码有助于理解为什么KMP算法亦可以由shift table构造。
+ 这两种算法的中文资料颇多，请有兴趣的同学自行选阅文献，不再赘述。

### Lecture 9, 10, 11, 12: Recursion and Modeling Computation

Lecture notes can be found [here](/Lecture_Notes_2.pdf): last updated: Apr 7, 2018. 

#### April 2, 2018

Reviewing the KMP algorithms, and the instruction for the second homework. Then we moved to the new section on recursion, its application in programming, and then the recursive sequence. For homognenous linear recursive relation of degree k, there is a general method of solving it using character equation, given that the character equation (degree k) has k distinct roots.

#### April 8, 2018

Continue on the recursive relation: solving them using generating functions （发生函数/生成函数/母函数）. The general theory of generating functions, manipulations involving shifting, multiplication and derivation. Examples of solving non-honomeneous, non-constant coefficient recursive relations.

Recommended Reading:
+ The general theory of generating functions is also covered in [this notes](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-042j-mathematics-for-computer-science-fall-2005/readings/ln11.pdf), so if you are not sure about what we covered in class, please refer to it.
+ Please make sure that you could follow all the calculation examples showed in class.

#### April 9, 2018

We introduced the theory of formal languages, the binary and unary operation on them, and the compatibility. Then we started to talk a bit about formal grammar. 

Recommended Readings:
+ 阅读教科书第八章前两节的内容，证明定理8-1.4。
+ There are many interesting [applications](http://web.cs.ucdavis.edu/~rogaway/classes/120/spring13/eric-dfa.pdf) of the theory of automata, even in [Biology](https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life).

[Problem Set 3, due April 20](/homework_set_3.pdf) —— 请用白色A4至A5大小的白色纸张书写，若多于一页请订起来以免散失。由于课程人数众多，为了批改和收发方便，请一定不要直接上交作业本。多谢理解！

#### April 13, 2018

### Lecture 13, 14, 15, 16: Counting and Combinatorics

#### April 16, 2018

#### April 20, 2018

#### April 23, 2018

#### April 27, 2018

[Problem Set 4, due May 4]() —— 请用白色A4至A5大小的白色纸张书写，若多于一页请订起来以免散失。由于课程人数众多，为了批改和收发方便，请一定不要直接上交作业本。多谢理解！

### Lecture 17, 18: Midterm Overview

#### April 28, 2018

#### May 4, 2018

### Lecture 19, 20, 21: Graph Theory

#### May 18, 2018

[Problem Set 5, due June 1]() —— 请用白色A4至A5大小的白色纸张书写或者打印，若多于一页请订起来以免散失。由于课程人数众多，为了批改和收发方便，请一定不要直接上交作业本。多谢理解！

### Lecture 22, 23: Trees

[Problem Set 6, due June 22]() —— 请用白色A4至A5大小的白色纸张书写或者打印，若多于一页请订起来以免散失。由于课程人数众多，为了批改和收发方便，请一定不要直接上交作业本。多谢理解！

### Lecture 24, 25: Functions and Relations

[Problem Set 7, due July 13]() —— 请用白色A4至A5大小的白色纸张书写或者打印，若多于一页请订起来以免散失。由于课程人数众多，为了批改和收发方便，请一定不要直接上交作业本。多谢理解！

### Lecture 26, 27: Final Overview

[Back](/index.md)
