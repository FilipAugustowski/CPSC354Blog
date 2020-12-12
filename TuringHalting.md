# Turing Machines and The Halting Problem

For the following blog post I wanted to cover turing machines since I lack a complete understanding at this point of what exactly is a turing machine is, what its uses are, and why it was developed. In addition, I will address the Halting problem and how it pertains to a turing machine.

### Turing Complete and Turing Machines
Around 1946 Allen Turing first presented his paper for a stored program computer, which was the beginning of a new displicine in math. The whole point of the paper was to design a system in which any sort of function, algorithm, or program could be input and thus give an output. Furthermore, there must be a way for each of those algorithms or programs to perform its inner functions. Clearly there had to be a very intelligent way of abstracting all that information. The turing machine in fact was the answer to this needed abstraction which Allen Turing addresses within his paper. There are a couple of main components to a turing machine, but its simplistic design goes as follows: there is a long strip of a material which is seperated into any number of smaller boxes; these smaller boxes can include a 1,0, or nothing and these values are scanned by a turing machine. The turing machine can be imagined as a small component about the size of the tape boxes which goes 1 by 1 on the tape reading off values. These values: 1 or 0 are then fed into the turing machines handbook. The handbook is essentially where the programmer places code and when a 1 or a 0 is read into the handbook, the handbook performs an operation based on that input. In the simplest case, if there is a 0 input at position 14 then the handbook could say something like:

```
State 14:
If 1 
then erase 
write 0
move State 16;
```
What this code is simply saying is if there is a 1, write a 0 instead and move to state 16. Over time this program handbook and the different functions it has will completely change the data that was intially encoded into the tape. 

Now why is this so useful and why is it so fundamental to the study of computation. The idea however is that any computer or device can actually be encoded with its functions onto this turring machine and as a result its functions would complete and be written to the tape. This is known as being Turring complete in that if a specific computer or device performs its operations in this sequential coding manner it mirrors the turring machine.

### Halting Problem

An approach to the halting problem to start is that once this idea of a turing machine started to take over the math world, mathematicians wanted to know whether or not first order logic is decideable. This means, if there is a specific input into a turing machine can there be a sure shot way to confirm what the output should be? Allan Turing in his paper explained that it is not possible for first order logic to be decideable. The way to confirm this idea is by understanding the two things that can occur when inputting data into a turring machine and waiting for its result: in one case the machine could never finish the computation or it gives an answer. In other words, will the turing machine halt or will it continue forever. To test whether a specific program halts or not one must obtain a yes or no answer to "Does it halt" from the program. This in and of itself is a paradox and this is where the halting problem comes from.

If there is a specific machine that gives a yes or no answer as to whether another specific program halts or not it would have a problem. If the machine states yes the program halts than one would get the response from the machine yes it halts and it would stop. However if a specific program never halts, than there is no possible way to get an answer no out of it since the machine will always get stuck with the input function that never halts. Thus this is the Halting Problem; there is no way to tell whether or not the machine actually goes on forever or if there is an issue with the code. 


https://en.wikipedia.org/wiki/Alan_Turing#Early_computers_and_the_Turing_test
