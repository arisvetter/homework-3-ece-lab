# Lab 04 - SOP/POS and KMaps

In this lab, you’ve learned how to apply KMaps, Sum Of Products and Products of
sums to simplify digital logic equations. Then, you’ve proven out that they work
using an implemented design on your Basys3 boards.

## Rubric

| Item | Description | Value |
| ---- | ----------- | ----- |
| Summary Answers | Your writings about what you learned in this lab. | 25% |
| Question 1 | Your answers to the question | 25% |
| Question 2 | Your answers to the question | 25% |
| Question 3 | Your answers to the question | 25% |

## Lab Summary

In this lab, we generated a naive equation to represent the truth table we were given. Every row that resulted in a Y value of 1, we represented with an equation of A & B & C & D, with the not's appropriately inserted. Then, we constructed a KMap from the truth table. We grouped terms together that we could simplifiy to create expressions that represent that group. Then, we combined all of those expressions to create an overall equation for Y, which was much simpler thant the initial naive equation we created. We followed the same process again but inverted all of the 1's and 0 values. The expressions we created from this KMap represented !Y. We used De Morgan's law to tranform that equation to one that represents Y. We then simulated and tested to ensure all three equations matched.

## Lab Questions

### Why are the groups of 1’s (or 0’s) that we select in the KMap able to go across edges?

The groups are able to go across edges because when moving from the end of one row back to the start of that row (or the end of one column back to the start of the column), only 1 variable changes. For instance, the final column in an AB x CD KMap is 10, and the first colum in 00. In the transition from the last column to the first column, only the variable B is changing. If only one variable is changing, we can group the outputs together. We could really more accurately represent each column and each row as a circle, or the overall KMAp as a torus, but for ease of creating and using it do not.

### Why are the names Sum of Products and Products of Sums?



### Open the test.v file – how are we able to check that the signals match using XOR?
In test.v, we use XOR to compare the output of the naive equation we created with the output of our minterm, and then the naive equation with the output of our maxterm. Because all of these equations were derived from the same truth table, the outputs should always match. We assume that our naive equation is correct for test.v. As XOR only results in a truth when exactly one of the inputs is 1, the XOR logic will only result in a truth when something is wrong and one of our equations doesn't match. At that point, test.v displays a message that either the maxterm or the minterm doesn't match.
