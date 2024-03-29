 *Notes*

--------------------------
# Wednesday January 17th
--------------------------

# What problems can algoriths solve?
* #### Managing big data on the internet
    * Search Enginge for findign data

# Why Study Algorithms ?
* #### Algorithm is a technology you should master
    * advacned computer artitecture
    * efficient algoirthms
    * machine learning
    * mobile devices
    * fast networking both wried and wireless
* ##### Consider sorting the list of n = 10^7 numbers as an example
    * #### **Insertion Sort** takes time C1N^2 where c1 is a constant
    * Suppose this is run on a fast computer that can do a numver of instructions
    * Suppose the code is optimized such taht c1 = 2
    (2* (10^7)^2 instructions) = 20000 instructions
* #### **Merge sort** takes time C1N logn where c1 is a constant
    * Considering this running on slow computer it would only take 1163 making it more optimized for the solution


# Friday January 19th

------------------------

# Sorting

* ### Problem of sorting
    * input: an array of numbers
    * Output: a permutation or reordering
        * Example:
            * Input: 8 2 4
            * output: 2 4 8
* ### Why is sorting important
    * sorting can be used to represent important problems and prprocess data for things like travel websites
* ### Sorting Algorithms
    * Insertion, Merge, Quicksort, Heapsort

# Insertion Sort
    Best-case Array is already sorted
    Insertion sort is an Θ(𝑛^2) algorithm
*I believe that all of the content and pseudocode has the first index as 1 and not 0**
* https://www.youtube.com/watch?v=JU767SDMDvA&ab_channel=MichaelSambol
    * An efficient algo for sorting a small number of elements
    * **IDEA** similar to sorting a hand of playing cards
        * start with empty left hand and a pile of cards
        * grab from pile with right hand and insert into left hand in correct position with largest num to the right
    * 5 2 4 6 1 3
    * Look at the next position and swap
        * i.e. compare 5 with 2, 2 is less so swap
        * i.e. compare 5 with 4, 4 is less so swap
        * continue until sorted
 #### Psuedcode
    for i = 2n
        key = A[i]
        // insert A[i] int othe sorted subarray A[1:i-1]
        j = i - 1
        while
            J > 0 and A[j] > key
            A[j+i] = A[j]
            j = j - 1
        A[j+1] = key
* ### Why insertion sort works correctly?
    * **Loop invariant**
        * At the start of each iteration of the outer-for loop, the subarray A[1: i-1] consits of the elements orginially in A[1: i-1] but in the sorted order.
    * Need to show three things
        * **Intialization** : true prior to first interation
        * **Maintenance**: true before iteration and remains true before the next iteration
        * **Termination** : loop terminates and invariant shows it's true
* ### Running time analysis
    * denote input size n with T(n)
        * **size of the input n** : short easier to sort
        * **nature of the input** : an already sorted list is easier to sort no shit
    * Time analyzed on RAM model:
        * k-th line of code takes ck time to run where ck is a constant
    * ![Runtime](insertionRuntime.png)
    * **Best Case** : array is already sorted so ti = 1 for i = 2,3, ...... n
    * **Worst Case** :  array is in reverse sorted order so ti = i for i  = 2,3, .... n

* ### Worst-cast running time
    *we'll focus on worst*
    * It gives upper bound providing a runtime **gauruntee* certified by professor sun
    * Worst happens a lot i.e. searching for info on database that doesn't exist
    * The *average case* i.e. one that is half sorted half not is usually just as bad
* ###  Order of Growth
    * We simplify our runtime
    * we remove the leadin term i.e 3* O(n) we remove the 3 it's inconsequential in the long run
    * O(n) faster than O(n^2) regardless of numerical coefficient

--------------------------
# Wenesday January 24th
--------------------------
# More sorting algos (merge sort)
--------------------------

* ## Divide and Conquer
    * Recursion and three problem sets
        * *Divide*
            * The problem into further subproblems smaller than instances of the same problem
        * *Conquer*
            * subproblems are solved recursively
        * *Combine*
            * combine subsolutions to original problem
* ## Merge sort
    * uses divide and conquer
        * ![merge sort](mergeSort.png)
        * ![pseudocode](mergeSortCode.png)
        * merge sort breaks up and array into two partitions, and then each two into two, etc. until there is only one left in each partition
        * next each element is compared against the first element of the other subarray and so on until it is reorganized in order.

![runtime](msRuntime.JPG)
* we ignore second term to get run time.
## SUMMARY
    Insertion Sort: O(n^2)
    Merge Sort: O(n log n)

    Insertion sort is **asymptotically** (ignoring constants) slower than merge sort, ti is faster for sorting small arrays in practice (due to its smaller constant factors)
    Insertion sort is used when there are sufficently small partitions from merge

