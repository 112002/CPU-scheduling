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

# Some commonly used RTOS scheduling algorithms are:
# 1.Cooperarive Multitasaking
Cooperative multitasking, also known as non-preemptive multitasking, is a
style of computer multitasking in which the operating system never initiates
a context switch from a running process to another process. Instead, processes
voluntarily yield control periodically or when idle or logically blocked in order
to enable multiple applications to be run concurrently. This type of multitasking
is called "cooperative" because all programs must cooperate for the entire
scheduling scheme to work. In this scheme, the process scheduler of an
operating system is known as a cooperative scheduler, having its role reduced
down to starting the processes and letting them return control back to it
voluntarily.
Problems:
As a cooperatively multitasked system relies on each process regularly
giving up time to other processes on the system, one poorly designed program
can consume all of the CPU time for itself, either by performing extensive
calculations or by busy waiting; both would cause the whole system to hang. In 
a server environment, this is a hazard that makes the entire environment
unacceptably fragile.
# 2.Rate-monotonic scheduling
In computer science, rate-monotonic scheduling (RMS) is a priority
assignment algorithm used in real-time operating systems (RTOS) with a
static-priority scheduling class. The static priorities are assigned according to
the cycle duration of the job, so a shorter cycle duration results in a higher
job priority.
These operating systems are generally preemptive and have deterministic
guarantees with regard to response times. Rate monotonic analysis is used in
conjunction with those systems to provide scheduling guarantees for a
particular application.
It is a mathematical model that contains a calculated simulation of periods in
a closed system, where round-robin and time-sharing schedulers fail to meet
the scheduling needs otherwise. Rate monotonic scheduling looks at a run
modeling of all threads in the system and determines how much time is
needed to meet the guarantees for the set of threads in question.

# 3.Earliest deadline first scheduling
Earliest deadline first (EDF) or least time to go is a dynamic
priority scheduling algorithm used in real-time operating systems to place
processes in a priority queue. Whenever a scheduling event occurs (task finishes,
new task released, etc.) the queue will be searched for the process closest to its
deadline. This process is the next to be scheduled for execution.
EDF is an optimal scheduling algorithm on pre-emptive uniprocessors, in the
following sense: if a collection of independent jobs, each characterized by an
arrival time, an execution requirement and a deadline, can be scheduled (by any
algorithm) in a way that ensures all the jobs complete by their deadline,
the EDF will schedule this collection of jobs so they all complete by their
deadline.
However, when the system is overloaded, the set of processes that will
miss deadlines is largely unpredictable (it will be a function of the exact
deadlines and time at which the overload occurs.) This is a considerable
disadvantage to a real time systems designer. The algorithm is also difficult to
implement in hardware and there is a tricky issue of representing deadlines in
different ranges (deadlines can't be more precise than the granularity of the clock
used for the scheduling). Therefore EDF is not commonly found in industrial
real-time computer systems.

# ROUND ROBIN SCHEDULING ALGORITHM
The round robin algorithm was designed mainly for time-shared systems not
for real time systems. Time slice or time quantum is defined in case of RR
algorithm, which refers to duration for which the process is allocated to the
CPU and executed.
The processes which have to be executed are kept in a circular queue which has
a head and a tail. The CPU scheduler will go around the queue, allocating the
CPU to each process for a time interval of one quantum but the problem is that
all the processes are arranged in FCFS (First Come First Serve) manner.
Arriving processes are then added to the tail of the queue.
The CPU scheduler will then select the Process Control Block from the head of
the ready queue. This is a disadvantage in RR algorithm since all processes are
basically given the same priority. Round robin also favours the process with
short CPU burst and penalizes long ones


# ALGORITHM
We calculate a intelligent time slice (ITS) is calculated based on the priority,
shortest CPU burst time and context switch. We have a pre defined time slice
which is the Original time slice (OTS), if the process needs special
consideration, the priority component (PC) is assigned to 0 or 1 according to
the pre defined priority by the user. We define a Shortness component (SC)
which is the difference between the burst time of the current process and its
previous process. If the difference is negative, we make SC as 1 else 0. To
calculate CSC i.e Context switch component we add PC,SC and OTP and the
resulting sum is subtracted from the burst time of the process. If the result
obtained is less than the OTS, we consider it as CSC. Adding all the calculated
components we get our ITS.
Our time quantum varies from TQi to TQn, where i is the round number.

1. Sort the processes according to priority as well as shortness and assign a new
priority to each process which is the sum of the original priority and shortness rank.
2. Calculate priority component. If there are n processes, for a process i in n
PCi=0 if its new priority is > 2n/3 (Not Important)
PCi=1 if its new priority is > n/3 (Moderately Important)
PCi=2 if its new priority is >= 1 (Important)
3. Calculate shortness component. If there are n processes, for a process i in n
SCi=0 if the (Burst Time)i>(Burst Time)i-1 (Longer)
SCi=1 if the (Burst Time)i<=(Burst Time)i-1 (Shorter)
4. Calculate the intelligent time slice (ITS) for each process as the sum of the initial
time slice, burst time, priority component and shortness component.
5. Repeat Step 6 until all processes are completed.
6. If the Round number(j) is 1, calculate time quantum as
TQj,i=ITSi if SCi=1
TQj,i=ITSi/2 if SCi=0
If the Round number(j) is not 1, calculate time quantum as
TQj,i=TQj-1,i * 2 if SCi=1
TQj,i=TQj-1,i * 1.5 if SCi=0
7. Calculate average waiting time and average turnaround time
