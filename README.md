

# CPU Scheduling Simulator

A simulator that implements and compares **Priority Scheduling** and **Shortest Remaining Time First (SRTF)** on identical workloads, producing Gantt charts, per-process metrics, and a structured performance analysis.

Built for the Operating Systems course — Project C1.

---

## The Development Team

| Name | GitHub Profile |
| :--- | :--- |
| **fady selim** | [@fadyselimz](https://github.com/fadyselimz) |
| **nour elfeky** | [@nourelfeky](https://github.com/nourelfeky) |
| **abdulrahman nady** | [@Abdo_Nady](https://github.com/AbdoNady14) |
| **Jana Amin** | [@janaadarwish](https://github.com/janaadarwish) |
| **yahia** | [@yahia-10](https://github.com/yahia-10) |
| **mohammed alaa** | [@Mohamed3laaa](https://github.com/Mohamed3laaa) |

---

## Table of Contents

- [Project Overview](#project-overview)
- [Algorithms](#algorithms)
- [Features](#features)
- [Input Specification](#input-specification)
- [Validation Rules](#validation-rules)
- [Test Scenarios](#test-scenarios)
- [Metrics Computed](#metrics-computed)
- [How to Run](#how-to-run)
- [Project Structure](#project-structure)

---

## Project Overview

This project addresses the comparison between a **policy-driven scheduler** (Priority) and an **efficiency-driven preemptive scheduler** (SRTF). Both algorithms are executed on the same process workload, and their outputs are compared across waiting time, turnaround time, response time, fairness, and starvation risk.

---

## Algorithms

### Priority Scheduling

Selects the ready process with the highest priority at every scheduling decision. The scheduler is preemptive — if a higher-priority process arrives while another is running, the CPU is immediately reassigned.

- **Tie-breaking rule:** Earlier arrival time takes precedence. If arrival times are equal, the lower Process ID is selected.

### Shortest Remaining Time First (SRTF)

A preemptive variant of Shortest Job First. At every time unit, the scheduler selects the process with the shortest remaining burst time. A newly arriving process preempts the current process if its remaining burst is shorter.

---

## Features

- Accepts a dynamic number of processes at runtime with no hardcoded data
- Simulates both algorithms on the same input workload
- Renders separate Gantt charts for Priority Scheduling and SRTF
- Displays per-process and average metrics for both algorithms side by side
- Performs full input validation before simulation begins
- Outputs a structured comparison summary and conclusion

---

## Input Specification

| Field          | Type    | Required        |
|----------------|---------|-----------------|
| Process ID     | String  | All projects    |
| Arrival Time   | Integer | All projects    |
| Burst Time     | Integer | All projects    |
| Priority Value | Integer | C1 (this project) |

---

## Validation Rules

The simulator rejects the following inputs with descriptive error messages:

- Negative arrival times
- Zero or negative burst times
- Duplicate Process IDs
- Missing or non-numeric values in numeric fields
- Invalid priority values

Simulation does not begin until all input passes validation.

---

## Test Scenarios

| Scenario | Description |
|----------|-------------|
| A — Basic Mixed Workload | Standard workload with varied arrival and burst times across multiple processes |
| B — Priority-Burst Conflict | A high-priority long process competes with a low-priority short process to expose behavioral differences |
| C — Starvation-Sensitive Case | A workload where one process risks extended waiting under one of the two policies |
| D — Validation Case | Demonstrates rejection of invalid input with appropriate error handling |

---

## Metrics Computed

For each algorithm and each process:

- **Waiting Time (WT)** — total time spent in the ready queue
- **Turnaround Time (TAT)** — total time from arrival to completion
- **Response Time (RT)** — time from arrival to first CPU assignment

Averages are reported for WT, TAT, and RT across all processes for both algorithms.

---
How to Run

Open the `index.html` file in any web browser.

You can also run it using VS Code Live Server:
1. Open the project folder in VS Code
2. Right click on `index.html`
3. Select "Open with Live Server"

Project Structure

your-project-folder/
│
├── index.html
├── Comparison_Report.word
├── Test_Cases/
│   ├── test1.png
│   ├── test2.png
│   ├── test3.png
│   └── test4.png
│
└── README.md

Description

- `index.html` contains the complete project implementation including HTML, CSS, and JavaScript in a single file.
- `Comparison_Report.word` contains the project report and comparison details.
- `Test_Cases` folder contains screenshots/photos of the test cases used in the project.