--------------------------
# Friday January 26th
--------------------------
# Asymptotic Notations
--------------------------
*Asymptotic efficiency* is the worst case running time where the input size in the limit (where higher order dominates and lower order are less relevant)
### O-Notation
* characterizes an upper bound on the asymptotic behavior of the function
* *grows no faster than a certain rate* (again based on highest order)
* ex: f(x) = 7x^3 + 2x^2 + 3 ===> is O(n^3)
### Ω-notation
* Ω-notation characterizes a *lower bound* as the asyptotic  behavior of the function
* the function grows **as least as fast as** a certain rate
* also based on highesdt order
* 𝑓(𝑛) = 7𝑛3 + 100𝑛2 − 20𝑛 + 6 is Ω(𝑛3), since the highest-order term 7𝑛3 grows at least as fast as 𝑛3
### Θ-notation
* is a **tight bound**
* function grows **precisely** at a certain rate
* again based on highest order
* 𝑓(𝑛) = 7𝑛3 + 100𝑛2 − 20𝑛 + 6 is both 𝑂 𝑛3 and Ω(𝑛3), so it is also Θ(𝑛3).
* Note: If a function is both 𝑂(𝑓(𝑛)) and Ω(𝑓(𝑛)), then the function is Θ(𝑓(𝑛)).
* proof for insertion sort is **IN THE SLIDES**

##### Insertion sort
* Since INSERTION-SORT has a worst-case running time that is both 𝑂(𝑛2) and Ω(𝑛2), we can conclude that its worst-case running time is Θ(𝑛2).

#### O-notation proof and other content
**CHECK SLIDES OFR FORMAL IMAGES AND EXAMPLES OF NOTATIONS**
* ![proof](proofONotation.JPG)
* other proofs are similar to this one
* O f(n) is less than cg(n)
* Ω f(n) is more than cg(n)
* Θ f(n) is sandwiched between c1g(n) and c2g(n)

--------------------------
# Monday January 29th
--------------------------
# Asymptotic Notations
--------------------------
* *Need to be careful when using asymptotic notation to be the most precise that you can be*
* You can say: The worst-case running time for insertion sort is 𝑂(𝑛2), Ω(𝑛2), and Θ(𝑛2); all are correct. Prefer to say 𝛩(𝑛2) here, since it’s the most precise.
* You can say: The best-case running time for insertion sort is 𝑂(𝑛), Ω(𝑛), and Θ 𝑛 . Prefer 𝛩 𝑛 , again more precise.
* You cannot say: The running time for insertion sort is Θ(𝑛2), with “worst-case” omitted. Omitting the case means making a blanket statement that covers all cases, and insertion sort does not run in Θ(𝑛2) time in all cases.
* You can say: The running time for insertion sort is 𝑂(𝑛2), or that it’s Ω(𝑛), because these asymptotic running times are true for all cases.

### o-notation
* **o-notation** : characterizes a strict upper bound on the asymptotic behavior of the function
    * **O-Notation** : can be considered <=
        * 𝑓 𝑛 = 𝑂(𝑔(𝑛)): function 𝑓 𝑛 grows no faster than 𝑔(n)
    * **o-Notation** : can be considered <
        * 𝑓 𝑛 = 𝑂(𝑔(𝑛)): function 𝑓(𝑛) grows strictly slower than 𝑔(n)
    * ![littleo](littleo.JPG)
### 𝜔-notation
* **𝜔-notation** : characterizes a strict upper bound on the asymptotic behavior of the function
    * **Ω -Notation** : can be considered >=
        * 𝑓 𝑛 = 𝑂(𝑔(𝑛)): function 𝑓 𝑛 grows at least as fast as 𝑔(n)
    * **𝜔-Notation** : can be considered >
        * 𝑓 𝑛 = 𝑂(𝑔(𝑛)): function 𝑓(𝑛) grows strictly faster than 𝑔(n)
    * ![need to airdrop this image here from the phone]()
### Comparison of functions
* transitive
* symmetric
* reflexive
* transpose symmetry

### dichotomy property
* comparison between two functions f and g and the comparison of two real numbers
* ![compare](comparingNum.png)
* for real numbers either a <= b or a >= b
* **NOTE**
![dichProp.png](dichProp.png)

### Growth of functions
* ![runtime](runtimeDiag.png)
* base of a log doesnt matter asymptotically but the base of exponential and the degree of a polynomail or polylog do matter asymptotically
* ![logProps](logProps.png)
* lg = log base 2
* 2^lg(n) = n
* (sqrt(2))^lg(n) = sqrt(n)
**order of growth highest to lowest**
### Examples of asymptotic notation from highest runtime to lowest
* n! e^n 2^n n^3 n^2 nlg(n) { 2^lgn n } (sqrt(2))^lgn) lg^2(n)

--------------------------
# Wednesday January 31st
--------------------------
# Recurrence
--------------------------
![tailopez](knowledge-tai-lopez.gif)

### Conventions
* dont need to state explicit base cases
![convention1](recurrenceConventino.png)
* state asymptotic notaiton without the ceilings and floors

