# Haskell Tutorial

In the following blog post I will give a small tutorial on how to begin understanding and using Haskell. 

## Downloading Haskell Windows:
If you are on a windows machine than this tutorial is for you.

1) First you need to get GHCI which is basically a terminal you can activate from your powershell that gives
you access to Haskell's compiler. 

2) Open your powershell and be sure to run it as administrator 

3) Copy and paste the following line in your powershell "Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux". This activates
a linux subsytem which will eventually allow us to use GHCI

4) Restart your machine 

5) In the past I have attempted to use CentOS to use Haskell but some odd errors and the inconveniance of launching a seperate operating system made me switch to Ubuntu.
Go to the windows store and download the latest version of Ubuntu.

6) Launch Ubuntu and create a username and password

7) Type the following lines of code to get Haskell going 
```
sudo apt update
sudo apt upgrade
sudo apt install haskell-platform
sudo apt install haskell-stack
```
Working with Haskell:
1) Open Ubuntu
2) Type GHCI to start the Haskell compiler 
3) Just to get a general idea of what the compiler does try a couple of these lines of code in your terminal:
```
300/2
5 * 2.3
mod 15 3 
```   
As one can see its a somewhat simple calculator. However throughout this course you will be using it in a different way

4) :cd SomePath to get into a workspace where you want to keep your files
5) Using the file explorer go to this same location and create a testing.hs file
6) Open the file with your favorite text editor. In this section I would like to explain how natural numbers work and how a natural number data type looks
7) Paste at the top of your file: 
data NN = O | S NN
    deriving (Eq,Show)
    
    What does this mean? We are essentially saying that we have a data type called NN (natural numbers). In this context a natural number can only be denoted by an O 
    or a S followed by another natural number. Now we are potentially already getting confused. 
    
    Here are some examples of some natural numbers:
    ```
    (S O) = 1
    (O) = 0
    (S(SO) = 2
    (S(S(S(S(S(S(S(S(S(S O)))))))))) = 10
    ```
    These are not natural numbers:
    ```
    (O O) -> cannot have an O attached to an O
    (O S) -> S must be attached to another natural number either O or S 
    (S S) -> The first S is correct however the second one needs to be attached to something else
    ```
    To solidify this more -> Paste a line or two below the following:
    ```
    int2nn :: Int -> NN
    int2nn 0 = O
    int2nn n = if n >= 0 then S(int2nn(n-1)) else error "not a positive number"
    ```
    Pay no attention to what these functions are doing for now. Save your test.hs file.

8) If you are in the same directory as your test.hs file type ":load test.hs" to compile your written code
9) Now you can type "int2nn 5" to see how the type looks in our natural numbers program. Use this function whenever you are having trouble inputing a natural number for testing
10) Now that you are able to define and understand natural numbers in our language we can begin to use some simple calculations
11) The following is the definition of subtraction which you can paste into your test file
    
    ```
    -- subtract
    subtr :: NN -> NN -> NN
    subtr O n = O
    subtr n O = n
    subtr (S n) (S m) = subtr n m
    ```
    Save your file and load it again in GHCI.
    You can test this by typing something like these into your console:
    ```
    subtr (S O) (O) 
    subtr (S(S(S O))) (S O)
    ```
    Each of these should give you an answer that is correct
    
    Now how does this subtr function work? 
    If you look at the first two lines: subtr O n and subtr n O these are essentially saying: if we subtract any number great than 0
    from 0 than we get 0 (there are no negatives with natural numbers) and we also have that if we subtract 0 from any number that is greater than 0 than we get that number.
    The third final line "subtr (S n) (S m) = subtr n m" is our recursive call. This is our recursive call, although you are just starting it is good to know for future 
    reference that the function's input on a recursive call should continue to decrease over each call. What we are doing here is kind of a different way of doing 
    subtraction than what one is used to. Instead of saying I take away 5 from 7, I am instead descreasing 5 and 7 by one each call by removing their leading S. As one can
    see the diffence between (S N) and n is that n is one less than (S N). Once one of our inputs into the subtr equation is 0 than we have our answer.
    
12) Take a look at this slightly more complicated example that uses the subtr function and conditional statements to make less than work. First try to understand the base case(s)
(the line of code that will terminate recursion) and then try to see how the subtr is used to get an answer. 

```
less :: NN -> NN -> Bool
less O m = True
less n O = False
less (S n) (S m) = if subtr n m == O && subtr m n /= O then True else False
```
    
Sources:
https://www.youtube.com/watch?v=5RTSlby-l9w&ab_channel=PercyGrunwaldfromTopTechSkills
 
