# 🧬 Clash-Free Timetable Scheduling using Genetic Algorithms

This project demonstrates the use of a **Genetic Algorithm (GA)** to generate **two clash-free timetables** over **3 days**, with **3 periods each day**, and **3 teachers**. The aim is to optimize schedules while avoiding conflicts, ensuring that no teacher is double-booked at the same time in either timetable.

## 📚 Scenario

- 3 Teachers  
- 3 Days  
- 3 Periods per Day  
- Each teacher teaches for exactly 3 hours (1 period per day)  

---

## 🧠 Problem Statement

Generate **two valid class schedules** such that:

- Teachers are not assigned to two periods at the same time (no collision).  
- Both schedules are independent (no shared teacher slots).  
- Total teaching time per teacher is exactly 3 hours.  
- Final fitness score = **1.0** (indicates no clash).  

---

## ⚙️ How the Genetic Algorithm Works

### 📌 Chromosome Representation

- Each schedule is a binary matrix (teacher × slots).  
- A `1` at position *(i, j)* means Teacher `i` teaches in slot `j`.  

### 🔍 Fitness Function

```python
Fitness = 1 / (1 + Collision Count)
```
A "collision" occurs if a teacher is assigned to both timetables at the same slot.

🔁 Genetic Operators
Selection
✔️ Random selection only (no tournament, rank-based, or roulette wheel selection).

Crossover
✔️ Randomly generates binary children (teacher schedules) with exact total teaching hours.

Mutation
✔️ Randomly generates valid bit strings ensuring hour constraints are met.

🔄 Evolution Process
Starts with an initial population from .csv files (see1.csv, see2.csv).

Repeats selection, crossover, and mutation until:

Both schedules are valid

No overlapping teacher assignments

Fitness score reaches 1.0

📊 Output
Two visual class schedules are shown with binary heatmaps:

X-axis: Days and Periods

Y-axis: Teachers

Black = Free, White = Assigned

💻 Tech Stack
Python 🐍

NumPy

Pandas

Matplotlib

🙏 Acknowledgements
Praveen Kumar

Jayati Kaushik

Class of BDA 2022–2024

📚 References
A Review of Optimization Algorithms for University Timetable Scheduling – Umm Al Qura University

Learning Genetic Algorithms with Python by Ivan Gridin

---
