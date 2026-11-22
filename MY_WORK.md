# 📝 MY_WORK: Student Information, Development Log, Reflection & Answers

> This is the **only file** your instructor reads to grade Parts 3 and 4 (documentation and video). Everything you write here must be **in your own words**.

---

## 🛑 STOP: Read This Before You Do Anything Else

> ### 1️⃣ Read the whole `README.md` first
> The `README.md` in this repository contains the full instructions: how this assignment continues Assignment 1, the Chapter 5 recap, class descriptions, feature specifications, question prompts and the video script. **If you skip it, you will lose marks.**
>
> ### 2️⃣ Understand the full code before answering any question
> Open `SchedulerSimulationSync.java` and read it **from top to bottom**. You must be able to explain what `SharedStats`, `ReadyQueue`, `CpuWorker`, `RaceWindow.pause()`, `ReentrantLock` and `Semaphore` do **before** you write a single answer in Parts B and C. **Run the original starter first** (it is intentionally broken) and **save its output**: you need it for Question 1 of Part C.
>
> ### 3️⃣ Use only the code of this repository
> Work **only** on `SchedulerSimulationSync.java` from this repository. Do **not** copy or paste code from your previous assignments.
>
> ### 4️⃣ Commit many times, not once
> A single commit, or all commits made in the last hour, costs you **-0.5 mark**. See the [Commit Rules](#-commit-rules-mandatory) below.

**How to use this file:**
1. Fill in your **Student Information** (below) right now.
2. Follow the steps in the **Work Roadmap** in order.
3. Update the **Development Log** *every time* you work on the assignment, not at the end.
4. Do not delete any section header. Replace the `[...]` placeholders with your own text.

---

## 👤 Student Information

> ⚠️ **WARNING:** Fill this in first. Your name and ID must match the student ID you set in `SchedulerSimulationSync.java` (line 304) and the one you say in your video.

| Field | Your Answer |
|-------|-------------|
| **Full Name** | Abdelrahman marwan moustafa noureldin |
| **Student ID** | 446052720 |
| **University Email** | 446052720@std.psau.edu.sa |
| **GitHub Username** | abdelrahman-marwan-hub |
| **Repository Link** | https://github.com/abdelrahman-marwan-hub/OS-Assignment3-Abdelrahman-Noureldin |
 
---

## 🎥 Video Link

**Video Link**: https://youtu.be/wxWa2hVEXuw?si=WO7svZEFpBMnxz3y

> ⚠️ **WARNING:** The video must be **publicly accessible** ("Anyone with the link can view") on **Google Drive**, **YouTube (Unlisted or Public)** or any other cloud file-sharing system. A private, restricted or broken link counts as a **missing video (-1 mark)**.
>
> 💡 **TIP:** Open the link in a **private/incognito window** before you submit. If it asks you to log in or request access, it is not public.
>
> 📌 **NOTE:** The link goes in **this file only** (`MY_WORK.md`), **not** in `README.md`. Name your video file `StudentID_Assignment3_Demo.mp4`. It must last **2 to 3 minutes**.

---

## 🗺️ Work Roadmap (follow in this order)

| Step | What to do | Where | Marks |
|:----:|------------|-------|:-----:|
| 0 | Read `README.md`, read the full code, **run the original starter and save its output** (it fails on purpose) | Your IDE | – |
| 1 | Fork, rename, keep the repo **PUBLIC**, set your student ID (line 304), **commit** | GitHub + code | Part 1 (1) |
| 2 | Feature 1: Mutex lock on the ready queue, **commit** | Code | Part 2 (0.25) |
| 3 | Feature 2: Mutex lock(s) on the shared statistics, **commit** | Code | Part 2 (0.25) |
| 4 | Feature 3: Counting semaphore instead of busy waiting, **commit** | Code | Part 2 (0.5) |
| 5 | Development Log (5+ entries, different dates) | This file, Part A | Part 3 (0.5) |
| 6 | Reflection (4 questions) | This file, Part B | Part 3 (0.5) |
| 7 | Technical Answers (4 questions) | This file, Part C | Part 3 (0.5) |
| 8 | Record the video, upload it, paste the link above | Video + this file | Part 4 (1.5) |
| 9 | Final check, then submit the repo link on Blackboard | Blackboard | – |

> 💡 **TIP:** Tick each step off as you go. Do not leave the log, the reflection or the video for the last day.

---

## 🔁 Commit Rules (MANDATORY)

> ### ⚠️ MANY COMMITS ARE REQUIRED. A single bulk commit is penalized (-0.5 mark).

**Minimum: 4 meaningful commits. Aim for 7 or more.**

| # | Commit | Example message |
|:-:|--------|-----------------|
| 1 | Student ID set | `Set my student ID: 441234567` |
| 2 | Feature 1: Ready queue lock | `Feature 1: Protected the ready queue with a ReentrantLock` |
| 3 | Feature 2: Statistics locks | `Feature 2: Added locks to the shared statistics counters` |
| 4 | Feature 3: Semaphore | `Feature 3: Replaced busy waiting with a counting semaphore` |
| 5 | Development log entries | `Docs: Added development log entries 1-3` |
| 6 | Reflection and answers | `Docs: Completed reflection and technical answers` |
| 7 | Video link | `Docs: Added demo video link` |

**Rules:**
- ✅ **One commit per feature.** Do not put all three features in one commit.
- ✅ **Commit after each work session**, and after each part of this file.
- ✅ **Spread your commits over different dates.** Not all in one day.
- ❌ **Do not make all commits in the last hour** before the deadline (November 14, 2026).
- ❌ **No vague messages** like `done`, `update` or `final version`.

> 💡 **TIP:** Your commit history is checked and you **show it in your video** (at least 4 commits visible). Your development log dates should match your commit dates.
>
> 💡 **TIP:** **Use VS Code** (see *Recommended Development Environment* in `README.md` for the full setup). Sign in to GitHub in VS Code, then commit from the Source Control panel (Ctrl+Shift+G) → stage → write a message → Commit → Sync/Push. You can edit and commit this file the same way. **Pushing** matters: commits that are not pushed to GitHub are invisible to the instructor.

---

# Part A: Development Log (0.5 mark)

> ⚠️ **WARNING:** Minimum **5 entries**, spread over **different dates**. Five entries written on the same day, or written all at once at the end, will lose marks and look like a copy. Entry dates should be **between the start of the assignment and the deadline (November 14, 2026)**.
>
> 💡 **TIP:** Write an entry at the **end of each work session**, while you still remember what happened. It takes 5 minutes.
>
> 💡 **TIP:** Be specific. "Worked on the code" is a weak entry. "Added a `ReentrantLock queueLock` to `ReadyQueue` and wrapped the body of `poll()` in `lock()` / `try` / `finally { unlock() }`" is a strong one.
>
> 📌 **NOTE:** Each entry needs: date and time, what you did, details, challenges, solution, and time spent. Real challenges are fine (and expected). Do not invent fake ones.

## Example Entry (do not copy it, write your own)

### Entry 1 - [November 2, 2026, 4:30 PM]
**What I did**: Forked the repository, set my student ID, and ran the original starter

**Details**:
- Forked the starter repository and renamed it
- Changed student ID on line 304 to my actual ID (441234567)
- Ran the original program: 4 CPUs started, three of them picked `P1`, then `IllegalThreadStateException` and the watchdog stopped the program
- Saved the output in a text file for Question 1
- Committed and pushed: `Set my student ID: 441234567`

**Challenges**: I did not understand why the same process was picked by three CPUs

**Solution**: Read `ReadyQueue.poll()` again and found the `RaceWindow.pause()` between reading the head and removing it

**Time spent**: 45 minutes

---

## Your Development Log

### Entry 1 -  November 20, 2026, 2:30 PM
**What I did**:  i forked the repository, read the assignment files, set my student ID, and ran the starter code.

**Details**:
- i read the README and the assignment files to understand the steps.
- i forked the starter repository to my GitHub account.
- i set my student ID in SchedulerSimulationSync.java.
- i ran the original starter and saved its output.
- i made my first commit: Set my student ID.

**Challenges**:  the starter code failed. four cpus picked P1 at the same time, and i got an IllegalThreadStateException.

**Solution**: i saved the output and read the code again. i found that poll() reads the head of the queue and removes it in two steps, so another cpu can come in the middle.

**Time spent**: 2 hours (2:30 PM – 4:30 PM).

---

### Entry 2 - November 22, 2026, 12:30 AM 
**What I did**: i implemented Feature 1 to protect the ready queue with a ReentrantLock.

**Details**:
- i added a ReentrantLock to the ReadyQueue class.
- i protected add(), poll(), processOf() and snapshot() with the lock.
- i used try and finally, so the lock is always released.
- i ran the program 5 times after the change.

**Challenges**: it was hard to protect poll() correctly, because several cpus use the queue at the same time.

**Solution**: i used one lock to protect the queue operations, so only one thread can access the protected operations at a time. this prevented multiple cpus from accessing and changing the queue at the same time..

**Time spent**:1.5 hours (12:30 AM – 2:00 AM).

---

### Entry 3 - November 22, 2026, 2:00 AM
**What I did**:  i implemented Feature 2 and Feature 3, made separate commits, and checked the program output.

**Details**:
- i added locks to protect the three shared statistics.
- i used separate locks for each counter
- i replaced the busy-waiting loop with a counting Semaphore.
- i added the shutdown mechanism to wake up the cpus.
- i made separate commits for Feature 2 and Feature 3.
- i ran the program and checked the outpt after the changes

**Challenges**: i had difficulty understanding how the semaphore could replace busy waiting and how to wake up the cpus when the simulation finishes.

**Solution**: i used a counting Semaphore to make the cpus wait when no processes are available. i also added a shutdown mechanism to wake up the cpus when the simulation finishes. i used locks to protect the shared statistics.

**Time spent**: 2.5 hours (2:00 AM – 4:30 AM).

---

### Entry 4 -  November 22, 2026, 4:30 AM
**What I did**: updated my personal information in MY_WORK.md.

**Details**:
opened MY_WORK.md in vscode and updated my personal information, including my github username and repository link. then, i committed the changes.

**Challenges**: i needed to make sure that my personal information and repository link were correct.

**Solution**:  i checked my information and updated the file. then, i committed the changes to github.

**Time spent**: 1 hours (4:30 AM – 5:30 AM).

---

### Entry 5 - November 22, 2026, 6:00 AM
**What I did**:  i completed the first three parts of MY_WORK.md.

**Details**:
- i completed the development log entries.
- i wrote the reflection answers.
- i answered the technical questions.
- i reviewed my answers and made some changes to improve them.

**Challenges**: it was hard to make sure that each answer covered all the required points and followed the required number of sentences.

**Solution**: i checked the assignment questions and requirements carefully. i organized my answers and made sure each answer covered the main points.

**Time spent**: 4 hours (6:00 AM – 10:00 AM).

---

### Entry 6 - Optional - November 22, 2026, 10:00 AM
**What I did**: record video 

**Details**:

**Challenges**:

**Solution**:

**Time spent**: 1:30 hours

---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: 12.5 hours

**Most challenging part**:
the most challenging part was understanding the synchronization problems in the starter code and fixing them. it was difficult to protect the ready queue and understand how multiple cpus could access it at the same time.

**Most interesting learning**:
 i learned how ReentrantLock protects shared data and how a counting Semaphore can replace busy waiting. i also learned how synchronization helps prevent race conditions.

**What I would do differently next time**:
 i would start the assignment earlier, read the code more carefully, i would also write my development log after every work session
---

# Part B: Reflection (0.5 mark)

> 🛑 **STOP:** Do **not** start this part until you have read the `README.md`, read the **entire** `SchedulerSimulationSync.java`, run it, and finished the three features.
>
> ⚠️ **WARNING:** Each answer must be **5 to 7 sentences**, in **your own words**. Copied or AI-generated answers without understanding get **0 marks for the whole assignment**. You may be asked to explain them in person.
>
> 💡 **TIP:** Mention concrete things you actually did: a method you wrote, an error you hit, a line of output you saw. Generic answers score low.
>
> 💡 **TIP:** Draft your answer in a few bullet points first, then turn them into sentences.

## Question 1: What did you learn about synchronization?

> 💡 **TIP:** Talk about race conditions (read-modify-write), critical sections, mutual exclusion with `ReentrantLock` and `try/finally`, the role of a counting semaphore, and what surprised you when the starter failed.

**Your Answer:** *(5-7 sentences)*

i learned that synchronization is important when many threads use the same data. a race condition happens whe two threads read and change the same variable at the same time, so one update can be lost.in the starter code, my counters were wrong: context switches were 17 and not 20.i used ReentrantLock to protect the critical sections, so only one thread can enter at a time. i also  learn that unlock() must be in  finally block, because it releases the lock even if an error happens. finally, the Semaphore lets a cpu sleep and wait for a process, instead of checking the empty queue again and again.

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

the most challenging part was protecting the ready queue. in the starter, four cpus picked same process P1 at the same time, and Java gave an IllegalThreadStateException. it was hard because the bug is not easy to see in the code. i had to understand that poll()reads the head of the queue and removes it in two steps, so another cpu can come in the middle.  i also had to protect the list and the map, because both are shared data. after i added the lock to all four methods, every cpu picked a different process.

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

first, i read the code carefully and tried to understand each class. i focused on ReadyQueue and SharedStats because they have the shared data. i read the README to understand each feature before i wrote any code. i ran the starter first and saved its output so i could see the errors. then i added the features one by  onث, and i ran the program 5 times after the changes. i checked the verification block each time, and this helped me understnd how locks and semaphores work in Java.

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

synchronization is used in many real-world applications. in a banking system, a lock can protect an account balance when two people use the same account. in a ticket booking system, synchronization stops two users from booking the same seat. a printer queue is like my ready queue : many programs add jobs and the printer takes them one by one. a semaphore can count the waiting jobs, so the printer sleep when the queue is empty. these examples are similar to my assignment because many threads use shared data or resources..

### Optional: What would you like to learn more about?

[Any topics related to synchronization or operating systems that you're curious about?]

### Optional: How confident do you feel about synchronization concepts now?

[Beginner / Intermediate / Confident. What do you understand well? What needs more practice?]

### Optional: Feedback on the assignment

the assignment was helpful. the starter code made the problem easy to see.

---

# Part C: Technical Answers (0.5 mark)

> 🛑 **STOP:** You cannot answer these questions without understanding the code. Re-read `SchedulerSimulationSync.java` and **run it** first. Your answers must reference **your own code and your own output** (your student ID makes your output and your expected values unique).
>
> ⚠️ **WARNING:** Each answer must be **3 to 5 sentences**, with specific examples from your code or output. Use correct terms: race condition, critical section, mutual exclusion, mutex lock, semaphore, busy waiting, deadlock, producer, consumer.
>
> 💡 **TIP:** Keep the output of the **original starter** and the output of your **final version** in text files or screenshots, so you can copy real snippets for Question 1.

## Question 1: Race Condition in Your Own Output

**Question**: Run the **original starter** (before any fix) and paste the **verification block** of that run. Which value was wrong (expected vs observed)? Explain **step by step**, with two named threads/CPUs, how **one lost update** happens on one of the shared variables (read, `RaceWindow.pause()`, write). Why can the same bug happen on a real machine even without `RaceWindow`, and why is it hard to detect?

> ⚠️ **WARNING:** The snippet must come from **your own run** (with your student ID), not from a classmate or from this README.
>
> 💡 **TIP:** Use a small timeline: *CPU-1 reads `contextSwitchCount` = 12 → CPU-2 reads 12 → CPU-1 writes 13 → CPU-2 writes 13 → one increment is lost.* If your starter run crashed before printing numbers, run it several times (or paste the exception and the watchdog message and explain it).

**Your Answer:** *(3-5 sentences)*

in my starter run, the verification was wrong: context switches were 17 instead of 20, completed processes were 8 instead of 10, and service time was 24053 instead of 29030. busy-waiting polls were 697. a lost update happens when two cpus read the same value before one of them writes it back. the same bug can happen on a real machine without RaceWindow, because a thread can stop between the read and the write. it is hard to find because it happens only sometimes, and the result changes in every run.

Verification block of the **original starter**:
```
⛔ WATCHDOG: the simulation did not finish (19 s). A process was lost, or a CPU is blocked forever, or the 'completed' counter lost an update.

Context switches (quanta executed)     expected 20       observed 17       ✘ MISMATCH
Completed processes                    expected 10       observed 8        ✘ MISMATCH
Total service time (ms)                expected 29030    observed 24053    ✘ MISMATCH
Busy-waiting polls (must be 0)         expected 0        observed 697      ✘ MISMATCH
✘ At least one check failed (see the ✘ lines above): a race condition or busy waiting is still present.
```

Verification block of **my final version**:
```
Context switches (quanta executed)     expected 20       observed 20       ✔
Completed processes                    expected 10       observed 10       ✔
Total service time (ms)                expected 29030    observed 29030    ✔
Busy-waiting polls (must be 0)         expected 0        observed 0        ✔
✔ All shared values are consistent.
```

**Explanation of the timeline:**
this is an example timeline: cpu-1 reads contextSwitchCount = 12. cpu-2 also reads 12 before cpu-1 writes. cpu-1 writes 13, then cpu-2 writes 13. two increments happened, but the counter went up only one time, so one update is lost. ReentrantLock fixes this because only one cpu can do the read and the write at a time.

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

i used queueLock for the four ReadyQueue methods, and three separate locks for the three statistics counters. i chose three locks because the counters are independent, so one update does not wait for another one, but it means more code. the queue has a different lock because it protects different data (the list and the map). a lock gives mutual exclusion because only one thread is inside the critical section, and the next thread enters when the lock is released. the default ReentrantLock is not fair, so one thread can wait longer than the others, and bounded waiting is not guaranteed.

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| `ReadyQueue.add()` | `queueLock` | it adds a thread to the shared list and the map |
| `ReadyQueue.poll()` | `queueLock` | two cpus must not read and remove the same head |
| `ReadyQueue.processOf()` | `queueLock` | it reads the shared map |
| `ReadyQueue.snapshot()` | `queueLock` | it loops over the list and the map |
| `incrementContextSwitch()` and `getContextSwitchCount()` | `contextSwitchLock` | it protects the `contextSwitchCount` counter |
| `incrementCompletedProcess()` and `getCompletedProcessCount()` | `completedProcessLock` | it protects the `completedProcessCount` counter |
| `addServiceTime()` and `getTotalServiceTime()` | `serviceTimeLock` | it protects the `totalServiceTime` value |

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

in the starter, a cpu checked the empty queue and slept 20 ms again and again, and this gave 697 busy-waiting polls. my semaphore value is the number of processes waiting in the ready queue. its initial value is  0 because the queue is empty at the start, and after the 10 add() calls it is 10. at the end, the last cpu calls wakeUpCPUs(),  which releases totalCPUs permits. without this, the other cpus stay blocked in acquire() forevr and the watchdog stops the program.

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*

this is the producer-consumer problem (bounded buffer). the 
producers are main and the cpus that put an unfinished process back in the queue, and the consumers are the cpus that take a process with poll(). for a bounded queue of size K, i need three semaphores: empty, full and mutex. a deadlock can happen if a thread takes the mutex before it waits on a semaphore. to prevent it, i break the hold and wait condition.

**Classical problem and roles**:
producer-consumer (bounded buffer) . producers: main and the cpus that add an unfinished process back. consumers: the cpus that take a process from  the queue

**Semaphores for a bounded queue (name and initial value)**:
empty = K (free places), full = 0 (processes in the queue), mutex = 1 (one thread at a time).

**Deadlock scenario and prevention**:
a producer takes the mutex, then waits for empty  because the queue is full. a consumer needs the mutex to remove a process, so it cannot free a place. both wait forever. to prevent this, i break the hold and wait condition: the producer waits for empty first, and takes the mutex after.

## Summary

**Key concepts I understood through these questions:**
1.a race condition happens when two threads read and write the same data, and one update can be lost. a ReentrantLock with try/finally fixes it.
2.a counting semaphore makes a cpu sleep when the queue is empty, so there is no busy waiting. the last cpu must wake up the others to shut down.
3.the ready queue and the cpus are a producer-consumer problem.

**Concepts I need to study more:**
1.deadlock and the four necessary conditions.
2.fairness and bounded waiting with locks.

---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [ ] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [ ] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [ ] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [ ] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [ ] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [ ] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [ ] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [ ] **The four verification lines are ✔ in 5 consecutive runs**
- [ ] Every lock is released in a `finally` block
- [ ] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [ ] Each feature has clear comments

**Commits**
- [ ] **At least 4 meaningful commits, ideally 7 or more**
- [ ] **One commit per feature**
- [ ] Commits are spread over **different dates** (not all in the last hour)
- [ ] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [ ] Full name and student ID filled in at the top
- [ ] Development log has **5+ entries** on different dates
- [ ] Reflection: 4 questions, 5-7 sentences each
- [ ] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [ ] No `[...]` placeholders left
- [ ] No section headers deleted

**Video**
- [ ] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [ ] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [ ] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [ ] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.
