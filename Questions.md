#**Sharath Reddy Vontari (shvo9452)**
##SOLUTIONS
####Question 1
- The broken program doesn't work because the queue object is not synchronized. 
- Therefore all the producer threads are running on that single queue object at the same time and
the count variable is updated by the threads at the same time. 
- Due to this the value of count reaches 20 and the program control exits the code. 
Therefore only limited products like 15- 20 are produced and the same are consumed. 
After which the queue becomes empty and the message called queue empty is repeatedly printed. 
- Hence, ultimately the threads end up in a state of livelock.

####Question 2
- The difference between broken and broken2 is that the methods in the production line java file are synchronized in broken2. 
- Synchronizing these methods was not enough because synchronizing the methods will allow
the purpose of each thread passing through the method only once. 
- But the required purpose which is applying a synchronise block for the queue object is not satisfied. 
- This means the process of producing all the 200 products and consuming all of them is not fully done, it is only partially done 
and therefore this explains the partial output of some of the product id's missing.

####Question 3
- To generate an output similar to that in the example_output.txt, 
- I have synchronised the queue object in both the producer and consumer files. 
- This ensures that only one thread can access the object queue, at a given time while the program control 
runs through the critical section that is the run() method. 
- This ensures that all the 200 products are produced and all of them are consumed.
- This is done from the concept of synchronize block.
