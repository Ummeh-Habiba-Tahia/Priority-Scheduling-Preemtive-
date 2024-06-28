# Priority-Scheduling-Preemtive-
##Description:
This C++ code implements two CPU scheduling algorithms: Round Robin and Preemptive Priority Scheduling. The code takes input for process details, such as burst time and priority, and then uses the algorithms to schedule these processes, providing relevant output.

Code Breakdown: 
1.Include Statements and Namespace:

#include <iostream>: for input and output operations.
#include <vector>: to use the std::vector container.
#include <queue>: to use the std::queue and std::priority_queue containers.
#include <algorithm>: for the std::min function.
The using namespace std; directive allows the use of standard library names without the std:: prefix.

2.Process Struct:

This structure represents a process with the following fields:
    pid: Process ID.
    bt: CPU Burst time required.
    priority: Priority of the process.
    remaining_bt: Remaining burst time for preemptive scheduling.
    
3.ComparePriority Struct:

This struct is used as a comparison function for the priority queue in preemptive priority scheduling.
The operator() function compares two processes based on their priority. A higher priority value implies a lower priority, thus returning true if p1 has a lower priority than p2.

4.Round Robin Scheduling Function:

roundRobinScheduling(vector<Process>& processes, int quantum): This function implements the Round Robin scheduling algorithm.
It initializes the ready queue and calculates the total burst time.
Processes are added to the ready queue based on their arrival time.
It iterates through the ready queue, executing each process for a time slice equal to the quantum or the remaining burst time, whichever is smaller.
If a process's burst time is not exhausted, it is re-added to the queue.
The function prints the execution details for each process.

5.Preemptive Priority Scheduling Function:

priorityScheduling(vector<Process>& processes): This function implements the Preemptive Priority scheduling algorithm.
It initializes the priority queue and calculates the total burst time.
Processes are added to the priority queue based on their arrival time.
It iterates through the priority queue, executing each process for a minimum time slice of 1 unit.
If a process's burst time is not exhausted, it is re-added to the queue.
If a process completes, the total waiting time is updated.
The function calculates and prints the average waiting time for the scheduling.

6.Main Function:

The main function takes input for the number of processes.
It initializes the processes vector with process IDs, burst times, and priorities.
It takes input for the time quantum for Round Robin scheduling.
It calls both the roundRobinScheduling and priorityScheduling functions to schedule the processes and output the results.

Example Execution:
User is prompted to enter the number of processes.
User is prompted to enter the burst time and priority for each process.
User is prompted to enter the time quantum for Round Robin scheduling.
The program schedules the processes using Round Robin and Preemptive Priority scheduling algorithms.
The program outputs the execution details for Round Robin and the average waiting time for Preemptive Priority scheduling.

Output:

Enter the number of processes: 3
Enter details for each process:
Process 1 Burst time: 10
Priority: 1
Process 2 Burst time: 5
Priority: 2
Process 3 Burst time: 8
Priority: 1
Enter the time quantum for Round Robin Scheduling: 2
Executing process 1 for time 2
Executing process 2 for time 2
Executing process 3 for time 2
Executing process 1 for time 2
Executing process 2 for time 2
Executing process 3 for time 2
Executing process 1 for time 2
Executing process 3 for time 2
Executing process 1 for time 2
Executing process 2 for time 1
Executing process 1 for time 1
Average waiting time for Priority Scheduling: 10
