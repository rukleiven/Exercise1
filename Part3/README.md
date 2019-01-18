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
 > "This of course requires a lot more work from the application developers in order to harness the full power of multi-tasking: a program running on a single task just doesn't get any benefit from a multi-core CPU (although the system gets an overall bonus because it doesn't lock if a single process takes a single CPU to 100% usage)"
 
 Kan være problematisk ved endring av variabler. F.eks. dersom to parallelle oppgaver blir løst samtidig, og bruker felles variabler.
 
 ### What are the differences between processes, threads, green threads, and coroutines?
 > "A process is the smallest unit of a running application, an application can consist of one or more processes. A thread is the basic unit to which the operating system allocates processor time. A thread can execute any part of the process code." 

> "Green threads are threads that are scheduled by a runtime library or virtual machine, instead of the underlying operative system, which regular threads are. Green threads are “user-level threads” which means they are scheduled by an ordinary user-level process, not by the kernel. So they can be used to simulate multi-threading on platforms that don’t provide that capability."

> "Coroutine: line of execution where theres only one corioutine running at any given time. A corioutine has its own stack, its own variables, and its own instruction pointer. It shares global variables, and most anything else with other coroutines." 

 
 ### Which one of these do `pthread_create()` (C/POSIX), `threading.Thread()` (Python), `go` (Go) create?
 > 1.	"Creates a new thread"
> 2.	"Returns selected thread object. If the thread is not created yet, a dummy thread object with limited functionality is returned."
> 3.	"Starts a new goroutine running, a goroutine is a lightweight thread managed by the go runtime."
 
 ### How does pythons Global Interpreter Lock (GIL) influence the way a python Thread behaves?
 > "The GIL is a lock that allows only one thread to hold the control of the Python interpreter. This means that only one thread can be in a state of execution in any point of time. The GIL is often used in single-threaded programs, but can be used as a bottleneck in multi-threaded code." 
 
 ### With this in mind: What is the workaround for the GIL (Hint: it's another module)?
 > *Your answer here*
 
 ### What does `func GOMAXPROCS(n int) int` change? 
 > The gomaprox variable limits the number of operating system threads that can execute user-level Go code simultaneously. 
