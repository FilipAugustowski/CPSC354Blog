# Concrete vs Abstract Syntax

During the third week of programming languages we were introduced to the idea of concrete and abtract syntax. When first presented with the idea that they were, in a major way,
different I was slightly confused. I mean I honestly don't understand why we did what we did in the assingment. I may have known how to do it but not neccesarily why. So I 
have decided to make this blog post to work out the concepts in my head.

As it was presented in the lecture I will start with Abstract Syntax. 

### What does Abstract Syntax mean? 
Abstract syntax does not seem to have a clear cut definition in and of itself but I think I understand how it is meant to be interpreted. Firstly Abstract Syntax seems to be 
the preffered way for a compiler/machine to read code. The parse trees that we developped in class are directly tied to the definition and understanding of abstract syntax due
to the fact that it shows in a general way how computation for the program will operate and how our program is taken apart. Now by taking a look at the following line of code:
```
mult (S n) m = add m (mult n m)
```
One sees the simple defintion for multiplication in our abstract syntax. I feel that one could call this abstract as one has no information on the variables within the equation.
Furthermore, it makes sense how one could define a tree from the recursive calls of this function. Here is an example of multiplication:
```
mult (S(S(S(S O)))) (S(S O)) = add (S(S O)) (mult (S(S(S O))) (S(S O)))
mult (S(S(S O))) (S(S O)) = add (S(S O)) (mult (S(S O)) (S(S O)))
mult (S(S O)) (S(S O)) = add (S(S O)) (mult (S O) (S(S O)))
mult (S O) (S(S O)) = add (S(S O)) (mult (O) (S(S O))) 
WE STOP HERE AND GET OUR RESULT (S(S(S(S(S(S(S(S O))))))))
```
These trees are of course simple but start to become very long and convoluted thus thats why we treat abstract syntax as the preffered language for the compiler. There are more reason for this though: the abstract syntax has a very specific order of input, no steps can be skipped, and it is difficult to write a readable operation/function. 
On the other hand we have concrete syntax which should be designed as the preffered language for humans.

### What does Concrete Syntax do and how does it work?
Now to just set up my thought process we had in the abstract syntax equation mult (S(S(S(S O)))) (S(S O)), using this multiplication equation of course gets you the right answer but it clearly takes a while to do all the work and steps. I would rather like to calculate 4 * 2 = 8. To do this in practice with a programming language we develop the idea of concrete syntax where I could quickly and easily write out calculations and not have to depend on the abstract definition of our functions. Instead we can use our current way of doing calculations (using normal mathematical equations and symbols) by making use of parsing to translate our concrete syntax into abstract syntax so that the machine can compile the code and do our calculations. In the assingment we explored parsers by first writing a context free grammer as such:

```
eval (Num n) = n
eval (Plus n m) = (eval n) + (eval m)
eval (Times n m) = (eval n) * (eval m)
eval (Sub e1 e2) = (eval e1) - (eval e2)
```

This context free grammer is much nicer to work with as a programer because we no longer have to use succesor numbers and can instead use Haskell's built in functions. 
This context free grammer was then used with BNFC to define a set of files that takes our expression data types and gives a propper final answer for calculations. Overall
I think I have gotten the main idea right for the concrete vs abstract syntax however I stil do not think I understand how good of a tool BNFC is or what it really does. It seems that a whole course itself could be taught on why BNFC is so useful and how to design something similar to it.
