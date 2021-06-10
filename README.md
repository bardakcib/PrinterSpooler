# PrinterSpooler
## Printer spooler simulation Multi-thread and Multi-process versions written in C

![](https://github.com/bardakcib/resources/blob/main/badges/built-with-love.svg)
![](https://github.com/bardakcib/resources/blob/main/badges/made-with-c.svg)
![](https://github.com/bardakcib/resources/blob/main/badges/vscode.svg)


## MULTI-THREAD SPOOLER

Tested with [Dev-C++ (orwell)](https://sourceforge.net/projects/orwelldevcpp/) / Windows 

* The printer will run as a thread, which processes incoming print jobs as long as it has free space in its buffer and it can print 1Kb in 0.01 actual seconds.
* Size of the printing job will be determined randomly from 50 Kb to 512 Kb.
* The requests and buffer allocation will be synchronized correctly by using semaphores.
* Initially, the printer buffer will be completely free, which means you will start with a semaphore value of the size of the buffer.
* The randomly created jobs will enqueue if there is enough buffer to print their job; otherwise they will wait until some resource becomes available
* For this design, you have to maintain a queue also. No job can start printing until the one enqueued right before it completes.


## MULTI-PROCESS SPOOLER

Tested with [Onlinegdb](https://www.onlinegdb.com/online_c_compiler)

* Use processes instead of threads.



## References

* [Threads vs Processes](https://www.backblaze.com/blog/whats-the-diff-programs-processes-and-threads/)
* [A Simple Queue in C](https://www.journaldev.com/36220/queue-in-c)
* [Nanosleep in C](https://www.linuxquestions.org/questions/programming-9/can-someone-give-me-the-example-of-the-simplest-usage-of-nanosleep-in-c-4175429688/)
* [Share memory between Processes](https://stackoverflow.com/questions/13274786/how-to-share-memory-between-processes-created-by-fork/63408673#63408673)
* [Benchmarking](https://www.bitsnbites.eu/benchmarking-os-primitives/)
* [Using fork in C](https://www.geeksforgeeks.org/using-fork-produce-1-parent-3-child-processes/)
* [Threads vs Process performance](https://stackoverflow.com/questions/807506/threads-vs-processes-in-linux)
* [POSIX semaphores in C](https://man7.org/linux/man-pages/man7/sem_overview.7.html)
