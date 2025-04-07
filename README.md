# 🧬 Clash-Free Timetable Scheduling using Genetic Algorithms

This project demonstrates the use of a **Genetic Algorithm (GA)** to generate **two clash-free timetables** over **3 days**, with **3 periods each day**, and **3 teachers**. The aim is to optimize schedules while avoiding conflicts, ensuring that no teacher is double-booked at the same time in either timetable.

## 📌 Features

- Generates **two independent timetables**.
- Applies **Genetic Algorithm** principles: selection, crossover, and mutation.
- Ensures **no teacher clash** within and between timetables.
- Encodes timetable entries as **bit strings**.
- Evaluates fitness based on **clash count** and **validity**.
- Supports **expansion** for more teachers, periods, and days.

## 📘 Problem Definition

- **Days**: 3 (e.g., Monday, Tuesday, Wednesday)
- **Periods per day**: 3 (i.e., total of 9 slots per timetable)
- **Teachers**: 3 (T1, T2, T3)
- **Objective**: Generate 2 schedules such that:
  - No teacher appears in more than one class per period.
  - Both schedules are **completely independent** (no teacher overlap at the same time).

## 🛠️ How It Works

1. **Encoding**: Each timetable is encoded into a bit string, representing teacher assignments for each period.
2. **Population Initialization**: A number of candidate solutions (chromosomes) are randomly generated.
3. **Fitness Evaluation**: Clash-free schedules are scored higher.
4. **Selection**: Best individuals are selected based on fitness.
5. **Crossover**: Parts of two parents are combined to form new offspring.
6. **Mutation**: Some bits are randomly flipped to maintain diversity.
7. **Replacement**: The new generation replaces the old, and the process repeats until convergence or the max generation is reached.

## 🧪 Example Output

Schedule 1: Day 1: T1 | T2 | T3 Day 2: T2 | T1 | T3 Day 3: T3 | T1 | T2
Schedule 2: Day 1: T2 | T3 | T1 Day 2: T1 | T3 | T2 Day 3: T3 | T2 | T1

✅ Both schedules are clash-free  
❌ No overlapping teacher in the same period across both timetables

## 📂 Project Structure

timtable/ ├── main.py # Entry point and execution logic ├── timetable.py # Timetable representation and fitness evaluation ├── ga.py # Genetic algorithm logic ├── utils.py # Helper functions └── README.md # Project documentation


## 🚀 Getting Started

1. Clone the repo:
   ```bash
   git clone https://github.com/yourusername/genetic-timetable.git
   cd genetic-timetable

python main.py
