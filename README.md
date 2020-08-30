# CPU-scheduling
All the algorithms of CPU scheduling is going to be used in this program using c++.
# I. Introduction:
In computer science, scheduling is the process by which processes are given
access to system resources like processor cycles, communications bandwidth.
Hence, there arises the need for a scheduling algorithm [5] for the computer
systems to perform multitasking and multiplexing.
Scheduling is a fundamental operating system function that determines which
process run, when there are multiple run able processes. CPU scheduling is
important because it impacts resource utilization and other performance
parameters. There exists a number of CPU scheduling algorithms like First
Come First Serve, Shortest Job First Scheduling, Round Robin scheduling,
Priority Scheduling etc, but due to a number of disadvantages these are rarely
used in real time operating systems except Round Robin scheduling.

/** A number of assumptions are considered in CPU scheduling which are as
follows: **/
1.Job pool consists of run able processes waiting for the CPU.
2.All processes are independent and compete for resources.
3.The job of the scheduler is to distribute the limited resources of
CPU to the different processes fairly and in a way that optimizes
some performance criteria.
The scheduler is the component of the kernel that selects which process to run
next. Operating systems may feature up to three distinct types of schedulers, a
long term scheduler, a mid-term or medium term scheduler and a short-term
scheduler. The long term scheduler or job scheduler selects processes from the
job pool and loads them into memory for execution. The short term scheduler,
or CPU scheduler selects from among the processes that are ready to execute,
and allocates CPU to one of them. The medium term scheduler removes
processes from memory and reduces the degree of multiprogramming results
in the scheme of swapping. Swapping is the scheme which is performed by
dispatcher which is the module that gives control of the CPU to the process
selected by the short-term scheduler.
The CPU scheduling also plays an important role in the real time operating
system which always has a time constraint on computations. A real time
system is the one whose applications are mission-critical, where real-time
tasks should be scheduled to be completed before their deadlines . Most realtime systems control unpredictable environments and may need operating
systems that can handle unknown and changing tasks. So, not only a dynamic
task scheduling is required, but both system hardware and software must
adapt to unforeseen configurations .
There are two main types of real-time systems : Hard Real-Time System, Firm
or Soft Real-Time System. In Hard Real-Time System, it requires that fixed
deadlines must be met otherwise disastrous situation may arise whereas in
Soft Real-Time System, missing an occasional deadline is undesirable, but
nevertheless tolerable. System in which performance is degraded but not
destroyed by failure to meet response time constraints is called soft real time
systems.
In real time systems each task should be invoked after the ready time and
must be completed before its deadline, an attempt has been made to
satisfy these constraints. Simple round robin architecture is not suitable to
implement in Soft real time due to more number of context switches,
longer waiting and response times. This in turn leads to low throughput in
the system. If a real-time process having relatively larger CPU burst it will
leads to the problem of starvation .Priority scheduling may be a better
option for real-time scheduling but it will face the similar problem i.e. low
priority processes will always starve.
