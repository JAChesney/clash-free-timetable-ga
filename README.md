# 🧬 Clash-Free Timetable Scheduling using Genetic Algorithms (Version 1.0)

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

A **"collision"** occurs if a teacher is assigned to both timetables at the **same time slot**.

---

### 🔁 Genetic Operators

- **Selection**  
  ✔️ Uses **random selection only**  
  ❌ No tournament, rank-based, or roulette wheel selection

- **Crossover**  
  ✔️ Randomly generates valid children bit strings  
  ✔️ Ensures exact teaching hours per teacher

- **Mutation**  
  ✔️ Randomly mutates valid strings  
  ✔️ Maintains the 3-period rule

---

### 🧭 Where Genetic Algorithms Fit in Analytics?

This project leverages **Genetic Algorithms (GAs)**, which are a part of **Prescriptive Analytics** in the data analytics hierarchy.

#### 🔍 Analytics Categories

1. **Descriptive Analytics** – What happened?  
2. **Diagnostic Analytics** – Why did it happen?  
3. **Predictive Analytics** – What is likely to happen?  
4. **Prescriptive Analytics** – What should we do?

> Genetic Algorithms are categorized under **Prescriptive Analytics** because they are used to find the **best possible action or solution** for a given problem.

In this project, the GA is used to **prescribe optimal, clash-free class schedules** by:
- Exploring all valid combinations of teacher assignments  
- Evolving the population toward conflict-free solutions  
- Using fitness-based feedback to guide decision-making  

This makes GAs a powerful optimization tool in educational planning and scheduling scenarios.

---

### 🔄 Evolution Process

- Starts with an initial population from CSV files: `see1.csv`, `see2.csv`  
- Repeats genetic operations until:
  - ✅ Both schedules are valid  
  - ✅ No overlapping teacher assignments  
  - ✅ Fitness score reaches `1.0`

---

### 📊 Output

Two optimized, clash-free schedules are generated and visualized as **binary heatmaps**:

- **X-axis** → Days × Periods  
- **Y-axis** → Teachers  
- **Black** = Assigned class
- **White** = Free period

Sample Output:

![image](https://github.com/user-attachments/assets/32b7b437-1980-45fb-ad49-2c32a7456122)

---
## ▶️ How to Run

1. Clone this repository:

   ```bash
   git clone https://github.com/JAChesney/clash-free-timetable-ga-v1.git
   ```
   
2. Install dependencies:
   
   ```bash
   pip install numpy pandas matplotlib
   ```
   
4. Run the script:
   ```bash
   python time_table.py
   ```
   
---

## 🚫 Limitations

- Fixed to 3 teachers, 3 days, and 3 periods per day.
- Teaching hours are hard-coded to 3 per teacher.
- Only supports generation of 2 timetables at a time.
- Uses purely random selection, mutation, and crossover methods.
- Not suitable for large or real-time scheduling needs.

---

### 💻 Tech Stack

- ![Python](https://img.shields.io/badge/-Python-3776AB?style=flat&logo=python&logoColor=white)
- ![NumPy](https://img.shields.io/badge/-NumPy-013243?style=flat&logo=numpy&logoColor=white)
- ![Pandas](https://img.shields.io/badge/-Pandas-150458?style=flat&logo=pandas&logoColor=white)
- ![Matplotlib](https://img.shields.io/badge/-Matplotlib-ffffff?style=flat&logo=matplotlib&logoColor=black)

---

### 📚 References

- *A Review of Optimization Algorithms for University Timetable Scheduling* – Umm Al Qura University  
- *Learning Genetic Algorithms with Python* by Ivan Gridin
