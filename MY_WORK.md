# 📝 MY_WORK: Student Information, Development Log, Reflection & Answers

## 👤 Student Information

| Field | Your Answer |
|-------|-------------|
| **Full Name** | Ghadi Bader |
| **Student ID** | 446051748 |
| **University Email** | 446051748@std.psau.edu.sa |
| **GitHub Username** | Ghadi-bader48 |
| **Repository Link** | https://github.com/Ghadi-bader48/OS-Assignment1-Ghadi-Bader |
 
---

## 🎥 Video Link

**Video Link**: [Paste your video link here]

---

## 🗺️ Work Roadmap (follow in this order)

| Step | Task | Status (mark when done) |
|---|---|---|
| 0 | Read README and run original starter | Completed on October 9, 2026 2:00 pm |
| 1 | Fork starter, set ID, commit and push | Completed on October 9, 2026 4:43 pm |
| 2 | Add display priority and commit | Completed on October 9, 2026 4:56 pm |
| 3 | Add context switch counter and commit | Completed on October 9, 2026 6:24 pm |
| 4 | Add waiting/turnaround summary and commit | Completed on October 9, 2026 8:58 pm |
| 5 | Write five log entries | Completed on October 9, 2026 9:40 pm |
| 6 | Write reflection in my own words | Completed on October 9, 2026 10:10 pm   |
| 7 | Upload demo video and add  link |   |
---

## 🔁 Commit Rules (MANDATORY)

| Commit | Message |
|---|---|
| 1 | `Set my student ID: 446051748` |
| 2 | `Feature 1: Added priority field to Process class` |
| 3 | `Feature 2: Implemented context switch counter` |
| 4 | `Feature 3: Added waiting time tracking and summary table` |
| 5 | `Docs: Added development log` |
| 6 | `Docs: Completed reflection and technical answers` |
| 7 | `Docs: Revised my answers` |
---

# Part A: Development Log (0.5 mark)

## Your Development Log

### Entry 1 - October 9, 2026, [4:43 pm]
**What I did**: Prepared my GitHub repository and set my student ID.

**Details**:
- Forked the official starter repository under `Ghadi-bader48` and named it `OS-Assignment1-Ghadi-Bader`.
- Cloned the public fork into VS Code and configured my Git identity.
- Replaced the student ID with `446051748` in `SchedulerSimulation.java`.
- Committed and pushed `Set my student ID: 446051748`.

**Challenges**: GitHub initially rejected a push with HTTP error 403.

**Solution**: Checked GitHub authentication and repository access, then completed the push using the correct account.

**Time spent**: [10 min]

---

### Entry 2 - October 9, 2026, [4:56 pm]
**What I did**: Added process priorities.

**Details**:
- Added the `priority` field and getter to the `Process` class.
- Generated priority values from 1 to 10 using `1 + random.nextInt(10)`.
- Updated `addProcessToQueue()` to display the priority when a process enters the ready queue.
- Kept the queue in FIFO order; priority affects display only.
- Committed and pushed `Feature 1: Added priority field to Process class`.

**Challenges**: I needed to keep the new priority value separate from scheduling decisions.

**Solution**: Left the FIFO queue and scheduler selection unchanged and used priority only in the printed queue message.

**Time spent**: [13 min]

---

### Entry 3 - October 9, 2026, [6:24 pm]
**What I did**: Added context-switch counting.

**Details**:
- Added `private static int contextSwitches = 0` in `SchedulerSimulation`.
- Incremented the counter before each `currentThread.start()` in the scheduler loop.
- Printed `Total context switches` after the scheduling loop.
- Committed and pushed `Feature 2: Implemented context switch counter`.

**Challenges**: I needed to count scheduler dispatches instead of the number of times a process was placed in the queue.

**Solution**: Incremented the counter at the point where a process thread actually starts running.

**Time spent**: [15 min]

---

### Entry 4 - October 9, 2026, [8:58 pm]
**What I did**: Added waiting-time tracking and the final summary table.

**Details**:
- Used `System.currentTimeMillis()` in `markQueued()` and `markStarted()`.
- Added each completed queue-wait interval to the process's accumulated waiting time.
- Stored all processes in an `allProcesses` list for the final report.
- Printed process name, burst time, waiting time, and turnaround time, with turnaround calculated as waiting plus burst.
- Committed and pushed `Feature 3: Added waiting time tracking and summary table`.

**Challenges**: A process can be re-queued, so its total waiting time must include more than one queue interval.

**Solution**: Recorded a new timestamp on each queue entry and accumulated the delay at each dispatch.

**Time spent**: [20 min]

---

