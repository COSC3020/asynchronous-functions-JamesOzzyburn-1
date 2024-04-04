[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/26dp6wek)
# Asynchronicity

Implement a function that takes an array and a key to search for and counts the
number of times key matches an element in the array (the count matches function
we talked about in lectures). Your implementation must count the number of
matches asynchronously, but does not need to do so in parallel. What type of
asynchronous execution you choose is up to you.

I have not provided a template; depending on how you choose to implement the
function, it will have a different signature.

I have also not provided any test code, but you can base yours on test code from
other exercises. Your tests must check the correctness of the result of running
the function and run automatically when you commit through a GitHub action.

The [async library](https://caolan.github.io/async/v3/) may be helpful with
this.

## Runtime Analysis

What is the time complexity of your implementation (worst-case $\Theta$)? Add
your answer, including your reasoning, to this markdown file.


## Answer
For my code I chose to write it in c++ just to try something different. My code starts out by making 2 copies of the original array and each copy only has half of the array so im thinking the runtime for that would be $2*(n/2)$ where $n$ is the size of the original array so effectivly I believe its just $n$ for this part. For the compute part I create two async calls which return their own future and each async call just loops though the array and counts all of the matches which is $n$. The only part im not really sure on is as we spawn two async calls we make two threads so and each thread is doing half of the work it would do if the code was single threaded but there is two calls so intuitively I think this is also $2*(n/2)$ which is just $n$. So in total I believe my code is $\Theta(n + n)$ which can be simplified to $\Theta(n)$. 
