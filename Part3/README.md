# Reasons for concurrency and parallelism


To complete this exercise you will have to use git. Create one or several commits that adds answers to the following questions and push it to your groups repository to complete the task.

When answering the questions, remember to use all the resources at your disposal. Asking the internet isn't a form of "cheating", it's a way of learning.

 ### What is concurrency? What is parallelism? What's the difference?
> "Concurrency is when two or more tasks can start, run, and complete in overlapping time periods. It doesn't necessarily mean they'll ever both be running at the same instant. For example, multitasking on a single-core machine.Parallelism is when tasks literally run at the same time, e.g., on a multicore processor."

> // Kommentar: Skiller mellom mulighet og faktsik utførelse.
 
 ### Why have machines become increasingly multicore in the past decade?
 > "The trend towards multiple cores is an engineering approach that helps the CPU designers avoid the power consumption problem that came with ever increasing frequency scaling. The computing power and clock frequency of a single processor reached their peak a few years ago, it just isn't easy to create more powerful and/or faster processors than the current ones; so the major CPU manufacturers (Intel, AMD) switched strategy and went multi-core...*"

> // Kommentar: Altså klarer vi ikke gjøre kjernene raskere enn de er uten å møte på større ulemper. Løsningen ble å heller å ha flere kjerner.
 
 ### What kinds of problems motivates the need for concurrent execution?
 (Or phrased differently: What problems do concurrency help in solving?)
 > Many real-time software systems must be reactive, and must respond to externally generated events, which can occur at any time, often also random times. The ability to respond to such events, although still being able to continue ones previous tasks, is an example of concurrency. In our project with the elevator, requests are sent at random time stamps, which our software system solves with concurrent problem solving. 
 
 ### Does creating concurrent programs make the programmer's life easier? Harder? Maybe both?
 (Come back to this after you have worked on part 4 of this exercise)
 > *Your answer here*
 
 ### What are the differences between processes, threads, green threads, and coroutines?
 > *Your answer here*
 
 ### Which one of these do `pthread_create()` (C/POSIX), `threading.Thread()` (Python), `go` (Go) create?
 > *Your answer here*
 
 ### How does pythons Global Interpreter Lock (GIL) influence the way a python Thread behaves?
 > *Your answer here*
 
 ### With this in mind: What is the workaround for the GIL (Hint: it's another module)?
 > *Your answer here*
 
 ### What does `func GOMAXPROCS(n int) int` change? 
 > *Your answer here*
