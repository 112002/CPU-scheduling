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

# II. SCHEDULING OBJECTIVES
A system architect must consider various elements in constructing a scheduling
algorithm, for example, kind of frameworks utilized and client necessities.
Relying upon the system, the client and designer may anticipate that the
schedulers will :
Maximize throughput: A scheduling algorithm ought to be equipped for
adjusting the greatest number of jobs per unit of time.
Avoid inconclusive blocking or starvation: A job ought not sit tight
for unbounded time before or while process service.
Minimize overhead: Overhead causes wastage of assets. Be that as it
may, when we utilize system resources viably, then general system
execution enhances extraordinarily.
Enforcement of priorities: if system allocates priorities to forms, the
booking system ought to support the higher-need forms.
Attain balance between response, utilization: the scheduling
algorithm must keep resources occupied
Support jobs which show desirable behavior.
Corrupt gracefully under huge load.
A system might finish these objectives in many ways. The scheduler can
stall indefinite blocking of jobs via aging. Scheduler increments throughput
by favoring processes whose requests can be satisfied quickly, or whose
completion cause other processes to run.
# III. SCHEDULING CRITERIA
CPU scheduling algorithms maybe such which have different properties, and
the choice of one particular algorithm might favor one category of processes
over other. Choosing an algorithm for a particular situation, we must cater to
properties of various algorithms. The scheduling criteria include the
following:
Context Switch: A context switch is process of storing and restoring
context (state) of a preempted process, so that execution may be resumed
from same point at a later stage. Context switching involves a lot of
computation, lead to wastage of time and memory, which in turn
increases the overhead of scheduler, hence operating system’s design, is
to optimize only these switches.
Throughput: it is the number of processes completed per unit time. It is
slow in round robin scheduling implementation. Context switching and
throughput are inversely proportional.
CPU Utilization: Tells the business of the CPU. One needs to
maximize CPU utilization.
Turnaround Time: Total time spent to complete the job. The time
interval from the time of submission of a job to its completion is the
turnaround time. Total turnaround time is the sum of the times spent
waiting to get into memory, waiting time in the ready queue, execution
time on the CPU and doing I/O.
Waiting Time: Time a job has been stalled in ready queue. The CPU
scheduling algorithm does not affect the amount of time during which a
process executes or does input-output; it affects only the amount of time
that a process spends waiting in ready queue.
Response Time: in real time systems, turnaround time may not be best
measure. Often, a job can provide with some output fairly early and
continue computing new results while previous results are being
produced to the user. Thus, it is the time from the submission of a
request until the first response is produced that means time when the
task is submitted until the first response is received. Thus, the response
time should be less.
Hence a good scheduling algorithm for real time and time sharing system must
have: -
 less context switches.
 high CPU utilization.
 high throughput.
 Less turnaround time.
 Less waiting
time.

