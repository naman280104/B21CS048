# XV Quiz (CSL 3030)

Welcome to the XV Quiz for CSL 3030 - Operating Systems!



## Instructions
- Answer the multiple-choice questions by selecting the correct option.
- For theoretical questions, provide concise and accurate explanations.
- Feel free to use this quiz for self-assessment or educational purposes.

## Multiple-Choice Questions

#### Question 1: Basics
1. What is XV6?
   - a. A programming language
   - b. A Unix-like operating system
   - c. A file system
   - d. An assembly language

#### Question 2: Architecture
2. XV6 is based on which earlier operating system?
   - a. Windows
   - b. Linux
   - c. BSD
   - d. DOS

#### Question 3: File System
3. Which file system is used in XV6?
   - a. FAT32
   - b. NTFS
   - c. ext4
   - d. simple

#### Question 4: System Calls
4. How are system calls implemented in XV6?
   - a. As functions in the C standard library
   - b. As interrupts
   - c. Through the command line
   - d. As external programs

#### Question 5: Processes
5. In XV6, what is the maximum number of processes that can run simultaneously?
   - a. 128
   - b. 256
   - c. 512
   - d. 1024

#### Question 6: Shell
6. What is the name of the shell used in XV6?
   - a. Bash
   - b. Zsh
   - c. Sh
   - d. Fish

#### Question 7: Scheduling
7. How does XV6 handle process scheduling?
   - a. Round-robin scheduling
   - b. Priority-based scheduling
   - c. First-Come-First-Serve (FCFS)
   - d. Random scheduling

#### Question 8: Memory Management
8. Which memory management technique is used in XV6?
   - a. Paging
   - b. Segmentation
   - c. Virtual Memory
   - d. None of the above

#### Question 9: Interrupts
9. How are interrupts handled in XV6?
   - a. Through polling
   - b. Using hardware interrupts
   - c. Using software interrupts
   - d. Both b and c

#### Question 10: Multithreading
10. Does XV6 support multithreading?
    - a. Yes
    - b. No

#### Bonus Question:
11. Who developed XV6?
    - a. Microsoft
    - b. Google
    - c. MIT
    - d. IBM

## Theoretical Questions

#### Question 12: Process States
12. Briefly explain the different states a process can be in within the XV6 operating system.

#### Question 13: File System Structure
13. Describe the structure of the file system in XV6. Include the key components and their roles.

#### Question 14: System Calls vs. Library Functions
14. Explain the difference between system calls and library functions in the context of XV6. Provide examples of each.

#### Question 15: Memory Paging
15. How does memory paging work in XV6? Discuss the benefits of using paging in memory management.

#### Question 16: Shell Commands
16. Name and briefly explain three essential shell commands in the XV6 operating system.

#### Question 17: Process Synchronization
17. Discuss the concept of process synchronization in XV6. Why is it essential, and what mechanisms are used to achieve it?

#### Question 18: Interrupt Handling
18. Explain the role of interrupts in the XV6 operating system. How are interrupts handled, and what is their significance in system operation?

#### Question 19: Virtual Memory
19. What is virtual memory, and how is it implemented in XV6? Discuss the advantages of using virtual memory.

#### Question 20: Boot Process
20. Outline the steps involved in the boot process of XV6. What happens from the moment the computer is powered on to when the XV6 kernel is loaded into memory?

## Answers
Please write your answers here
1. b
2. b
3. d
4. b
5. a
6. c
7. a
8. a
9. d
10. b
11. c
12. In XV6, processes can be in following states -
       a) UNUSED: The process has not been allocated yet.
       b) EMBRYO: The process has been allocated, but it has not yet started running.
       c) RUNNING: The process is currently running on the CPU.
       d) RUNNABLE: The process is ready to run, but the CPU is not currently available.
       e) ZOMBIE: The process has finished running, but its parent process has not yet reaped it.
       f) SLEEPING: The process is waiting for an event to occur, such as a file to be opened or a network connection to be established.
       
