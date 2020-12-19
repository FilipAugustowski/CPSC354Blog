# Abstract Reduction Systems

Over the past week in Programming Languages we have learned about Abstract Reduction Systems (ARS) using Lambda Calculus as the model of rules to abstract. We learned that 
ARSs that are confluent and terminating are sound abstract models for an algorithm or a programming language. At this point, we have coded a calculator that has an interpreter 
thus making it easier for humans to use/read and it preserves readability for our machine. Now, the discrete mathematics that comes with an ARS seems to make sense to me, but 
I wanted to explore how this will help us with coding in and of itself. 

To start this I think I would like to go over why confluence and termination are highlighted and so important. Confluence was covered less so than termination in the lecture
so I decided to do some of my own research and upon opening one of what seemed hundreds of papers I realized why it was not covered and how complex the concept is. To summarize
slightly one defines confluence as a binary relation in which "two coinitial reductions (i.e., reductions having the same starting term) can always be extended towards a common 
reduct"(1). To sort of translate this into plain English I believe that this means that we want an ARS where any two starting terms or functions that are the same can be broken 
down into different steps and still give us the same answer. It is important to note that this adds to our code a way to write things in the order humans think
makes the most sense and have the machine do the order of operations in the way in which it needs. Something interesting to note is that termination is something that is difficult
to prove, however not nearly as much as confluence. Termination has a well known hierarchy ZAN01 which is a sort of system that one can use to prove if a system terminates. 
ZAN01 is noted because it is currently the established hierarchy to prove a system terminates, however confluence has no established system. It seems that confluence is much harder
to prove because there are way more choices that one has to account for in order to justify a proof. In and of itself it is difficult to find a way of breaking down two terms 
so that you show confluence, however once you have developed a system it could be that your system is very slow to tell you if you have confluence. This is why I believe we were
not expected to learn this in class, however the connection between the way one orders input and coding shows me that this is important and very useful to understanding the 
fundamentals of programming. 

Termination is when we have an ARS that only allows calculations that actually terminate. Once again we are trying to remove ambiguity from our programming language and make it so
that the program's recursion continuously produces smaller values and that eventually we hit a base case. If we have an infinite loop from any program than the system using the 
language is sure to fail like what was described with Windows earlier on. To illustrate the importance of termination I would like to you use a game design example. If you 
are using Unity or any sort of game engine you will have a player movement script for example, often the player movement script must take in a direction (from input) 
and a magnitude of force (predetermined) to produce a velocity which is then applied so that the character moves. The collection of the input happens a few times per second, if
at any point our calculation of velocity does not terminate than the character as a whole will stop working. This also means that any other code happening in the collection
function will break such as checking if the player is grounded, rotating the player to where they want to look, among others. There have been many times in the past where
I will create a function that does not terminate to a value or I create a loop that does not terminate and it has actually made my computer crash. I find that it is very 
interesting that these general concepts expand to all parts of the coding world. I think the only thing that I am unsure of is how an ARS takes form in a program, does it 
takes its form in the parser, the interpreter, in normal code, or the system as a whole is an ARS and together its elements work with one another to justify this definition.

Sources: https://ir.cwi.nl/pub/29552/1901.10773.pdf (1)
