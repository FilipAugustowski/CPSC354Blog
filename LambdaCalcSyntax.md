# Syntax in Regards to Lambda Calculus

When we first began learning about Lambda Calculus I was pretty confused why. I mean its a sort of language where you literally only need to remember 3 rules for its syntax.
We have that :
```
e ::= λx.e ∣ ee ∣ x
```
Now one of the main take aways from lecture was that this abstract syntax definition is meant to be as concise as possible. We use λx.e to denote a function e that may
have a variable x within it. We use ee to abstract a program e which is input to another program e and x is just a variable. When initially thinking about this, it seems
that this would never suffice as a programming langauge, however I felt this changed as we continued learning about its nuances.

Once one looks at the concrete syntax of the Lambda calculus langauge they should note that it is setup in a way using expression from the previous assingment. This is 
very useful and powerful for streamlining the calculator functions that we had created. Furthermore, the Lambda calculus syntax is so usefully abstract that it allows us to
add many more functions to the calculator without having to worry about the organization or structure of the program. Furthermore, this allows us to create long lines 
of lambda calculus strings which will essentially act as a program. I guess the main idea is that if you are going to learn about how programming languages are built and structured
you should start with the simplest program. If we think about the first computers ever created all they could really do was calculate these simple mathematical equations so 
thats why we are beginning to learn from here. 

