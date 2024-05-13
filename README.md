# Recursive-vs.-Non-recursive

Here is the propmt for this programming assignment that was given in class:
1)	Ask the user to specify the number of steps, n, in a staircase.
2)	Ask the user to specify the set of steps that are allowed in each leap, for example, {1,2} or {1,3,5}. The cardinality of this set needs to be in the range of [2, n] and the value range for any member in this set should be [1,n].
3)	Design both the recursive and non-recursive algorithms to output the total number of different ways to get to the nth step in the staircase along with the details of each way.
4)	Use the following format for your output.

The time elapsed in the recursive algorithm is xxx.
The time elapsed in the non-recursive algorithm is yyy.

There are a total of xxx ways.
Way 1: 1 -> 1 -> 1 -> …->1
Way 2: 1 -> 1 -> 1 -> …->2
…
Way xxx: …



Here is how the program is ran:
The program is run by first entering the total number of steps. Then, you input the number of different leap values, or leap sizes, you are implementing. Then, one at a time, you input those different leap values. Then, the program generates every possible combination of leap values that add up to the total number of steps.
