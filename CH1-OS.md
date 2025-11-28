### OS BASICS
1.1 Definition
OS (Operating System) – System software that manages hardware and provides services to programs.

1.2 OS Goals (ECSF - eating cookie should safe)
Efficient resource use (efficient because os optimizes all the processes and programs running, which prevents conflict thus resources aren't put to waste because theyre managed correctly and arbitrarily. like for example when multi tasking, the operations do not interfere with each other and remains stable.)
Convenience for users (the reason why it is convenient because all complex process runs in the background, while the user only interacts with the GUI/program interface, most of the backend work goes to the os)
Security & protection (they're firewalled to control network traffic and prevent unauthorized access , theyre sandboxed so that dintinct programs that are running have their own environment such that sessions in these programs wouldnt interfere, preventing unauthorized access to sensitive informations from one program to the other we also called this memory protection. And then, User Account Control (UAC) preventing a single user to make site wide changes.)
Fair CPU distribution (the os chooses the distribution with the most balanced performance, efficiency and fairness.)

Fun Fact:
1. The Same-Origin Policy (SOP) prevents sites from interfering with each other's data. Thus, the idea of a website easily controlling all your tabs is a myth due to the Same-Origin Policy, a fundamental web security control implemented in all modern browsers, including Tor. This policy dictates that a script or resource from siteA.com cannot access the content, data, or cookies of siteB.com unless siteB.com explicitly allows it.
2. Cross-Origin Resource Sharing (CORS)
The most common way Site A and Site B communicate is using a mechanism called Cross-Origin Resource Sharing (CORS).
How it works:
A piece of JavaScript code on Site A attempts to request data from Site B.
The browser asks Site B's server if it is allowed to send its data to Site A.
Site B must explicitly include a specific code header in its response, essentially saying, "Yes, I trust Site A; you can share this data with them."
If Site B does not provide this explicit permission header, the browser automatically blocks the request and hides the data from Site A.


1.3 Main Functions (Key Word: “PMDFS”)
- Process Management (core function of OS, deals with creating, scheduling and coordinating processes. it ensures that cpu utilization is efficient and system performs smoothly. 
Types of Process Management:
Single-tasking systems: Easy to manage since only one process runs at a time.
Multiprogramming/multitasking systems: More complex, as multiple processes need to share the CPU efficiently.
Resource sharing: Active processes may share memory and other resources, requiring careful management.
Process synchronization: Necessary when processes interact or communicate to avoid conflicts.

- Memory Management (handles the allocation and deallocation of memory spaces to various processes. ensures that the memory utilization is efficient, maitains memory integration and fragmentation issues are minimized.)
Main memory is the RAM (Random Access Memory) - volatile storage area where programs and data are stored during executing. provides rapid access to the CPU and I/O devices.

Types of Address Spaces
Logical Address Space: created by the cpu, also known as virtual address. can be changed, and is used by programs to reference memory locations. when a program is executed the memory must first be store in this address. The logical address itself is typically stored in computer variables using the platform's native pointer size, such as unsigned long or void *.
Physical Address Space: address created by the mmu(memory management unit), translates the logical address into the correct physical address for hardware access, it is the absolute address in the computer's main memory (RAM) where the specific data is physically located, meanwhile the Memory Management Unit (MMU) is a hardware component taht translates the logical address into a physical address. The data itself is not "translated"; the address is.
Think of the physical memory space as an apartment building. Each unique byte of data that can be stored in the building has a specific address (like an apartment number). This address is a numerical label that the CPU uses to find exactly where to store or retrieve data. the CPU uses a physical address to locate a specific byte of data among the billions available in the memory [1]. The address points directly to the hardware location (the "slot") where the data resides. 

Note: these are NOT storage, they're memory location identifier, meaning it points the location of a piece of data or program within a memory space, typically a virtual one.

Types of Memory Loading
Static Loading: Loads the entire program into memory at once, requiring all its resources before execution begins. Takes more memory space.
Dynamic Loading: Loads only the necessary parts of a program into memory as they are needed during runtime, which saves memory and is more efficient for large programs.
For example: In a game, you would have faster start-up times: The player can begin the game with only core files downloaded and loaded into memory, while the rest of the content loads in the background.
Efficient resource usage: Only the relevant parts of the game are in memory at any given time, reducing the game's memory footprint.
Seamless experience in large worlds: This technique is essential for modern open-world games, allowing expansive environments to be explored without jarring loading screens between areas (developers often use tricks like long corridors or elevator rides to mask the loading process). 
In essence, by selectively fetching resources, the game ensures only necessary data is managed, which is precisely the definition and goal of dynamic loading in game development.

Types of Linking
Static Linking: bundles all required code into a one large, independent application file at build time
Dynamic Linking: gives multiple programs a single copy of the library, which allows all the different programs currently running on your computer to access the necessary functions and resources from that one central source rather than loading redundant individual copies.

- Device / I/O Management (controls how devices like printers, keyboards, and disk drives communicate with the computer's processor.)
- File System Management - the process of organizing, storing, and managing files on a computer's storage devices
- Security - the set of measures and practices used to protect an operating system from threats like malware, unauthorized access, and data theft, while protection measures deal with internal threats.

2. TYPES OF OPERATING SYSTEMS (BMMRDMM)
Batch OS – jobs run with no user interaction.
Multiprogramming OS – multiple programs in memory.
Multitasking – many tasks share CPU (switching).
Real-Time OS (RTOS) – strict timing deadlines.
Distributed OS – multiple computers appear as one.
Multiprocessing OS – multiple CPUs.
Mobile OS – Android, iOS.

3. PROCESS MANAGEMENT
3.1 Definitions

Program – passive code stored on disk.

Process (PCB) – program currently running (active).

Thread – smallest unit of CPU execution inside a process.

3.2 Process States (N-R-R-W-T)

New

Ready

Running

Waiting (Blocked)

Terminated

3.3 PCB (Process Control Block) Contains:

PID (Process ID)

Registers

Program Counter

Memory info

Scheduling info

4. CPU SCHEDULING
4.1 Why Scheduling?

To maximize CPU use, fairness, low waiting time.

4.2 Main Algorithms

FCFS – First Come First Served

SJF / SRTF – Shortest Job / Remaining Time First

Priority Scheduling – highest priority goes first

RR (Round Robin) – fixed time slice (quantum)

MLQ (Multilevel Queue) – separate queues (ex: system > user)

4.3 Scheduler Types

Long-term – admission of jobs

Short-term – chooses next process for CPU

Medium-term – swaps processes in/out

5. MEMORY MANAGEMENT
5.1 Key Terms

MMU – hardware that translates virtual → physical addresses

Frame – physical memory unit

Page – virtual memory unit

5.2 Memory Allocation Types

Contiguous Allocation – single block

Paging – fixed-size pages, removes external fragmentation

Segmentation – variable-sized logical segments

5.3 Fragmentation

Internal – unused space inside an allocated block

External – total free space exists but scattered

5.4 Virtual Memory

Gives illusion of large memory using disk.

Uses paging and swap space.

6. FILE SYSTEMS
6.1 File Attributes

Name

Type

Size

Location

Protection

Timestamps

6.2 Directory Structures

Single-level

Two-level

Tree-structured

Acyclic graph (shared files)

6.3 File Operations

Create

Read

Write

Delete

Open / Close

7. I/O & DEVICE MANAGEMENT
7.1 Terms

Driver – software that controls a device

Buffering – temporary storage

Spooling – overlapping I/O with computation

7.2 I/O Methods

Programmed I/O

Interrupt-driven I/O

DMA (Direct Memory Access) – fastest; bypasses CPU

8. CONCURRENCY & SYNCHRONIZATION
8.1 IPC (Inter-Process Communication)

Pipes

Message Passing

Shared Memory

8.2 Synchronization Tools

Semaphore (sem) – integer used to control access

Mutex (mutual exclusion) – lock for one thread only

8.3 Race Condition

Output depends on the order of execution — dangerous.

8.4 Deadlock (4 Conditions – “M H N C”)

Mutual Exclusion

Hold and Wait

No Preemption

Circular Wait

8.5 Deadlock Strategies

Prevention

Avoidance

Detection & Recovery

9. SECURITY & PROTECTION
Basic Security Concepts

Authentication – verify identity

Authorization – what user can access

Encryption – protects data

Access Control List (ACL) – permissions list

10. FAST FACTS (FOR EASY MEMORY)

OS = Resource Manager

Process = Active Program

Thread = Lightweight Process

Paging fixes external fragmentation

Segmentation = logical memory view

Round Robin = fair sharing

Deadlock = circular dependency

DMA = fastest I/O

Kernel = core of OS

User mode vs Kernel mode = protection