### Entry 5 - October 9, 2026, [9:40 pm]
**What I did**: Reviewed my code commits and worked on the assignment documentation.

**Details**:
- Checked  that the feature commits were visible in my public GitHub repository.
- Reviewed the `Process` class, scheduler loop, and summary table.
- Added the development log with information about each implemented feature.
- Checked that the technical descriptions matched the code and the fixed seed for my student ID.

**Challenges**: I needed to connect the written explanations to the exact methods used in the program.

**Solution**: Reviewed `addProcessToQueue()`, the thread scheduling loop, and `markQueued()` / `markStarted()` while writing the log.

**Time spent**: [30 min]

---


## Development Log Summary

**Total time spent on assignment**: [2 hrs]

**Most challenging part**: Tracking waiting time over repeated entries to the ready queue while keeping the Round-Robin scheduling logic unchanged.

**Most interesting learning**: How `Thread.start()`, `Thread.join()`, and the FIFO queue work together to execute processes in time slices.

**What I would do differently next time**: Test and document each change immediately after completing it, including the exact output used in the technical answers.
---

# Part B: Reflection (0.5 mark)

## Question 1: What did you learn about multithreading?

**Your Answer:** 
I learned that a Java class implementing Runnable can be executed by a Thread. The Process class represents a task, and addProcessToQueue() methods creates a thread for each CPU turn. Thread.start() starts the thread, then Thread.join() method is used to wait for the thread to finish. Thread.sleep() method is used to make the thread  sleep, the time equals the time of the CPU execution . If a process still has remaining burst time, it returns to the ready queue and receives another thread for its next turn. In my test P2 needed three execution turns to complete its 10,883 ms burst time.


## Question 2: What was the most challenging part of this assignment?

**Your Answer:** 
It was calculating the total waiting time of each process, beacuse a process can return to the ready queue several times, so to get the waiting time correct I neeed to summ all of its waiting times.I record when each process entered the queue and when its next execution started. In my test P2 was re-queued twice because its burst time was 10,883 ms and the quantum was 5,000 ms. The final waiting time (71,740 ms) was the sum of all time spent waiting for its different turns. I also had to ensure that collecting these measurements did not change the FIFO scheduling order.

## Question 3: How did you overcome the challenges you faced?

**Your Answer:**
I saved the time at which the program inserts a process into the queue and when the scheduler starts its thread.I used markQueued() method to save the timestamp at which the process is inserted to the queue using the System.currentTimeMillis() methond, After that  markStarted() was used to add the elapsed queue-waiting time to the process's previous total. This sum's up all the waiting time across for all rounds. I Finally verified the calculations by checking the final output, for P2 71,740 ms of WT + 10,883 ms BT = 82,623 ms TT.


## Question 4: How can you apply multithreading concepts in real-world applications?

**Your Answer:** 
 Multithreading helps applications manage multiple tasks while keeping the system responsive. For example,Operating system share CPU time among runnable threads using time slices. A browser can run background tasks while keeping its interface responsive. A server use worker threads to handle requests from different users at the same time. In my test 5,000 ms quantum is used to show how unfinished tasks can return to a ready queue. This demonstrate the idea of dividing work into turns to prevent a long-running task from blocking all other ready tasks.

### Optional: What would you like to learn more about?

Learn more about synchronization when several threads use shared data.

### Optional: How confident do you feel about multithreading concepts now?

I feel like 80%.

### Optional: Feedback on the assignment

None.
---

# Part C: Technical Answers (0.5 mark)

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes? Mention at least **TWO** specific differences (e.g., memory sharing, creation overhead, communication speed), and reference relevant parts of `SchedulerSimulation.java`.

**Your Answer:**
A process is an independent program running in its own isolated memory space, while a thread is a smaller path of execution living inside a process that shares memory with other threads. This memory sharing makes threads much faster to create and communicate with because they don't require heavy operating system overhead. In our SchedulerSimulation.java file, the Process class acts as our data model for a task, but we use new Thread(process) to actually create a real Java thread to execute that task's run method concurrently.

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from **your** program output, including **how many times that process was re-queued** before it finished, and explain why re-queueing matters for fairness.

**Your Answer:** 
When a process doesn't finish within the 5,000 ms time quantum, the scheduler interrupts it, removes it from the CPU, and appends it to the back of the FIFO ready queue. In my test, P2 had a burst time of 10,883 ms, so it ran for 5,000 ms, yielded, ran for another 5,000 ms, yielded again, and finished on its third turn. So it was re-queued exactly two times after its initial entry. Re-queueing is vital for fairness because it prevents long, CPU-heavy processes from starving shorter tasks of execution time.


