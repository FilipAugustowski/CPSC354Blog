# A History of Ocaml
In the following blog post I wanted to introduce the reader to Ocaml, a programming language that I had used for a full semester and never really researched. 

## Where does the name come from?
So CAML is meant to stand for *Categorical Abstract Machine Language* which is a sort of pun that makes reference to CAM (*Cateogrical Abstract Machine*) and ML (*Meta Language*). These two names then give the indication of what sort of language Ocaml will be. On one hand the CAM portion adds class inheritance and dynamic method dispath while on the other hand the ML tells us that the program will not require type definitions, a garbage collector is supplied, and the language has an imperitive aspect to it. 

## A Short History
Simply, the development of Ocaml was a result of the continued development and improvemnt of ML type languages. The circle of professionals who worked on ML languages and subsequently Ocaml were based in Europe on what was known as the Formel team. In Edinburgh during the 1980s the Formel team became interested in ML because it was recieving large and useful updates. LCF (*Logic For Computable Functions*) is "an interactive automated theorm prover developed at Standford and Edinburgh... Work on the LCF system introduced the general-purpose programming language ML to allow users to write theorem-proving tactics, supporting algebraic data types, parametric polymorphism, abstract data types, and exceptions." which is what was used with ML during this time in order to improve the usefulness of the language. LCF was designed by Robin Milner (A turing award winner) and incorporated both ML and Lisp programming. 

One issue with this however was that LCF could not run on varying types of operating systems at Formel like: Multics, Berkeley Unix on Vax, and Symbolics. Just as a small aside, I personally had never heard of any of these operating systems, but it was interesting to learn the Multics was actually a very powerful operating system during the 70s and 80s since general motors, and Ford both used the system. Multics was later used as a model to create Unix.

So a French computer scientist (this is important as a French team is what spearheaded Ocaml), Gérard Huet, chose to make LCF compatible with Lisp compilers such as MacLisp, FranzLisp, LeLisp, and ZetaLisp. Lisp just for background is the second oldest high level programming language developed; it is a year younger than ForTran. With this more people like Guy Cousineau and Larry Paulson began to contribute by adding a compiler, algebraic data types, and pattern matching. The next big development that brought Guy Cousineau to want to develop a new implementation was when Pierre-Louis Curein developed a connection between Lambda Calclus and categorical combinators. This idea is the basis for Cousineau's work because he had scene the categorical combinators as a means of improving compilation for ML. From here a team at Formel was started and Guy Cousineau led the developement of OCaml. One of the key features of Ocaml when it was developped was it adaptibility and option to change syntax within the language; the main idea was to give a pathway to change the language as time went on or when the Standard ML was upgraded. 


https://en.wikipedia.org/wiki/ML_(programming_language)
https://en.wikipedia.org/wiki/Categorical_abstract_machine
https://caml.inria.fr/about/history.en.html
https://en.wikipedia.org/wiki/Robin_Milner
https://whatis.techtarget.com/definition/Multics-Multiplexed-Information-and-Computing-Service#:~:text=Multics%20(Multiplexed%20Information%20and%20Computing%20Service)%20was%20a%20mainframe%20time,GE)%2C%20and%20Bell%20Labs.
https://en.wikipedia.org/wiki/Lisp_(programming_language)
