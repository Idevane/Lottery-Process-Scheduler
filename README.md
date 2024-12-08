# Lottery Process Scheduler 
 Lottery process scheduler written in C
# DLXOS Lottery Scheduler Project

## Overview

This project involves modifying the **DLXOS** operating system to implement and compare a **lottery scheduling algorithm** with the existing **round-robin preemptive scheduler**. Lottery scheduling provides probabilistic process selection by assigning processes a number of "tickets," which determines the likelihood of a process being chosen for execution. The project also includes profiling both scheduling algorithms to analyze their performance.

---

## Features

- **Lottery Scheduling Implementation:**
  - Processes are assigned tickets proportional to their priority (`p_nice`).
  - Processes with more tickets have a higher probability of being scheduled.
  - Processes with at least one ticket avoid starvation.
  
- **Comparison with Round-Robin Scheduling:**
  - Analyze CPU time allocation for processes under both schedulers.
  - Measure process execution time from creation to termination.

- **Modifications to DLXOS:**
  - New scheduling logic in `ProcessSchedule()` and other related functions.
  - Timer functionality via `my_timer_get()` to track execution timing.

---

## Setup Instructions

1. Copy the project archive:
   ```bash
   mkdir ~/cs314/project2
   cp ~/Public/cs314/project2.tgz ~/cs314/project2/
   ```

2. Extract the archive:
   ```bash
   cd ~/cs314/project2
   tar xvfz project2.tgz
   ```

3. Ensure the following directory is in your PATH:
   ```bash
   /home/cs314/dlxtools/bin/
   ```

4. Compile the project:
   ```bash
   cd ~/cs314/project2/src
   make
   ```

5. Run the simulator from the `execs` directory:
   ```bash
   cd ~/cs314/project3/execs
   ```

---

## Implementation Details

### Lottery Scheduler
- Processes are assigned tickets based on `p_nice` values.
- The scheduler uses `srandom()` and `random()` to select a ticket randomly.
- The number of tickets for each process remains constant throughout its execution.

### Modified Functions
- `ProcessSchedule()`
- `ProcessSuspend()`
- `ProcessWakeup()`
- `ProcessFork()`
- Utility functions for ticket assignment and random selection.

### Timer
- `my_timer_get()` returns the time elapsed in seconds since the simulator started.

---

## Profiling

### Comparison Metrics
- **Round-Robin:** Tracks execution fairness and CPU time allocation.
- **Lottery Scheduling:** Tracks the impact of ticket count on CPU time distribution.

### Data Collection
- `p_info` is used to control the collection of CPU timing data for processes.
- Results are logged and analyzed to demonstrate scheduler behavior and efficiency.

---

## Deliverables

### Group Submission
- **Project Archive (`.tgz`):** Contains:
  - `group.txt`: Group member details.
  - `design.txt`: Design of round-robin and lottery schedulers.
  - `profiles.txt`: Description and results of profiling experiments.

### Individual Submission
- A text file describing:
  - Responsibilities and contributions to the project.
  - Challenges faced.
  - Suggestions for improvement in future projects.

---

## Testing

### Provided User Programs
- Test the implementation using the sample programs in the `project3.tgz` package.
- Follow the usage examples provided in the assignment documentation.

---

## FAQ

### Why use lottery scheduling?
- Ensures fairness while allowing for prioritization based on ticket count.
- Prevents starvation by guaranteeing every process has a non-zero chance of execution.

### What modifications were made to DLXOS?
- Enhanced `ProcessSchedule()` to incorporate ticket-based probabilistic scheduling.
- Added timer functionality to measure execution time for profiling.

---

## Contact

- **Author:** Isaac DeVaney  
- **Email:** isaacdevaney@gmail.com
- **GitHub:** idevane


