# Sorting Algorithm Performance Lab 
This project is a C++ command-line tool designed to execute, measure, and compare the performance of various sorting algorithms. It tracks both execution time (in milliseconds) and the number of comparisons made during the sorting process.

## 🛠 Compilation
To build the program, you need a C++ compiler (like `g++`). Navigate to the project directory and run:
```bash
g++ main.cpp process.cpp sorting.cpp -o sorting_program
```
***Note: On Windows, this will generate*** `sorting_program.exe`.

## 🚀 Usage Guide
The program operates in two primary modes: **Algorithm Mode** and **Comparison Mode**.
1. **Algorithm Mode(`-a`)**
Used to analyze the performance of a single sorting algorithm.
* **Using an existing data file:**
```bash
sorting_program -a [algorithm] [file_path] [output_parameter]
```
***Example:*** `sorting_program -a quick-sort input.txt -both`
* **Using auto-generated data:**
```bash
sorting_program -a [algorithm] [input_size] [input_order] [output_parameter]
```
***Example:*** `sorting_program -a merge-sort 50000 -rand -time`
* **Running all data types automatically:**
If you provide a size but omit the input order, the program runs all 4 data scenarios (Random, Sorted, Reverse, Nearly Sorted):
```bash
sorting_program -a [algorithm] [input_size] [output_parameter]
```
2. **Comparison Mode (`-c`)**
Used to compare the performance of two specific algorithms on the same dataset.
* **Compare via file:**
```bash
sorting_program -c [algo_1] [algo_2] [file_path]
```
* **Compare via generated data:**
```bash
sorting_program -c [algo_1] [algo_2] [input_size] [input_order]
```

## 📋 Parameter Reference

**Supported Algorithms**
`selection-sort`, `insertion-sort`, `binary-insertion-sort`, `bubble-sort`, `shaker-sort`, `shell-sort`, `heap-sort`, `merge-sort`, `quick-sort`, `counting-sort`, `radix-sort`, `flash-sort`.

**Input Orders**
| **Parameter** | **Description** |
| :--- | :--- |
| `-rand` | Randomized data |
| `-sorted` | Already sorted data (ascending) |
| `-rev` | Reverse sorted data (descending) |
| `-nsorted` | Nearly sorted data |

**Output Parameters**
| **Parameter** | **Description** |
| :--- | :--- |
| `-time` | Display execution time only (ms) |
| `-comp` | Display number of comparisons only |
| `-both` | Display both time and comparisons |

## 📝 Important Notes
1. **Output File:** In Algorithm Mode (when using a single file), the resulting sorted array is written to `output.txt`.
2. **Performance:** Be cautious when running $O(n^2)$ algorithms (like `bubble-sort` or `selection-sort`) on large datasets (e.g., $n > 100,000$), as they may take a significant amount of time to complete.
