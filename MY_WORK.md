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
| **Full Name** | Renad Fahad Alghamdi |
| **Student ID** | 446051308 |
| **University Email** | 446051308@std.psau.edu.sa |
| **GitHub Username** | Renad-Fahad-308 |
| **Repository Link** | [Paste your repository link here] |
 
---

## 🎥 Video Link

**Video Link**: [Paste your video link here]

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

### Entry 1 - [November 13, 2026, 7:11 AM]
**What I did**:  I updated my student ID in the Java code

**Details**: I opened SchedulerSimulationSync.java and found the studentID variable and I replaced the default number with my university ID and saved the change on GitHub

**Challenges**: I needed to find the correct variable and make sure I did not change anything else


**Solution**: I checked the studentID line and reviewed the code before saving my change

**Time spent**: 35 minutes



---

### Entry 2 - [November 13, 2026, 12:21 PM]
**What I did**: I started Feature 1 by adding a lock to the ready queue

**Details**: I imported ReentrantLock and created queueLock inside the ReadyQueue class. I used it to help protect the shared queue

**Challenges**: I was not sure at first where I should add the lock in the class

**Solution**: I looked at the ReadyQueue variables and added queueLock in the correct place

**Time spent**: 30 minutes



---

### Entry 3 - [November 13, 2026, 12:27 PM]
**What I did**: I added locking to the ready queue methods

**Details**: I protected add(), poll(), processOf(), and snapshot() using queueLock. I also used try and finally to make sure the lock is released after each method

**Challenges**:  I had to check the brackets carefully because each method had different code inside it

**Solution**:  I updated the methods one at a time and checked the lock and unlock statements before moving to the next method

**Time spent**: 1 hour


---

### Entry 4 - [November 14, 2026, 8:09 AM]
**What I did**:  I worked on Feature 2 to protect the shared statistics

**Details**: I added statsLock in SharedStats. I used one lock for contextSwitchCount, completedProcessCount, and totalServiceTime. I protected the methods that read and update these values

**Challenges**:  I needed to understand how one lock could protect three different counters

**Solution**:  I used the same statsLock in the six methods and made sure each method releases the lock using finally

**Time spent**: 1 hour


---

### Entry 5 - [November 15, 2026, 11:45 PM]
**What I did**: I added a Semaphore for Feature 3

**Details**:  I imported Semaphore and changed the CPU waiting code. I used it to help the CPU threads wait for processes instead of checking the ready queue many times

**Challenges**: Understanding how the CPU threads wait and continue working with a Semaphore took me some time

**Solution**:  I changed the waiting logic to use the Semaphore and added code to help the CPU threads finish when the work is done

**Time spent**: 1 hour


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

**Total time spent on assignment**: 4 hours and 5 minutes


**Most challenging part**: The hardest part for me was understanding where to add the locks and how to use them in the different methods

**Most interesting learning**:  I learned how ReentrantLock can protect shared data and how Semaphore helps CPU threads wait for work

**What I would do differently next time**: I would read the code more carefully before making changes and test each feature after finishing it

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
I learned that synchronization helps threads work safely when they use shared data. Before this assignment .I did not know how threads could affect each other when they run together. I understood that a race condition can happen when threads access the same data at the same time. In my code I used ReentrantLock to protect the ready queue and shared statistics I also learned why we use try-finally to release the lock. The Semaphore helped me understand how CPU threads can wait for a process instead of repeatedly checking the queue.




## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*
The most challenging part for me was understanding where I needed to add the locks. At first, I was not sure which parts of the code needed protection. I had to carefully check the add, poll, processOf, and snapshot methods. I also needed to make sure the lock was released after each method finished. Another part that needed attention was protecting the shared statistics. I learned that even a small mistake in the lock placement could cause a problem.



## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

I started by reading the code and understanding what each method does. Then I added the locks step by step instead of changing everything at once. I checked the opening and closing brackets after each change. For the shared statistics, I used one statsLock to protect the three counters. I also checked how the Semaphore was used to control CPU waiting. Working on each feature separately made the code easier for me to understand.


## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*
Synchronization is useful in applications where many users access the same information. For example, an online shopping website needs to update the number of available products correctly. If two customers buy the last item at the same time, the system must prevent incorrect updates. A lock can help protect the shared product quantity. Synchronization is also useful in a printer queue because many people may send documents at the same time. This reminds me of the ready queue in my assignment where I used a lock to protect shared data.


### Optional: What would you like to learn more about?

