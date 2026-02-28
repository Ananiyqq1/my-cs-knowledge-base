```
Chapter 1: Overview of Algorithms
```
- Algorithm
	- a finite set of unambiguous instructions that, given some set of initial conditions, can be performed in a prescribed sequence to achieve a certain goal and that has a recognizable set of end conditions
	- is a set of rules for carrying out some calculations to solve a problem
	- designed to yield results for any valid input according to precisely defined instructions
- Phases of Algorithm
![Phases of an Algorithm](./Phases%20of%20an%20Algorithm.png)
	- Development Phase
		- Design Phase - architecture, logic, and
implementation details of the algorithm are envisioned and documented
	   - Coding Phase - the designed algorithm is converted into a computer program
	- Deploying - involves the design of the
actual production environment where the code will run

![Deploying](./Flow%20of%20Steps.png)

- Pseudocode
	- higher-level description of an algorithm in a semi-structure way
	- example SRPMP
```
1: BEGIN Mapping_Phase
2: Ω = { }
3: k = 1
4: FOREACH Ti∈T
5: ωi = RA(Δk,Ti)
6: add {ωi,Ti} to Ω
7: state_changeTi [STATE 0: Idle/Unmapped] → [STATE 1: Idle/Mapped]
8: k=k+1
9: IF (k>q)
10: k=1
11: ENDIF
12: END FOREACH
13: END Mapping_Phase
``` 
- Snippet
	- represent the logic of the algorithm directly in the programming language in a somewhat simplified version
	- example swap two variables
```
define swap(x, y):
	buffer = x
	x = y
	y = buffer
```
- concerns when designing algorithm
	- Concern 1: Is this algorithm producing the result we expected?
	- Concern 2: Is this the most optimal way to get these results?
	- Concern 3: How is the algorithm going to perform on larger datasets?
- algorithms classification based on characterstics of the problem
	- Data Intensive
		- algorithms are designed to deal with
a large amount of data
		- relatively simplistic processing requirements
		- example: compression algorithm applied to a huge file
	- Compute Intensive 
		- considerable processing requirements
		- donot involve large amounts of data
		- example: algorithm to find a very large prime number   
	- Both Data and Compute Intensive
		- the most resource-intensive
algorithms
		- require careful design of the algorithm and intelligent allocation of available resources 
		- example: Algorithms used to perform sentiment analysis on live video feeds
- Data Dimension
	- Volume - the expected size of the data that the algorithm will process
	- Velocity - the expected rate of new data generation when the algorithm is used. It can be zero
	- Variety - quantifies how many different types of data the designed algorithm is expected to deal with
![Data Dimension](./Data%20Dimension.png)
- Compute Dimension
	- is about the processing and computing needs of the problem at hand
	- The processing requirements of an algorithm will determine what sort of design is most efficient for it
- Performance Analysis
	- One of the ways to estimate the performance of an algorithm is to analyze its complexity
	- complexity theory is the study of how complicated algorithms are
		- It should be correct
		- It should be understandable
		- It should be efficient
		- there are two types
			- Space Complexity - estimates the runtime memory requirements needed
				- the algorithm needs to store the transient temporary data structures in memory
				- The way the algorithm is designed affects the number, type, and size of these data structures
			- Time Complexity - estimates the time the algorithm will take
				- two basic approaches
					- *post-implementation profiling approach*: In this approach, different candidate algorithms are implemented and their performance is compared
					- *pre-implementation theoretical approach*: In this approach, the performance of each algorithm is approximated mathematically before running an algorithm
				- is not dependent on any hardware that the algorithm will run on
				- solely depends on the structure of the algorithm itself
	- types of cases to consider when conducting a performance analysis
		- Best case - the data given as input is organized in a way that the algorithm will give its best performance
			- Best-case analysis gives the upper bound of the performance
		- Worst case - is to try to find the maximum
possible time it will take to get the job done under a given set of conditions
			- Worst-case analysis gives the lower bound of the performance of the algorithm
		- Average case - starts by dividing the various possible inputs into various groups. Then, it conducts the performance analysis from one of the representative inputs from each group. Finally, it calculates the average of the performance of each of the groups.
	- Big O notation - is used to quantify the performance of various algorithms as the input size grows
		- *Constant time* O(1) - If an algorithm takes the same amount of time to run, independent of the size of the input data
		- *Linear time* O(n) - if the execution time is directly proportional to the size of the input
		- *Quadratic time* O(n$^2$) - if the execution time of an algorithm is proportional to the square of the input size
		- *Logarithmic time* O($log$n) - if the execution time of the algorithm is proportional to the logarithm of the input size
- Validating an Algorithm
	- confirms that it is actually providing a mathematical solution to the problem we are trying to solve
	- should check the results for as many possible values and types of input values as possible
	- based upon assumption used to simplify logic
		- Exact Algorithm - expected to produce a precise solution without introducing any assumptions or approximations
		-  Approximate Algorithm - When the problem complexity is too much to handle for the given resources
		simplify our problem by making some
assumptions.
	- Explainability - are used for critical cases, it becomes important to have the ability to explain the reason behind each and every result whenever needed. This is necessary to make sure that decisions based on the results of the algorithms do not introduce bias
	 