#### Four methods for solving recurrences
* **substitution method** : guess the soltuiuonthen use induction to prove the solution is correct
* **recursion-tree method** : Draw out a recursion tree,
determine the cost at each level, and sum them up. This is useful for understanding of the recurrence and coming up with a guess for the substitution method
* **Master Method** :  A cookbook method for solving recurrence of the form 𝑇(𝑛) = 𝑎𝑇(𝑛/𝑏) + 𝑓(𝑛), where 𝑎 > 0 and 𝑏 > 1 are constants, subject to certain conditions
* PROOFS on slides (idk if we'll need to know those he said at the beginning that we didn't
![recursionTreeMethod](recursionTreeMethod.JPG)
![masterMethod](MasterMethod.png)
![masterCookbook](masterCookbook.png)
# THIS IS TEST CONTENT ^^^^^^^
## MEMORIZE THE THREE FORMS ANALYZE THE CASE AND APPLY IT DIRECTLY
    for the master method the driving function is the f(n) term and the watershed function is the n^(logb(a)) fuction ==> in each of the cass you are comparing the watershed function to the driving function
    the final answer is givin by the f(n) however, you have to increase the polylog function by one
    if f(n) = n^2/(lg(n)) then the power of the lg function is -1 so case 2 doesnt apply and furhter the master method doesnt apply
![mmEx1](mmEx1.png)
![mmEx1](mmEx2.png)
![mmEx1](mmEx3.png)
![mmEx1](mmEx4.png)

--------------------------
# Friday Feburary 2nd
--------------------------
# Divide and Conquer Algorithms
--------------------------
* Divide the problem into one or more subproblems that are smaller instances of the same problem.
* Conquer the subproblems by solving them recursively.
* Combine the subproblem solutions to form a solution to the original problem.

### Binary Search
1. **Divide** : check middle element
2. **Conquer** : Recursivelt search a subarray (left or right)
3. **Combine** : Trivial (do nothing)
* https://www.youtube.com/watch?v=fDKIpRe8GW4&ab_channel=MichaelSambol
![binaryS](binarySearch.jpg)

### Matrix Multiplication
    matrixMultiply(A,B,C,n)
        for i = 1 to n
            for j = 1 to n
                for k = 1 to n
                    cij = cij + aik * bkj
* triple for loop is the algorithm
* Θ(n^3)
* **divide and conquer algorithm for Matrix Multiplication**
    * divide a nxn matrix into 2x2 matrix of (n/2) x (n/2) submatrices:
    * ![matmult](MatrixMult.png)
    * Recurrence: T(n) = 8 T(n/2) + /theta(1)
    * because of 8 submatrix multiplications and submatrix size of n/2 and adding 1 for dividing matries
    * with the **master method** using case 1 we know the runtime is /theta(n^3)
* **Strassen's Algorithm**
    * *idea* : reduce submatrix multiplications by using more submatrix additions because thye cost less compute power
    * similar to --> x^2 + y^2 = (x-y)(x+y)
    * Recurrence: T(n) = 7 T(n/2) + /theta(n^2)
    * watershed = n^2.807 f(n) = n^2
    * bigtheta(n^2.807)
---------------
# **Monday Feburary 5th**
---------------
# **Randomized Algorithms**
---------------

### The hiring problem
* Hiring a new person you are given one candidate each day for a total of *n* days (*n candidates*)
* If you hire you must fire the current person
* ![cost](costCand.png)
* strategy is to hire the best candidate seen so far that is better than the current employee which you must fire
* becaue you must have someone hired you will hire the first candidate interviewied.
* ![hireCode](hirePsuedo.png)
    * There are n candidates total and you hire m of them (m <= n)
    * O(ci(n) + ch(m))
        * The **total interview** cost ci(n) is fixed (because n is)
        * **hiring cost** is dependent on m
        * ![hireEx](hireEx.png)
        * You take the higher level interviewee.
    * **Worst case**
        * In reverse order so you hire all of the people (ch(n))
    * **Probabilistic Analysis**
        * make assumptions about the distributions of the input by using the average over all possible inputs (**average-case run time**)
        * all n! permutations of their ranks (1,2,3,....,4) are equally likely
        * ![pa](pa.png)
    * **Indicator Random Variable**
        * Provides a convenient method for converting between Probabilities(Pr) and expectations (E).
        * ![ira](iraProof.png)
    * **Coin Flip Problem**
        * ![coinFlip](coinFlip.png)
    * **Back to the Hiring Problem**
        * **What is the probability that candidate i is hired?**
            * For candidate i = 1,2,....,n define Xi = I{candidate is hired} as an indicator random variable
            * E[Xi] = Pr{Candidide i is hired} = 1/i
            * this means 10 candidates => 1/10 chance of gettign hired
            * The first i candidates are all equally likely to be the best candidate
        * ![hiringProb](hiringProbSummation.JPG)
    * **From Probalisitic Analysis to Randomized Algorithm**
        * **Probablisitc Analysis**
            * Assumesk knowledge of distribution input
        * **Randomized Algorithm**
            * Uses randomization to enforce a distribution on the inputs inside the algorithm instead of in the input
            * for psuedo start with randomly permute (change the order) the list of candidates
            * random permutations ensure that it is not the worst case
    *![vocab](analysisVocab.png)

---------------
# **Wednesday Feburary 7th**
---------------
# **Quick Sort**
---------------
### Mood for this lecture
 ![zukc](zuck.gif)
### We grilling some mf meats

### Quciksort
* **Quicksort** is a sorting algo that uses divide and conquer
* This 4 minute video prob better than the whole lecture
https://www.youtube.com/watch?v=Hoixgm4-P4M&ab_channel=MichaelSambol
* Quicksort uses a **PARTITION** that selects a **pivot** value **THE LAST VALUE** and rearranges the elements on either side of the partition recursively
    * ![quicksort](quicksort.png)
* **Worst Case Runtime**
    * The partitioning is **completely unbalanced**
    * each partition has 0 on one side and n-1 elements on the other
    * ![quickWorst](quickWorst.png)
    * /theta(n^2)
* **Best Case Runtime**
    * The partitioning is **completely balanced**
    * each partiion has roughly n/2 elements
    * ![quickMM](quickMM.png)
    * /theta(nlgn) ---> Case #2 of the master method
* **Average Case Runtime**
* **AVERAGE**
    * much closer to the best case
    * ![quickAvg](quickAvg.png)
    * Any split of **constant proportionality** yields a runnign time of O(nlgn) the ratio only affects the constant which has no affect asymptotically i.e. /theta

### Randomized Quicksort
* To enforce an input distribution, we can again randomize the algorithm, and get the same expected running time 𝑂 𝑛 lg 𝑛

---------------
# **Friday Feburary 9th**
---------------
# **Heapsort**
---------------
    Mood for todays heaps
![max](maxV.gif)

### Heap
* **Binary Heap** data structure is an array object which can also be viewed as *(nearly) complete binary tree*
    * Each node of the tree corresponds to an element of the array
    * It is filled on all levels except the lowest level
    * lowest level is filled from left to right
    * ![heap.png](heap.png)
* **Indexes**
    * Parent(i) = i//2
    * Left(i) = 2i
    * Right(i) = 2i+1
* **Array View**
    * Array is represneted as A[1:n] with n elements
* **Heap View**
    * Heap has an attribute A.heap-size which repreenst the number of valid elements
    * 0 < A.heap-size <= n
* **Height**
    * for mostly complete ---> Θ(lg 𝑛)
    * ![macHeapp](macHeapp.jpg)
* **Mn Max Heaps**
    * ![minmax.jpg](minmax.png)
* **Max Heapify**
    * Recursive procedure that maitains the amx-heap rpoperty for a heap A on index i by:
        * Binary trees rooated at Left(i) and right(i) the two childern off of the root
        * But A[i] the root may be smaller than its children thus violating the max heap property
        * ![heapify](heapify.JPG)
    * ![maaax.jpg](maaax.png)
    * **Runtime**
        * O (lgn)
        * *because it has a height of h and h =lgn but its big O because you might not always go down to a leaf*
![](mhRT.png)
* **Building a Heap**
    * **Max Heapify** builds a heap from the bottom up
    * ![buildHepa](buildHeap.png)
    * You start at the n//2 index because that is where the last parent node would be the higher indexes wouldnt have children (in this scenario index 5)
### Heap Sort
* ![heapsory](heapsory.png)

### Why is heapsort correct?
* ![heapsory](heapsortCorrect.png)
---------------
# **Monday Feburary 12th**
---------------
# **Started class with heapsort however, he hasnt posted the following slides**
---------------
###### *Mood today with a chiefs superbowl win*
![patM](patM.gif)
* ### Heapsort info
    * *Watch his video below for heapsort*
    * https://www.youtube.com/watch?v=2DmK_H7IdTo&ab_channel=MichaelSambol
    * ![heapRun](heapRuntime.JPG)
### Comparing Sorting Algos
* ![comparRuntime](compareRuntime.png)
### Sorting in Place
* It is called in place if the sorting algo is done *directly on input array*
    * Most in place sorting algos use Θ(1) of additional space making them *space efficient*
* **Out of place sorting**
    * Not sorted in place
    * Θ(n) additional space to sort an array of n elements
* ![sortPlaces](sortPlaces.png)

### Prioriy Queues
* Another popular application of heap is to use it as efficient priority queue, which is a data structure for maintaining a set 𝑆 of elements, each with an associated value called a key
* Come in two forms
    * Max-priority queues
    * Min-priority queues
### Max priorirty queue
* supports
*Underflow means that we check if the heap is empty*
    * max -> returns element with largest key
        * Runtime: Θ(1)
        * ![maxHeapMax](maxHeapMax.png)
    * extract-max -> removes and returns item with largest key
        * Running time: 𝑂(lg(𝑛)) , since MAX-HEAPIFY take 𝑂(lg(𝑛)) time
        * ![extract](maxHeapExtract.png)
    * increase-key -> increase value of element x's key to k with k >= x
        * Running time: 𝑂(lg(𝑛)) , since the height of heap is 𝑂(lg(𝑛)) and assuming finding element 𝑥 in the array takes Θ(1) time
        * ![increase](increaseKey.png)
        * ![increase](IOKey.png)
    * insert -> inserts element with key in the set
        * Running time: 𝑂 lg 𝑛 , since MAX-HEAP-INCREASE- KEY takes 𝑂 lg 𝑛 time
        * ![maxhi](maxHeapInc.png)
![maxheapsummary](maxHeapSummary.png)

### Scheduling jobs on a computer shared among multiple users.
* The max-priority queue keeps track of the jobs to be executed and their relative priorities.
* When a job is finished, the scheduler selects the highest-priority job from among those pending by calling EXTRACT-MAX.
* When a job has been pending for a long time, its priority can be increased by calling INCREASE-KEY.
* The scheduler can add a new job to the queue at any time by calling INSERT

---------------
# **Wednesday Feburary 14th**
---------------
# **Elementary Data Sets**
---------------
### My mood for learnign about FIFO today
![](fifoHappy.gif)

### Sets
* In CS sets can grow, shrink, and be manipulated
* Operations
    * Can have different types of operations such as:
    * insert, delete, search -> Sets with these operations are called **Dictionaries**
    * finding max and min values.
### Dynamic Sets
* Key
    * identifier
    * ex: student id
* Satellite Data
    * carried around
    * ex: name, gender, age
* Other data
    * ex; pointers to other objects
* Some dynamic sets assume there is a *total order* based numbers or alphabetic order often
    * This allows us to defin a min element and a follwoing element
* Data Structures
    * Arrays & matrices
    * Stacks & queues
    * Linked lists
    * Skip lists
    * (Search) Trees
    * Hash tables
    * Disjoint sets
    * Graphs
### Dynamic Set operations
* Two categories
    * Queries
        * return info about set
    * Modifying Operations
        * change info about the set
* COmmon set operations
    * search, insert, delete
    * min, max, successor, predecessor
* Time complexity
    * **If array is not sorted**
        * INSERT and DELETE take Θ(1) time
        * SEARCH, MINIMUM, MAXIMUM) can take 𝑂(𝑛) time in the worst case
    * **If array is sorted**
        * e.g., MINIMUM, MAXIMUM) take Θ(1) time
        * SEARCH takes 𝑂 lg 𝑛 using binary search, but INSERT and DELETE can take 𝑂(𝑛) time in the worst case