13. XV6 is a simple layered file system that consists follwoing key components -
      a) File descriptor: It abstracts many Unix resources like pipes, files and devices.
      b) Pathname: It provides hierarchical path names like /usr/local/...., and resolves them with recursive lookup.
      c) File descriptor: This layer unifies resource management, while the directory layer utilizes inode tables for efficient file handling.
      d) Inode: The inode layer associates each file with a unique inode number and data blocks for efficient data storage and retrieval.
      e) Logging: The logging layer facilitates transactional updates to multiple blocks, ensuring data integrity in the event of system crashes.
      f) Buffer Cache: The buffer cache layer optimizes disk access and enforces data integrity by caching and synchronizing block modifications.
      g) Disk: The disk layer reads and writes blocks on an virtio hard drive.  
    The file system is organized into a hierarchy of directories. The root directory is the top-level directory of the file system. All other directories are contained within the root directory.
    When a file is opened, the kernel looks up the file name in the directory table to get the inode number for the file. The kernel then reads the inode from the inode table to get the location of the data blocks for the file. The kernel then maps       the data blocks into the buffer cache to read or write the file data.

14. System calls and library functions are both mechanisms used by programs to request services from the operating system. Following are some differences - 
    System calls are implemented in the kernel, which is the core of the operating system. When a program makes a system call, the kernel is invoked directly to perform the requested service. System calls are typically used to access hardware             resources, such as the file system or the network, or to perform privileged operations, such as creating a new process or terminating another process.
    Library functions, on the other hand, are implemented in user space, which is the memory space that is accessible to user programs. When a program calls a library function, the code for the function is simply copied into the program's memory and      executed. Library functions are typically used to perform common tasks, such as reading and writing files, manipulating strings, or performing mathematical operations.

    Here are some examples of system calls in XV6:
       fork(): Creates a new process
       exec(): Loads and executes a new program
       open(): Opens a file
       read(): Reads data from a file
       write(): Writes data to a file

    Here are some examples of library functions in XV6:
       printf(): Prints formatted output to the console
       scanf(): Reads formatted input from the console
       malloc(): Allocates memory
       free(): Frees memory
       strcpy(): Copies a string
       strlen(): Returns the length of a string

15. In xv6, paging is used to manage memory. xv6 uses 32-bit virtual addresses (VAs), which means that the maximum memory size is 4GB. A page size of 4KB is used, and a two-level page table is employed. Paging enables non-contiguous memory allocation by dividing memory into frames of equal size and programs into pages of equal size. This allows the operating system to allocate memory to processes in a more efficient way, even if the memory is not physically contiguous.

16. Three essential commands are -
      a) ls: It lists all content in a directory
      b) mkdir: It is used to create new directory with a specified name.
      c) Cat: It is used to concatenate files and print them to the console.

17. In xv6, process synchronization relies on locks, which play a crucial role in maintaining memory consistency by preventing race conditions. This mechanism is vital for preventing issues like deadlock and ensuring that processes coordinate effectively to access shared resources without conflicting with one another.

18. When an interrupt occurs, the processor halts the execution of the current program and initiates the execution of an interrupt handler. The role of this handler is to manage and address the interrupt. After handling the interrupt, the program resumes execution (if it hasn't been terminated). The values of its registers are saved when the interrupt occurs so that they can be reinstated at that point.

19. xv6 has no implementation of a virtual memory.

20. make qemu-nox command used to boot the XV6.
     Following processes are involved
     a) BIOS initialization
     b) Boot loader execution
     c) Kernel entry point
     d) Memory setup
     e) Device initialization
     f) Process creation
     g) User program execution
   Throughout the boot process, the kernel performs various checks and configurations to ensure the system is in a stable state and ready to execute user programs. This involves enabling interrupts, setting up system call handling, and initializing system parameters.