[Any topics related to synchronization or operating systems that you're curious about?]

### Optional: How confident do you feel about synchronization concepts now?

[Beginner / Intermediate / Confident. What do you understand well? What needs more practice?]

### Optional: Feedback on the assignment

[Any comments? Was it helpful? Too easy or hard? Suggestions?]

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
When I tested the original starter code, CPU-1 and CPU-2 both picked P1, and CPU-1 showed an IllegalThreadStateException. The simulation did not finish, and the watchdog stopped it after 28 seconds. The verification showed 29 context switches instead of 32 and 13 completed processes instead of 14. This happened because the shared queue was not protected so that both CPUs could pick the same process. RaceWindow.pause() increases the chance of this problem, but the race condition can still happen without it because of thread timing.

Verification block of the **original starter**:
```
Exception in thread "CPU-1" java.lang.IllegalThreadStateException
    at java.base/java.lang.Thread.start(Thread.java:1389)
    at CpuWorker.run(SchedulerSimulationSync.java:283)

? WATCHDOG: the simulation did not finish (28 s). A process was lost, or a CPU is blocked forever, or the 'completed' counter lost an update.

??? VERIFICATION (expected values are computed from YOUR seed) ???
Context switches (quanta executed)    expected 32      observed 29      ? MISMATCH
Completed processes                   expected 14      observed 13      ? MISMATCH
Total service time (ms)               expected 46053   observed 41891   ? MISMATCH
Busy-waiting polls (must be 0)        expected 0       observed 977     ? MISMATCH
? At least one check failed (see the ? lines above): a race condition or busy waiting is still present
```

Verification block of **my final version**:
```
??? VERIFICATION (expected values are computed from YOUR seed) ???
Context switches (quanta executed)    expected 32      observed 32      ?
Completed processes                   expected 14      observed 14      ?
Total service time (ms)               expected 46053   observed 46053   ?
Busy-waiting polls (must be 0)        expected 0       observed 0       ?
? All shared values are consistent.
```

**Explanation of the timeline:**
For example, CPU-1 reads contextSwitchCount as 5, and CPU-2 reads the same value before it changes. CPU-1 adds 1 and saves 6. CPU-2 also adds 1 using the old value and saves 6 instead of 7. This causes a lost update because both CPUs changed the same counter without a lock. A ReentrantLock prevents this by allowing only one CPU to update the counter at a time

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*
In my code,I used queueLock to protect add(), poll(), processOf(), and snapshot() because both CPUs use the same ready queue. For the statistics, I chose one statsLock for contextSwitchCount,completedProcessCount, and totalServiceTime to keep the updates and reads safe, although separate locks could reduce unnecessary waiting. I kept the queue lock separate from the statistics lock so each part can work without waiting for the other.These locks provide mutual exclusion, and threads can make progress when the needed lock is released.Since I used the default ReentrantLock, it does not guarantee fairness or bounded waiting so that a thread could wait longer than others

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| ReadyQueue: add(), poll(), processOf(), snapshot() |  queueLock | To keep the shared queue safe when both CPUs access it|
| SharedStats: contextSwitchCount, completedProcessCount, totalServiceTime (updates and reads) | statsLock  | To protect the counters and avoid incorrect results |

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

In the original starter, the CPUs repeatedly checked the ready queue when it was empty, wasting CPU time; my output showed 977 busy-waiting polls. I used a counting Semaphore to track how many processes were ready, so the CPUs could wait with acquire() instead of continuously checking the queue. Its initial value is 0 because the queue starts empty, and after adding the first 14 processes, it reaches 14 if no CPU has taken a permit yet. Each time a process is added, release() adds a permit, while acquire() takes one when a CPU is ready to get a process. At the end, release(totalCPUs) wakes any CPUs blocked in acquire() so they can stop, but without it, some CPU threads could remain blocked and prevent the simulation from ending.

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*

**Classical problem and roles**:
My scheduler is an example of the Producer-Consumer problem. The main thread produces processes by adding them to the queue, while the CPUs consume processes and also act as producers when they put unfinished processes back into the queue.

**Semaphores for a bounded queue (name and initial value)**:
If the ready queue has a capacity of K, the three semaphores would be: empty = K (available spaces), full = 0 (ready processes), and mutex = 1 (protecting the queue).

**Deadlock scenario and prevention**:
A deadlock may occur when a producer takes the mutex before waiting for space in a full queue, preventing the consumer from getting the mutex to remove a process. To avoid this, I would break the hold-and-wait condition by waiting for an empty slot before locking the queue.

## Summary

**Key concepts I understood through these questions:**
1. I learned how race conditions happen when two CPUs access shared data at the same time
2. I understood how ReentrantLock protects the ready queue and shared statistics
3. I learned how a semaphore reduces busy waiting and helps CPUs work correctly

**Concepts I need to study more:**
1. I need more practice understanding deadlocks and how to prevent them
2. I want to understand fair and unfair locks better

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