### Arrays
* A contingious sequence of memory space (i.e pandas in pyhton)
    * ex [1,2,3]
    * Given an array index 𝑖, it takes Θ(1) time to access the corresponding array element 𝐴[𝑖]
### Matrices
* 2D+ array
[[1,2,3]
[4,5,6]]
* row major: 1,2,3,4,5,6
* column major: 1,4,2,5,3,6
* *Single vs Multiple Array Representation*
    * *single array* is more efficient on modern computer systems
    * *multiple array* can be more flexible when rows and columns have different lengths
    * takes Θ(1) time to access the corresponding matrix element 𝑀[𝑖, 𝑗]

### Stacks and Queues
* **Stack**
    * LIFO
    * Insert: Push
    * Delete: Pop
        * can only access teh top of the stack
    * ![silylStack](stackTop.png)
    * ![silylStack](stackPs.png)
* **Queue**
    * FIFO
    * Insert: Enqueue
    * Delte: Dequeue
    * Q.head: start of the queue
        * element of be dequeued
    * Q.tail : end of the queue
        * index of new lemenet to be enqeues
    * Q.size : capactiy of the queue + 1
    * ![](queueHT.png)
    * ![](headTails.png)
    * ![](exercise.png)
    * To check doe for underflow and overflow
**For Enqueue**
if (Q.head == Q.tail + 1) or (Q.head ==1 and Q.tail == Q.size):
    error "overflow"

