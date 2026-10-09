# 📝 MY_WORK: Student Information, Development Log, Reflection & Answers

> This is the **only file** your instructor reads to grade Parts 3 and 4 (documentation and video). Everything you write here must be **in your own words**.

---

## 🛑 STOP: Read This Before You Do Anything Else

> ### 1️⃣ Read the whole `README.md` first
> The `README.md` in this repository contains the full instructions: class descriptions, feature specifications, question prompts and the video script. **If you skip it, you will lose marks.**
>
> ### 2️⃣ Understand the full code before answering any question
> Open `SchedulerSimulation.java` and read it **from top to bottom**. You must be able to explain what `Process`, `run()`, `runToCompletion()`, `addProcessToQueue()`, `Thread.start()`, `Thread.join()` and `Thread.sleep()` do **before** you write a single answer in Parts B and C. Run the program at least once and watch the output.
>
> ### 3️⃣ Commit many times, not once
> A single commit, or all commits made in the last hour, costs you **-0.5 mark**. See the [Commit Rules](#-commit-rules-mandatory) below.

**How to use this file:**
1. Fill in your **Student Information** (below) right now.
2. Follow the steps in the **Work Roadmap** in order.
3. Update the **Development Log** *every time* you work on the assignment, not at the end.
4. Do not delete any section header. Replace the `[...]` placeholders with your own text.

---

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
---

## 🔁 Commit Rules (MANDATORY)

| Commit | Message |
|---|---|
| 1 | `Set my student ID: 446051748` |
| 2 | `Feature 1: Added priority field to Process class` |
| 3 | `Feature 2: Implemented context switch counter` |
| 4 | `Feature 3: Added waiting time tracking and summary table` |
| 5 | `Docs: Added development log` |

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

### Entry 6 - [Optional - Date and Time]
**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: [X hours]

**Most challenging part**:

**Most interesting learning**:

**What I would do differently next time**:

---

# Part B: Reflection (0.5 mark)

> 🛑 **STOP:** Do **not** start this part until you have read the `README.md`, read the **entire** `SchedulerSimulation.java`, run it, and finished the three features.
>
> ⚠️ **WARNING:** Each answer must be **5 to 7 sentences**, in **your own words**. Copied or AI-generated answers without understanding get **0 marks for the whole assignment**. You may be asked to explain them in person.
>
> 💡 **TIP:** Mention concrete things you actually did: a method you wrote, an error you hit, a line of output you saw. Generic answers score low.
>
> 💡 **TIP:** Draft your answer in a few bullet points first, then turn them into sentences.

## Question 1: What did you learn about multithreading?

> 💡 **TIP:** Talk about thread creation (`Runnable`, `Thread.start()`), waiting with `Thread.join()`, simulating work with `Thread.sleep()`, and what surprised you.

**Your Answer:** *(5-7 sentences)*

[Write your answer here.]

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding the code, one of the features, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

[Write your answer here.]

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading documentation, adding `System.out.println` to debug, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

[Write your answer here.]

## Question 4: How can you apply multithreading concepts in real-world applications?

> 💡 **TIP:** Use real applications you know (web browser, game, mobile app, music player) and connect each one to what you built here.

**Your Answer:** *(5-7 sentences)*

[Write your answer here.]

### Optional: What would you like to learn more about?

[Any topics related to threading or operating systems that you're curious about?]

### Optional: How confident do you feel about multithreading concepts now?

[Beginner / Intermediate / Confident. What do you understand well? What needs more practice?]

### Optional: Feedback on the assignment

[Any comments? Was it helpful? Too easy or hard? Suggestions?]

---

# Part C: Technical Answers (0.5 mark)

> 🛑 **STOP:** You cannot answer these questions without understanding the code. Re-read `SchedulerSimulation.java` and **run it** first. Your answers must reference **your own code and your own output** (your student ID makes your output unique).
>
> ⚠️ **WARNING:** Each answer must be **3 to 5 sentences**, with specific examples from your code or output. Use correct terms: thread, process, time quantum, ready queue, context switch, burst time.
>
> 💡 **TIP:** Keep your program output in a text file or screenshot so you can copy real snippets for Question 2.

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes? Mention at least **TWO** specific differences (e.g., memory sharing, creation overhead, communication speed), and reference relevant parts of `SchedulerSimulation.java`.

> 💡 **TIP:** Note that the class named `Process` in our code is a *simulated* process, and it is run by a real Java *thread*. Explain that distinction and point to the `new Thread(process)` line in `addProcessToQueue()`.

**Your Answer:** *(3-5 sentences)*

[Write your answer here.]

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from **your** program output, including **how many times that process was re-queued** before it finished, and explain why re-queueing matters for fairness.

> ⚠️ **WARNING:** The output snippet must come from **your own run** (with your student ID), not from a classmate or from this README.
>
> 💡 **TIP:** Pick a process with a large burst time (e.g., more than 2 × time quantum) and count how many "added to ready queue" lines it has after the first one. Search your console for its name (e.g., `P3`).

**Your Answer:** *(3-5 sentences)*

[Write your answer here.]

Example from my output:
```
[Paste a relevant snippet from your program output here showing a process being re-queued]
```

**Explanation of example:**
[Explain what is happening in the output snippet you pasted.]

## Question 3: Thread Lifecycle

**Question**: A thread goes through these states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (e.g., P1) from your simulation. For each state, explain **when** P1 enters it and **which line or method call** triggers the transition (`Thread.start()`, `Thread.join()`, `Thread.sleep()`, etc.).

> 💡 **TIP:** Follow P1 through the code: created in `addProcessToQueue()`, started in the scheduler loop, sleeping inside `run()`, and the main thread waiting on `join()`. Remember that **the main thread waits** on `join()`, while **P1's thread sleeps** in `Thread.sleep()`. Be clear about which thread is in which state.

**Your Answer:** *(3-5 sentences overall; one short explanation per state)*

1. **New**: [When is P1 in the New state?]

2. **Runnable**: [When does P1 become Runnable?]

3. **Running**: [When is P1 Running?]

4. **Waiting**: [When and why would a thread be Waiting?]

5. **Terminated**: [When is P1 Terminated?]

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. **At least one** must be an operating-system-level scenario (e.g., how an OS scheduler shares CPU time among running programs). The second can be any application you choose. For each, explain what the system is and **why Round-Robin fits** (fairness, responsiveness, predictability).

> 💡 **TIP:** Relate each example back to your simulation: what plays the role of the "process", the "time quantum" and the "context switch" in that scenario?

**Your Answer:** *(3-5 sentences per example)*

### Example 1 (operating-system level): [Name of scenario]

**Description**:
[Describe the real-world scenario.]

**Why Round-Robin works well here**:
[Fairness, responsiveness, predictability?]

### Example 2: [Name of application/scenario]

**Description**:
[Describe the real-world scenario or application.]

**Why Round-Robin works well here**:
[Fairness, responsiveness, predictability?]

## Summary

**Key concepts I understood through these questions:**
1.
2.
3.

**Concepts I need to study more:**
1.
2.

---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Late submission costs **-1 mark per day**, and the deadline is **October 10, 2026**.

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
