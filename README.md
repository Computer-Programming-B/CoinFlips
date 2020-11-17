On average, how many times do you need to flip a coin to get three heads in a row?
==================================================================================

In this assignment you will write a computer simulation to answer the question "On average, how many times do you need to flip a coin to get three heads in a row?" Simulations are one way to solve problems that would otherwise be too complicated, expensive, time consuming, dangerous or even impossible to calculate or perform in real life. You can check your answer by comparing it to the this [solution on quora.com](https://www.quora.com/What-is-the-expected-number-of-coin-flips-until-you-get-3-heads-in-a-row). You may find slides 143-164 of the [slide presentation](https://docs.google.com/presentation/d/1rICcmNbnGYsB-cV_6EatPyzcOS2sId80Jh2kayUzm4Q/edit#slide=id.ga2b2b98a27_0_165) helpful in completing this assignment.
 
Suggested steps to starting this assignment
--------------------------------------------
1. Start a new Python 3 program on repl.it
2. Now we need some code to simulate flipping a coin. Type the following code and run the program several times to check the output:
```python
from random import *
flip1 = randint(0,1)==1
print(flip1)
```
3. You should see roughly a 50% chance of `True` or `False`. We'll say that `True` represents heads.
4. Since we are looking for three heads flips in a row, create two more variables `flip2` and `flip3`. Change your print statement to:
```python
print(flip1 == True and flip2 == True and flip3 == True)
```
5. Three heads in a row is unusual. You will might need to run the program 20 or 30 times until it prints `True`
6. Now, code the following algorithm to count how many flips it takes to get 3 heads in a row:
   + Initialize three variables `flip1`, `flip2` and `flip3` to be randomly `True` or `False`
   + Initialize another variable `numFlips` to 3
   + Write a `while` loop: `while not(flip1 == True and flip2 == True and flip3 == True):`
   + In the while loop:
      + assign  `flip1` the value of `flip2`
      + assign `flip2` the value of `flip3`
      + assign  `flip3`  a new random value that is a 50/50 chance of `True` or `False`
      + increase `numFlips` by one
   + print `numFlips`
7. You should now have a program that counts how many flips it takes to get three heads in a row. Run the program a number of times to get a sense of what the average number of flips would be 
8. Now we need to modify our program so that it will do many, many trials rather than just one. We'll start by creating a function definition `def oneTrial():`. Move all the code in the algorithm into the `oneTrial` definition. Change the last line to return `numFlips` instead of printing it.
9. Underneath your function definition, initialize two new variables `sum` and `count` to zero
10. Write a loop `while count < 1000:` Add code in the loop to:
   + Increase `sum` by the value returned by `oneTrial()`
   + Increase `count` by 1
11. Print `sum` divided by `count`. Check your result against [solution on quora.com](https://www.quora.com/What-is-the-expected-number-of-coin-flips-until-you-get-3-heads-in-a-row). Adjust the number of trials from 1000 until you get a stable result.