**For Dequeue**
if Q.head == Q.tail:
    error "underflow"

---------------
# **Friday Feburary 16th**
---------------
# **Data Structures**
---------------

### Linked Lists
* Data strcutue for dynamic sets in which elemnts are arranged in a linear order (as in an array)
    * For an *array* the linear order is determined by array indicues
    * for  *linked list* the linear order is determined by pointers
    * can be sorted or unsorted
    * can be doubly or single linked list
### Singly Linked Lists
* Each element has a pointer to the net elemnet but none to the previous
### Doubly Linked Lists
* Pointer to both next and previous elemnets
* 𝐿, each element 𝑥 has a 𝑘𝑒𝑦 attribute and two pointer attributes: 𝑛𝑒𝑥𝑡, 𝑝𝑟𝑒𝑣
* x.next points to next if == NIL its the last value
* x.prev points to previous if == NIL its the first value
* L.Head poiints ot first element if == NIL lsit is empty

# ALL THE FOLLOWING EXAMPLES ARE WITH DOUBLY LINKED LISTS

### Searching a doubly linked list
    List_search(L,k)
        x = L.HEAD
        while x != NIL and x.key != k
            x = x.next
        return x
* Θ(n) for worst time

### Adding to the front of a doubly linked list
    List_prepend(L,x):
        x.next = L.Head
        x.prev = NIL
        if L.Head != NIL
            L.head.prev = x
        L.head = x
* Θ(1) for time

### Inserting into a doubly linked list
    List_Insert(x,y)
        x.next = y.next
        x.prev = y
        if y.next != NIL
            y.next.prev = x
        y.next = x
* Θ(1) for time

### Deleting from a doubly Linked List
    List_Delete(L,x)
        if x.prev != NIL
            x.prev.next = x.next
        else
            L.head = x.next
        if x.next!= NIL
            x.next.prev = x.prev
* Θ(1) for time

### Sentinels
* A dummy element in a data structure that allows us to simply boundry conditions
* In the context of a linked list a sentinel is L.nil that represents NIL but has all other attributes of elements in the list
* references to NIL are replaces with sentinel L.nil
* **Turns the regular doubly linked listed into a cirecular doubly linked list (with a sentinel) where L.nil is between head and tail of the list.
    * ![](sentinel.png)
### How do Snetinels simplify code?
* ![SimplyifyJobsCode](sentSimp.png)
* ![SimplyifyJobsCode](sentSimp2.png)
### When shoudl we use them?
* Pro
    * Simplify code
    * speed up code by constant factor
* Cons
    * When there are small lists the extra storage used by sentiels is significant wasted memory

### Arrays vs Linked List
* Both dictionary like
* Arrays are easier to implement, fixed length
* Linked Lists are more flexible, flexible length
* ![compare](compare1624.png)
* ![compare](compare021624.png)

