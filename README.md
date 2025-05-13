# cse344-homework-4--v1-threads-and-system-v-semaphores-solved
**TO GET THIS SOLUTION VISIT:** [CSE344 Homework #4 –v1 Threads and System V semaphores Solved](https://www.ankitcodinghub.com/product/cse344-homework-4-v1-threads-and-system-v-semaphores-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;93945&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;0&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;0&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;0\/5 - (0 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CSE344 Homework #4 –v1 Threads and System V semaphores Solved&quot;,&quot;width&quot;:&quot;0&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 0px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            <span class="kksr-muted">Rate this product</span>
    </div>
    </div>
<div class="page" title="Page 1">
<div class="layoutArea">
<div class="column">
v1 Threads and System V semaphores

</div>
</div>
<div class="layoutArea">
<div class="column">
Let’s keep it simple and abstract. There is one supplier thread and multiple consumer threads. The supplier brings materials, one by one. And the consumers consume them, two by two. That’s it. Each actor will be modeled by its own thread.

<pre>                   Example: ./hw4 -C 10 -N 5 -F inputfilePath
</pre>
Input File (ASCII)

It will contain in total NxC times the character ‘1’ and NxC times the character ‘2’ in an arbitrary order. This file will be provided externally as input (i.e. assume it’s there). Each character in the file will correspond to a type of material. ‘1’ will correspond to the first material, and ‘2’ will correspond to the second material.

Supplier x 1

There will be only one supplier thread. It will read the input file’s contents, one character at a time and output a message concerning its activity. For every character/material read from the file, it will augment/post a semaphore representing its amount. If it reads a ‘1’ it will post the semaphore representing the amount of ‘1’s read so far, and if it reads a ‘2’ it will post the semaphore representing the amount of ‘2’s read so far. It will terminate once it reaches the end of the file. The supplier will be a detached thread. You will have no other variables for keeping count of the delivered materials.

Output examples: // Before delivery

<pre>Supplier: read from input a ‘1’. Current amounts: 0 x ‘1’, 0 x ‘2’.
</pre>
// After delivery

<pre>Supplier: delivered a ‘1’. Post-delivery amounts: 1 x ‘1’, 0 x ‘2’.
</pre>
// At EOF

<pre>The Supplier has left.
</pre>
Consumers x C

Each consumer will have its own thread (not detached). Its task is to loop N times. At each iteration it will take/remove one ‘1’ and one ‘2’ by reducing the corresponding semaphores’ values. Careful, if either is not available (e.g. if there is no ‘1’ or ‘2’) then it will not take the other. In other words, it will either take two items (one ‘1’ and one ‘2’) or wait until two (one ‘1’ and one ‘2’) are available. This way each consumer will consume in total exactly N x ‘1’s and N x ‘2’s.

Output examples:

//Before consuming (i denotes the integer id of the consumer 0 to C-1, j is the iteration number,

0 to N-1)

Consumer-i at iteration j (waiting). Current amounts: 8 x ‘1’, 12 x ‘2’.

//After consuming

Consumer-i at iteration j (consumed). Post-consumption amounts: 7 x ‘1’, 11 x ‘2’.

</div>
</div>
<div class="layoutArea">
<div class="column">
April 29th, 2022

</div>
</div>
</div>
<div class="page" title="Page 2">
<div class="layoutArea">
<div class="column">
// After consuming N times

<pre>Consumer-i has left.
</pre>
Restrictions and requirements

– C &gt; 4 (integer)

– N &gt; 1 (integer)

– All threads must run concurrently.

– inputFilePath: relative or absolute

– There will be only one process.

– Don’t use more than 2 semaphores.

– Don’t create additional threads besides a supplier and C consumers.

– You must use only System V semaphores for synchronization.

– All output will be written to STDOUT without buffering (each line will begin with a timestamp).

– In case of SIGINT, all processes and threads will terminate gracefully, closing all open files and freeing all allocated resources.

Evaluation

Your submission will be evaluated with multiple (valid) input files and various (valid and invalid) input parameters. The assistants will try hard to cause a deadlock. Take the required precautions.

Grading (the rules have been updated!)

1) Compilation error: grade set to 1; if the error is resolved during the demo, then evaluation continues.

2) Compilation warning (with respect to the -Wall flag); -1 for every warning until 10. -20 points if there are more than 10 warnings; no chance of correction at demo.

3) No makefile, makefile without -Wall, makefile without “make clean”: -30

4) No pdf report submitted (or submitted but insufficient, e.g. 3 lines of text with no design explanation, etc), file formats other than pdf: -20

5) The program crashes/locks or produces wrong output with valid input: -100

6) Poor synchronization (e.g., sleeps, busy waiting, timed waits, etc): -100

7) The program doesn’t satisfy a requirement or violates a restriction: -100

8) Presence of memory leak (regardless of amount – checked with valgrind) -30

9) -15 for every day of late submission.

10) In case of an arbitrary and fatal error, exit by printing to STDERR a nicely formatted informative message. Otherwise: -10

11) If you don’t cleanup after children processes and/or leave zombies: -50

Is my homework submission valid?

It is valid if given a correct input file, at least one consumer consumes a ‘1’ and a ‘2’.

</div>
</div>
</div>