Example from my output:
```
P2 added to ready queue │ Priority: 3 │ Burst time: 10883ms
P2 executing quantum [5000ms]
Remaining time: 5883ms
P2 yields CPU for context switch
P2 added to ready queue │ Priority: 3 │ Burst time: 10883ms
P2 executing quantum [5000ms]
Remaining time: 883ms
P2 yields CPU for context switch
P2 added to ready queue │ Priority: 3 │ Burst time: 10883ms
P2 executing quantum [883ms]
Remaining time: 0ms
P2 finished execution!
```

**Explanation of example:**
The initial queue entry is not counted as a re-queue. The two later `added to ready queue` messages show that P2 was re-queued twice before finishing on its third execution turn. Its priority was displayed but did not change the FIFO order.

## Question 3: Thread Lifecycle

**Question**: A thread goes through these states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (e.g., P1) from your simulation. For each state, explain **when** P1 enters it and **which line or method call** triggers the transition (`Thread.start()`, `Thread.join()`, `Thread.sleep()`, etc.).

**Your Answer:** 

1. **New:** The scheduler creates P1's Java thread with new Thread(process) in addProcessToQueue() method, but the thread has not been started.

2. **Runnable:** Calling currentThread.start() makes P1's thread ready to execute; Java officially uses RUNNABLE for both ready-to-run and running threads.

3. **Running:** When the JVM schedules P1, its run() method executes the first 5,000 ms simulated time slice.

4. **Waiting:** During each Thread.sleep(stepTime), P1's thread enters the Java TIMED_WAITING state, while the main scheduler thread waits for P1 using currentThread.join().

5. **Terminated:** P1's thread terminates when its run() method returns, and because 370 ms remains, the scheduler creates a new thread for P1's second and final 370 ms turn.

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. **At least one** must be an operating-system-level scenario (e.g., how an OS scheduler shares CPU time among running programs). The second can be any application you choose. For each, explain what the system is and **why Round-Robin fits** (fairness, responsiveness, predictability).

**Your Answer:** 

### Example 1 (operating-system level): CPU time sharing

**Description:** An operating system may use Round-Robin scheduling to share CPU time among ready threads belonging to a browser, a media player, and an editor. Each thread receives a limited time slice, comparable to the 5,000 ms quantum in my simulation. If the thread still needs CPU time, it becomes eligible for another turn.

**Why Round-Robin works well here:** Rotating between ready threads improves fairness and helps interactive applications remain responsive instead of letting one CPU-bound thread monopolize the processor. The scheduler's dispatch counter in my program illustrates how often a simulated process was selected to start running.

### Example 2: Server processing queued tasks

**Description:** A server can maintain a FIFO queue of small processing tasks for several users and execute them using worker threads. If a task requires more work than its assigned turn, the application can divide the work and place the unfinished task at the back of the queue. This is similar to P2 returning to the queue twice before completing in my simulation.

**Why Round-Robin works well here:** Taking turns helps prevent one large request from delaying every smaller queued task. It also gives a predictable order of service for tasks that are ready to be processed.

## Summary

**Key concepts I understood through these questions:**
1. The `Process` class models a task, while Java threads actually run its time slices.
2. FIFO Round-Robin gives unfinished processes repeated turns without using their displayed priority for selection.
3. Waiting time accumulates across queue entries, and turnaround time is calculated as waiting time plus burst time.

**Concepts I need to study more:**
1. Thread synchronization and shared-state safety.
2. The difference between a simulated thread dispatch and a real operating-system context switch.

---

# ✅ Final Checklist (complete before submitting)

**Repository**
- [ ] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [ ] Repository is renamed to `OS-Assignment1-YourFirstName-YourLastName`
- [ ] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [ ] Student ID is set in `SchedulerSimulation.java` (line 150)
- [ ] Code compiles and runs with no errors
- [ ] Feature 1 (priority), Feature 2 (context switches) and Feature 3 (waiting time table) all work
- [ ] Each feature has clear comments

**Commits**
- [ ] **At least 3 meaningful commits, ideally 6 or more**
- [ ] **One commit per feature**
- [ ] Commits are spread over **different dates** (not all in the last hour)
- [ ] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [ ] Full name and student ID filled in at the top
- [ ] Development log has **5+ entries** on different dates
- [ ] Reflection: 4 questions, 5-7 sentences each
- [ ] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output
- [ ] No `[...]` placeholders left
- [ ] No section headers deleted

**Video**
- [ ] 2-3 minutes long, named `StudentID_Assignment1_Demo.mp4`
- [ ] Shows your name, ID, repository, 3 features, IDE execution, one threading concept, and commit history
- [ ] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [ ] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.
