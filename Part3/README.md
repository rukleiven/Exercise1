# Reasons for concurrency and parallelism


To complete this exercise you will have to use git. Create one or several commits that adds answers to the following questions and push it to your groups repository to complete the task.

When answering the questions, remember to use all the resources at your disposal. Asking the internet isn't a form of "cheating", it's a way of learning.

 ### What is concurrency? What is parallelism? What's the difference?
> Concurrency: Multiple tasks start, run and complete independent of eachother in overlapping time periods. They do not necessarily execute at the same instant, i.e multitasking on a single-core processor. Parallelism means that multiple tasks run at the exact same time, which requires multiple processor cores.   

> // Kommentar: Skiller mellom mulighet og faktisk utførelse.
 
 ### Why have machines become increasingly multicore in the past decade?
 > "The trend towards multiple cores is an engineering approach that helps the CPU designers avoid the power consumption problem that came with ever increasing frequency scaling. The computing power and clock frequency of a single processor reached their peak a few years ago, it just isn't easy to create more powerful and/or faster processors than the current ones; so the major CPU manufacturers (Intel, AMD) switched strategy and went multi-core...*"
 
>Due to limitations in hardware. The number of transistor per areal does not scale by Moore's anymore. A solution to this problem is multiple-core systems. 

> // Kommentar: Altså klarer vi ikke gjøre kjernene raskere enn de er uten å møte på større ulemper, varme. Løsningen ble å heller å ha flere kjerner.
 
 ### What kinds of problems motivates the need for concurrent execution?
 (Or phrased differently: What problems do concurrency help in solving?)
 > Many real-time software systems must be reactive, and must respond to externally generated events, which can occur at any time, often also random times. The ability to respond to such events, although still being able to continue ones previous tasks, is an example of concurrency. In our project with the elevator, requests are sent at random time stamps, which our software system solves with concurrent problem solving. 
 
 ### Does creating concurrent programs make the programmer's life easier? Harder? Maybe both?
 (Come back to this after you have worked on part 4 of this exercise)
 
> The programmer must be aware of shared variables, such that if two threads are modifying the same variable, it need to be synchronized. 
 

 
 ### What are the differences between processes, threads, green threads, and coroutines?

> A process is the instance of a running application that contains program code and data. Threads do not contain data, but execute the program code of the process. A process can be made up of several threads. Green threads are threads that are scheduled of a library or a virtual machine instead of the OS.  

> Coroutines er subrutioner (metoder, funksjoner, osv.) som gir fra seg kontroll over prosessor under veis i kjøringen.

 
 ### Which one of these do `pthread_create()` (C/POSIX), `threading.Thread()` (Python), `go` (Go) create?
> pthread_create() oppretter en tråd. Threading.Thread() oppretter en OS kontrollert tråd, men noe spesielt pga GIL (global interpreter lock). Go oppretter coroutines som ligner på green threads, men det er en forskjell.
 
 ### How does pythons Global Interpreter Lock (GIL) influence the way a python Thread behaves?
 > "The GIL is a lock that allows only one thread to hold the control of the Python interpreter. This means that only one thread can be in a state of execution in any point of time. The GIL is often used in single-threaded programs, but can be used as a bottleneck in multi-threaded code." 
 
 ### With this in mind: What is the workaround for the GIL (Hint: it's another module)?
 > En må kjøre flere python interpreters gjennom å benytte multiprocess modulen. For så å dele et minneområde mellom prosessene.
 
 ### What does `func GOMAXPROCS(n int) int` change? 
 > The gomaprox variable limits the number of operating system threads that can execute user-level Go code simultaneously.
 > Setter maksgrense for hvor mange tråder som go corutinene kan fordeles over.