---------------
# **Monday Feburary 16th**
---------------
# **Binary Search Trees**
---------------

### Tree
* Data structure for dynamic sets in which objects are not in a linear relationship like linked list
* key attribute and pointer attributes to other nodes
* **Two Types**
    * binary (at most 2 childer)
    * unbounded (no limit of kids nick cannon style)
    **Binary Tree Diagram**
    * ![binaryTree](binaryTree.png)
    **Unbound Binary Tree Diagram**
    * ![unboundbinaryTree](unboundBinaryTree.png)
    * **Depth**
        * length of the simple path from root to node
    * **height*
        * length of the longest simple path from the node to a leaf
### Binary Search Tree
* Satisfies:
    * if x is a node and if y is a node in the left subtree of x then y.key <= x.key
    * if x is a node and if y is a node in the right subtree of x then y.key >= x.key
* ![](exBST.png)
### In order Tree walk
* ![](inorder.png)
## Ex tree used for walks
* ![](exWalk.png)
### In order Tree walk
* left subtree, node, right subtree
* Output: 2,5,5,6,7,8
### Preorder Tree Walk
* Node, left subtree, right subtree
* Output: 6, 5, 2, 5, 7, 8
### Postorder Tree Walk
* left subtree, righ subtree, node
* Output: 2, 5, 5, 8, 7, 6
### Tree Searching
* ![searching](treeSearch.png)
### Tree minimum and Tree Maximum
* ![minMax](treeMinMax.png)
### Successor and Predecessor
* **Successor**
**RUnning time of O(h)
    * next node visited in an inorder walk
    * !(successor)[treeSuccessor.png]
    * **Two Cases**
        * Case 1
            * If the right subtree of 𝑥 is not empty, then the successor is the leftmost (smallest) node in 𝑥’s right subtree
            * simpel path down the tree
            * !(succ1)[treeSuccCase1.png]
        * Case 2
            * If the right subtree of 𝑥 is empty, then the successor is the lowest ancestor of 𝑥 whose left child is also an ancestor of 𝑥 (i.e., climb up the tree and stop after the first right turn)
            * Simple path up the tree
            * !(succ2)[treeSuccCase2.png]
* **Predecessor**
    * preceding node visited in an inorder walk
    * ![](predecessor.jpg)

---------------
# **Friday Feburary 23rd **
---------------
# **Binary Search Tree**
---------------

### Insert
* Inserts a new node z into tree T by tracing a simple path down the root based on the value of z.key and places z in an appropriate leaf position to maintain the binary-saerch-tree property
* running time O(h)
* ![insertBST](insertBST.png)
* ![insertPS](insertPS.png)

### Delete
* Tree delete procedure deltees a node z from tree T.
* Three Cases:
    * Case 1
        * If node z has no left child then repalce z by its right child (which could be NIL, meaning that z has no children)
        * ![BSTDel1](BSTDel1.png)
    * Case 2
        * If node z has a left child but no right chhild then replace z by its left child.
        * ![BSTDel2](BSTDel2.png)
    * Case 3
        * if node z has both a aleft child and a right child, then find z's successor y ( which must lie iin z's right subtree and has no left child)
        * **Case 3.1:** if y is z's right child then repalce z by y. In this case, y adopts z's orgiinal left subtree as its own left subtree and y's orginal subtree is unchanged.
            * ![BSTDel3](BSTDel3.png)
        * **Case 3.2:** if y is not z's right child, then first replace y by its own right child x and then replace z by y. In this case y adopts z's original elft and right subtrees as its own left and right subtrees
            * ![BSTDel32](BSTDel32.png)
    #### Psuedo code
    * ![BSTDelPs](BSTDelPs.png)
    * if statement 1 is case 1
    * elseif statement is case 2
    * else is case 3
        * last three liens are case 3.1
        * entire if block in last else is case 3.2
    #### Transplant
    * replaces subbtree rooted at node u with subtree rooted at node v
    * makes new parent node
    * ![transplant](transplant.png)

    ##### Run times
    * Tree delete O(h), each line is /theta(1) even transplant
    * tree minimum (line five) takes O(h)
    * BST Operations
        * all are O(h) runtime where height is h
        * **Best case** allmost balanced  Θ lg 𝑛
        * **Word Case** unbalanced like a line ℎ = Θ n
### Balanced BSTs
* AVL Tree
    * each node the heights of its two children subtrees differ by at most 1
* Red Black Tree:
    * each node has an extra "color" bit ("red" or "black") used to re-organize the tree to ensure its approx balance
    * ![balanceBST](balanceBST.png)

#### Rotation
* Importatn operation used by balanced BSTs to maintain the follow properties:
    * the height of the tree is always h = Θ lg 𝑛
    * the binary search tree property
    * ![BSTrotate](BSTrotate.png)
    * ![rotatePS](rotatePS.png)
### Working of balanced BSTs
* The query operations wirh the same with ordinary bST (search, min, successor)
* The modifying operation (insert, dlete) need to be augmented with roations to maintain desired properties.
* someitmes need multiple rotations.
---------------
# **Wednesday Feburary 21st**
---------------
# **Skip Lists**
---------------
* Randomzied data structures that are built upon sorted linked lists but allow INSERT, DELETE, and SEARCH operations done in O(lg(n)) average time
### Skip List Alternatives
* Sorted Arrays
* Binary Search Trees(O(Logn))
* AVL Trees(O(lgn))
* Treaps
*![](skipListAlt.png)
### Why choose skip list over other data structures?
* More Dynamic than Sorted Arrays
* Better Memory Efficiency than Tree-like Structures
* Implementation with Concurrency and Parallelism
* Simple Implementation
* Approximation Queries are faster

