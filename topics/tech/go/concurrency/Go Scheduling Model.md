# Go Scheduling Model

## The GPM scheduling model

The scheduling mechanism of Go programs, called the **GPM scheduling model**, consists of three main characters: **Goroutines (G)**, **Machines (M)**, and **Processors (P)**. The model is designed to manage the execution of goroutines across multiple processors.

* **Goroutines (G)**: These are the lightweight threads that are managed by the Go runtime. They are the smallest unit of work in Go. Goroutines are like application-level threads. A Goroutine maintains an executing state, but can only be executed when attached to a processor.
* **Processor (P)**: A processor is a logical entity that executes a goroutine. It owns the executing resources by binding to a logical core. In addition to the Goroutine executed, it also has a local run queue, or "LRQ".
* **Machine (M)**: A machine is actually an OS thread that is still managed by the OS, and must be placed on a core to execute. Each machine is individually attached to a processor, and this is how the performance of the scheduler is affected by the number of cores.

## References

* [[Medium] Scheduling In Go](https://medium.com/random-life-journal/scheduling-in-go-727c9b88c93a)
* [[Ardan Labs] Scheduling In Go: Part II – Go Scheduler](https://www.ardanlabs.com/blog/2018/08/scheduling-in-go-part2.html)