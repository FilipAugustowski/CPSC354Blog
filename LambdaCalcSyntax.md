# Syntax in Regards to Lambda Calculus

When we first began learning about Lambda Calculus I was pretty confused why. I mean its a sort of language where you literally only need to remember 3 rules for its syntax.
We have that :
```
e ::= λx.e ∣ ee ∣ x
```
Now one of the main take aways from lecture was that this abstract syntax definition is meant to be as concise as possible. We use λx.e to denote a function e that may
have a variable x within it. We use ee to abstract a program e which is input to another program e and x is just a variable. When initially thinking about this, it seems
that this would never suffice as a programming language, however I felt this changed as we continued learning about its nuances.

Once one looks at the concrete syntax of the Lambda calculus language they should note that it is setup in a way using expression from the previous assignment. This is 
very useful and powerful for streamlining the calculator functions that we had created. Furthermore, the Lambda calculus syntax is so usefully abstract that it allows us to
add many more functions to the calculator without having to worry about the organization or structure of the program. Furthermore, this allows us to create long lines 
of lambda calculus strings which will essentially act as a program. I guess the main idea is that if you are going to learn about how programming languages are built and structured you should start with the simplest program. If we think about the first computers ever created all they could really do was calculate these simple mathematical equations so that's why we are beginning to learn from here. 

To give more justice to the syntax of Lambda calculus one should attempt to understand these examples and intricacies. 

1) When writing λx.(abc) one rewrites it as λx.((ab)c) due to the fact that eee is left associative. I believe the reasoning for this rule is that one wants to evaluate ab as a separate ee which can be resolved to an e. This solution e can then be reapplied to have ee within the intial expression. So the idea is one wants to solve the first two expressions together and then apply its result to the third. 

2) When writing λx.(λy.λz.(abc)) we first apply the parenthesis to abc as previously described so that 

  λx.(λy.λz.(abc)) = λx.(λy.λz.((ab)c))
  
  Now there is also a rule that applies to the abstraction within the equation which is right associative so that 
  
  λx.(λy.λz.((ab)c)) = λx.(λy.(λz.((ab)c)))
  
  To sort of simplify the idea take a look at this 
  λx.λy.λz = λx.(λy.λz)
  λx.(λy.λz) = λx.(λy.(λz))

  After looking at this a bit I believe the rule makes sense in that the input into the left most λx. should be fully solved before being input. By adding the parenthesis one
  seems to abstract whats going on in (λy.(λz)) from λx. so that it appears as λx.x. 
  
## Some Philosiphy; Non-Extensionality
After some close reading I learned something that struck me as quite interesting in regards to the philosophy of Lambda calculus and how it relates to general mathematics. To start off, it is clear that Lambda calculus is a simple language with only three rules that allow one to first define functions and then input values into those defined functions. The idea of a function can be extended to a rule in that the function is a rule that defines what happens to a specific input. The main point is that this is how functions in Lambda calculus should be viewed. In normal on paper mathematics one can check that two functions are equivalent if the set of the inputs and outputs of the two functions are exactly equivalent. These functions in normal math can be seen as functions as sets objects which are *extensional* while on the other hand functions as rules are not. One does not define Lambda calculus functions as extensional because determining if two functions are equivalent in Lambda calculus is not as easy as comparing sets of inputs and outputs. Instead functions as rules are *non extensional* or *intensional*. This means that defining whether two functions are equivalent in Lambda calc is done by verifying that the two functions operate on input in the same exact way. For example, if I had two Lambda calc functions: one that gives me the fastest race car driver in the U.S and one that gives me the fastest race car driver in the world; lets say that the fastest race car driver in the world is an American so that would mean that these two functions give the same answer. While they are equivalent answers; they are only extensionally equivalent and not intentionally . However, the extensional equivalency is broken if perhaps the fastest race car driver in the world is from Poland. 


Sources: https://plato.stanford.edu/entries/lambda-calculus/