### Search in linked listes
* takes O(n) time because you may have to go throguh the whole list

### How ro speed up search with skip lists
* Skip lists speed up search by mainting multiple lists and some lemenets appear in both connected by vertical links
* ![skipListSearch](skipListSearch.png)

### Time complexity for searching throguh a skip list
* ![twoLists](twoLists.png)
* In the general case
* ![generalCase](generalList.png)

### Dealing with Insert and Delete
* INSERT and DELETE may disturb the ideal structure over time
* handles this by maintaining roughly the list

### Delete in skip lists
* Delete(x): when deleting an element x, delete it from all lists containing it

## Inserting in skip lists
* always insert it into the bottom list by using search(x.key)
* ![insertSkipList](insertSkipList.png)
---------------
# **Wednesday Feburary 28th**
---------------
# **Hashing and Hash Tables**
---------------

### Hash Table
* A hash table is a data struture that supports dictionary operations (INSERT, DELTE, SEARCH) for a dynamic set
* Compared to other data satructures
    * Hash tables peform extremely ell in practice
    * pythiogn dictionaris are built using has tables
    * used in crypto
* We assume:
    * Each object has a unique key (student id) and satellite data (other records)

### Direct Address Tables
* **Direct Addressing** :
    * Simple technique that works well when the unvierse of all possibel keys is resonably small <= m
    * in a **direct address table** each slot corresponds to  a key in the unvierse
    * ![directAddressTable.png](directAddressTable.png)
* IN a direct address table all dictionary options (insert, delete, search) are trivial to implement and fast /theta(1) time.
    * However, with ginormous data sets this can be impractical to store
### Hash Tables
* more efficient when the set K of actual keys is much samller thatn the universe U of all possible keys
* ![hashTable.pn](hashTable.png)
### Collision
* collision happens if two keys hash to the same slot in a hash table
    * 2 ways to resolve conflicts:
        * hash function/scheme: tries to avoid )or minimize the number of collisions by choosing a suitable hash function h)
        * Collision resolution: resolves collsiions when they do occru
### Hash Function
* "ideal" hash fucntion h hasehs each possible input (k element of U) to a hash value H(k) that has the folowoiign properties:
    * uniform random: h(k) is chosen randomly and uniformly in the range {0,1, .... , m-1 }
    * Indpenedent: h(k) is chosen indepently for different k values
### Independent uniform Hashing
* the *ideal* hash funuction
    * hard to implement
    * practical hash functions approx to this ideal
### Hashing Schemes
* static hashing
    * division method
    * multiplication method
* randhom hasing
    * universal hasing
* Prefaect hasing
    * simple scheme
    * two level scheme
### Static hashing
* Static hashing uses a single, fixed hash function ℎ. Thus, the same input 𝑘 will be hashed to the same slot when static hashing is applied multiple times
* Division method
    * ![divMethod](divMethod.png)
* multiplication method
    * ![multMethod](multMethod.png)

### Collisions in Static hashing
* Static Hashing is vulnerable to a worst case behavior created by malicious adversayr who could choose a set of keys that all hash to the same slot cerating a lot of collisions
* ![hackCollis](hackCollis.png)

### Random Hashing
* Introduce ranomization in hash functions to achieve good expected # of collisions without assuming unifrom elements
* In random hasing instead of using a fixed hash function h, a family H = {h1, h2, ... } of hash functions is used.
    * Before executing a sequence of operations (insert, delete, search), a particular hash function ( h elemetn of H) is sleected at random from the fam

### Universal Hashing
* Special case of random hasing
* if it satisfies
    * for any distinc keys k1 and k2 the nuber of hash fuctions in H that hash them to the same slos is |H|/m.
    * in other words we choose a member of H, h at random with probability h(k1) = h(k2) is <= 1/m
    * In universal hashing with n elemnets for a given elemetn x # of collisions (or # of elmetns that has to the same slto as x)
        8 in expectation /theta(a) where a = n/m is the load factor (avg number of elements per slot)

##### Example of Univeral Hashing
* ![exUnHash.png](exUnHash.png)

---------------
# **Friday March 1st**
---------------
# **Hashing Continued Lecture slides 8**
---------------

### Perfect Hashing
* gauruntees zero collisions
* only works for a static set of n elements
* thus the hash functions need to be reconstructued if the set of elements is changed
* two types of perfect hasing schemes both rely on universal hashing
    * simple scheme : m = \theta(n^2)
    * two level sceme : m = \theta(n)

### Simple Scheme
* perfroms the following procedure to gauruntee no collision fora set of n elements
* ![simpleScheme.png](simpleScheme.png)
* **Theorem** : Using simple perfect hashing scheme with m = n^2 the success probabiity of each trial is >= 1/2

