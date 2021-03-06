# Lecture 0

___

## Defining algorithms

An algorithm is a series of actions such that they yield a result or an effect.

## What defines a good algorithm?

First and foremost, for an algorithm to be good, it first has to complete some criteria, ex:

* Sort an array in ascending or descending order
* Navigate a datastructure in a specific way
* Find pair of values in an array
* Print a message

If an algorithm does not fill the criteria for which it was written then it is of no use.

Depending on a situation, a slower algorithm may be preferred over a faster algorithm that consumes more space. Moreover in some cases, where the dataset cannot be contained in the memory and disk operations are required, an algorithm that is slower but has less disk operations is preferred over a faster with a lot more operations.

Understanding the underlying structure of the data as well as the problem is more important than simply using a good algorithm for _x, y, z_.

___

>…git actually has a simple design, with stable and reasonably well-documented data structures. In fact, I'm a huge proponent of designing your code around the data, rather than the other way around, and I think it's one of the reasons git has been fairly successful […] I will, in fact, claim that the difference between a bad programmer and a good one is whether he considers his code or his data structures more important. Bad programmers worry about the code. Good programmers worry about data structures and their relationships.
>
>Torvalds, Linus (2006-06-27). Message to Git mailing list. Retrieved on 2006-08-28.



__Example as to why understainding the dataset is more important than code:__

Suppose you have 1 million numbers where: $$x\epsilon[0,100]$$ 
_(This means the minimum value of x is 0 and the maximum is 100)_

And you are tasked to sort them.

The simplest way to do this is by beginning from the start and go towards the end picking the biggest number we find and putting it in the end, the next number we find is put each time before the previous we placed.

Bubblesort has $${O(n^2)}$$ time complexity. This means that at most, the algorithm has to make comparisons in the order of $${n^2}$$ where _n_ is the amount of elements in the dataset.

In this scenario, we have to do comparisons in the order of $$1,000,000 ^ 2 = 1,000,000,000,000 = 10^{12} = 1 trillion$$

A more efficient algorithm is mergesort. In mergesort, the array is split into smaller and smaller segments until segment of size 1. Then recursively merge the segments into bigger, sorted segments.

Mergesort has $${O(n \times log_2n)}$$ time complexity, thus, the worst case of mergesort in this scenario requires comparisons in the order of  
$${1,000,000 \times log_21,000,000 = 10^6*19.931569 = 10^7*2} = 200 million $$

An even faster way is using bucket sort. Bucketsort counts how many times each value is found within the array and then recreates the array sorted. 

Bucketsort has $${O(n)}$$ time complexity, meaning that in this scenario, we have comparisons in the order of: $${1,000,000 = 10^6}= 1 million$$

Bucketsort however, is very dependent on the dataset as well as machine constraints.