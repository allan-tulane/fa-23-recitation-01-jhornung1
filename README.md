# CMPS 2200  Recitation 01

**Name (Team Member 1):**  **Jacob Hornung**  
**Name (Team Member 2):**_________________________

In this recitation, we will investigate asymptotic complexity. Additionally, we will get familiar with the various technologies we'll use for collaborative coding.

To complete this recitation, follow the instructions in this document. Some of your answers will go in this file, and others will require you to edit `main.py`.

## Install Python Dependency

We need Python library of "tabulate" to visualize the results in a good shape. Please install it by running 'pip install tabulate' or 'pip install -r requirements.txt' in Shell Tab of Repl.  

## Running and testing your code

- To run tests, from the command-line shell, you can run
  + `pytest test_main.py` will run all tests
  + `pytest test_main.py::test_one` will just run `test_one`
  + We recommend running one test at a time as you are debugging.

## Turning in your work

- Once complete, click on the "Git" icon in the left pane on repl.it.
- Enter a commit message in the "what did you change?" text box
- Click "commit and push." This will push your code to your github repository.
- Although you are working as a team, please have each team member submit the same code to their repository. One person can copy the code to their repl.it and submit it from there.

## Comparing search algorithms

We'll compare the running times of `linear_search` and `binary_search` empirically.

`Binary Search`: Search a sorted array by repeatedly dividing the search interval in half. Begin with an interval covering the whole array. If the value of the search key is less than the item in the middle of the interval, narrow the interval to the lower half. Otherwise, narrow it to the upper half. Repeatedly check until the value is found or the interval is empty.

- [ ] 1. In `main.py`, the implementation of `linear_search` is already complete. Your task is to implement `binary_search`. Implement a recursive solution using the helper function `_binary_search`. 

- [ ] 2. Test that your function is correct by calling from the command-line `pytest main.py::test_binary_search`

- [ ] 3. Write at least two additional test cases in `test_binary_search` and confirm they pass.

- [ ] 4. Describe the worst case input value of `key` for `linear_search`? for `binary_search`? 

**TODO: The worst possible case for the input value 'key' for the linear search would be whatever the final value would be in the list. Example would be in mylist = [1,2,3,4,5,6], worst case for key would be 6. On the other hand, for a binary search, the worst case either be the first or the last value in the list.**

- [ ] 5. Describe the best case input value of `key` for `linear_search`? for `binary_search`? 

**TODO: Best case for a linear search would be the first value in the list, and best case for a binary search would be the exact middle value of a list**

- [ ] 6. Complete the `time_search` function to compute the running time of a search function. Note that this is an example of a "higher order" function, since one of its parameters is another function.

- [ ] 7. Complete the `compare_search` function to compare the running times of linear search and binary search. Confirm the implementation by running `pytest main.py::test_compare_search`, which contains some simple checks.

- [ ] 8. Call `print_results(compare_search())` and paste the results here:

**TODO: |        n |   linear |   binary |
|----------|----------|----------|
|       10 |    0.004 |    0.004 |
|      100 |    0.006 |    0.003 |
|     1000 |    0.065 |    0.008 |
|    10000 |    1.300 |    0.043 |
|   100000 |   12.827 |    0.037 |
|  1000000 |  365.496 |    0.058 |
| 10000000 | 2250.532 |    0.062 |**


- [ ] 9. The theoretical worst-case running time of linear search is $O(n)$ and binary search is $O(log_2(n))$. Do these theoretical running times match your empirical results? Why or why not?

**TODO: This does mostly line up, as while linear search got dramatically larger and larger, the binary search time remained mostly the same and very small**

- [ ] 10. Binary search assumes the input list is already sorted. Assume it takes $\Theta(n^2)$ time to sort a list of length $n$. Suppose you know ahead of time that you will search the same list $k$ times. 
  + What is worst-case complexity of searching a list of $n$ elements $k$ times using linear search? **TODO: $O(nk)$**
  + For binary search? **TODO: $\Theta(n^2) + O(log_2(n))$**
  + For what values of $k$ is it more efficient to first sort and then use binary search versus just using linear search without sorting? **TODO: Sort and then Binary search is more efficient when $O(n^2)$ + $O(k*log(n))$ < $O(k*n)$**