### Two-level Scheme:
* The <ins> two level perfect hasing </ins> scheme uses *two levels o hash tables* with *universal hashing* at both levels
* **First level** : a hash table of size(m) = n <ins> there may be collisions </ins>
* **Second Level** : hash tables of varying sizes for each slot of first level <ins> gaurantees no collisions </ins>
* ![twoLevel.png](twoLevel.png)

### compare hash schemes
* ![compareHash.png](compareHash.png)

### Collision Resolution
* resolves for things hashed to same slot
    * chaining
    * open addressing

### Chaining
* resolves collision by using a *linked list* for all elments hashed to the same slot
* ![chaining.png](chaining.png)

### Insert and Delete
* in a hash table with **chaining** INSERT, DELEE, all take \theta(1)
* **same as PREPEND and DETELE** operations on a linked list

### Search
* In a hash table wit hn elements and *chaining* the <ins>SEARCH</search> element takes
* **WORST CASE**
    * \theta(n)
    * under static hashing (all n elements hash to the same slot)
* **AVERAGE CASE**
    * \theta(1 + 𝛼)
    * Under static hashing (assuming elements chosen uniformly), or under universal hashing (without assumption on elements).
    * 𝛼 = 𝑛/𝑚 is load factor (“< 1”, “= 1”, and “> 1” are all possible).
    * Θ(1) time for applying hash function and accessing slot.
    * Θ(𝛼) time for searching through the elements
* **THUS**
    * if a = O(1) or equivalently n = O(m) the average/expected SEARCH time is \theta(1)
### Open Addressing
* *stores all of the elments in the hash table itself*
    * each entry of a table has an element or NIL
    * table could fill up i.e. load factor a = 1
* **collisions** are handled by successively probing the different slots
    * INSERT -> probe until mpty slot is found and store new element
    * SEARCH -> probe until elmenet is found (success) or not (fail)
* ![probeSequence](probeSequence.png)
* check slides to see the sequence CHECK BUDDY ACTUALLY STUDY

### Probe Sequence
* **INSERT**
    * follows the probe sequence until an **empty slot is found (for inserting the element)** or **realizing the table is full** (cant insert)
* **SEARCH**
    * follos the same probe sequence until **success** (key is found) or **failure** ( empty slot is found or all positions are probed**
    * ![probePsuedo.png](probePsuedo.png)

---------------
# **Monday March 4th**
---------------
# **Hashing Continued Lecture slides 8**
---------------

### Probing Strategies
* defines the hash function h(k,i) for key k and probe number i
* two types **Linear probing** and **Double Hashing**

### Linear Probing
    Uses the hash function:
    h(k,i) = (h1(k) + i)mod(m)
    where h1(k) is an auxiliary hash function
* ![linearProbe.png](linearProbe.png)
* **Pros**
    * easy to implement
    * good cache performance (accessed sequentilaly which are stored in the same cache block
* **Cons**
    * primary clustering : long runs occupied slots build up increaseing aerage time. Moreover, the long runs of occupied slots tend to get longer

### Double Hashing
    Uses the hash function
    h(k,i) = (h1(k) + i*h2(k))mod(m)
    where h1(k) and h2(k) are the auxiliary hash functions
* ![doubleHash.png](doubleHash.png)
* ![dhEx.png](dhEx.png)
* Able to insert in position 9 based on the double hashing
#### For each key K you start with i = 0 then incremenet for each key
#### i is the attempt for that key (i.e. for a hypothetical key 13 you start with key 0,1,2,.... then it finds a spot now for a new key 45 i = 0 then i =1 ,2,3,.....

### Anlaysis of Open addressing
* **Uniform Hashing**
    * the prove seuqnce of the key is equially likely among all permutations (0,1,....,m-1)
        * *this is and ideal assuption**
* *Load factor 𝛼 = 𝑛/𝑚 < 1*
    * since no extra storage is used outside of the table # of elements (n) < # slots (m)
    * proportion of occupied slots in the hash table

### (Unsuccessful) Search
* ![unSearch.png](unSearch.png)

### Other Operations
* a **successful search** takes *less time*
* **INSERT** takes the *same time* as *unsuccessful SEARCH* (because it inserts after finding an empty slot*
* **DELETE** is tricky
    * simply deleted is \theta(1) time
    * but after makign the slot NIL may prevent searching for another key whos prove sequcne containst that slot
    * Alright, let's imagine you have a toy box, and you want to keep it organized. In our case, the toy box is like a storage space for things called elements. Now, sometimes you take out a toy and put it back in the box. But what if the box is full, and you can't find a space for your toy?
    * One way to handle this is by marking a spot in the box as "DELETED" when you take a toy out. This way, you remember that there was something there before. But, if you do this, searching for toys becomes a bit tricky because you have to check these "DELETED" spots too.
    * Now, there's another clever way to handle this without marking spots. Imagine you have a special trick to find a free spot without having to mark it. It's like a game – you can still put your toy in the box without leaving a mark, and when you look for it later, you'll know exactly where it is.
    * But, here's the thing: this trick makes searching for toys a bit different. The time it takes to find a toy doesn't depend on how full the box is anymore. It's like playing hide and seek with rules that stay the same, no matter how many toys are in the box.
    * So, when computer programs organize information, they sometimes use similar ideas to keep things neat and find them quickly. It's like having different strategies for keeping your toy box tidy!

### Compare Collision Resolutions
* ![compareCollis.png](compareCollis.png)


# CONTENT AFTER THE MIDTERM
