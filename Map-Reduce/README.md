
# Map-Reduce Inventory Analysis

This project simulates a distributed inventory and profit tracking system using a **Map-Reduce architecture** implemented in C++. The system reads data from multiple CSV files, processes them in parallel across child processes using `fork`, `exec`, and `pipe`, and generates real-time inventory and profit reports for a supply company.

## Objectives

- Learn and apply inter-process communication using unnamed and named pipes.
- Simulate real-world inventory tracking and order fulfillment using the Map-Reduce model.
- Practice process creation (`fork`, `exec`) and stream redirection in a Unix-based system.

## Problem Overview

A food distribution company manages inventory across multiple warehouses in different cities. Each warehouse logs transactions (`input`/`output`) in its own CSV file. The goal is to:

- Track stock levels per item, per warehouse.
- Calculate profit from items sold based on transaction types and item prices.
- Generate final reports both for each warehouse and a unified master report.
- Each line contains: `<item>,<quantity>,<unit_price>,<type>`

## Implementation Details

- Each warehouse CSV file is handled by a **child process**.
- **Map Phase**: Each process parses its file, extracts item-level inventory and profit info, and sends the result via a pipe.
- **Reduce Phase**: The parent process collects all results and aggregates them into a consolidated report.

## Communication

- Pipes (`pipe()`) are used to transfer structured output between child and parent processes.
- Each message includes:
  - Item name
  - Quantity available
  - Total profit
- `parts.csv` is read to obtain a global list of all possible items.

## Features

- Interactive CLI interface for user input and output.
- Real-time pipe-based IPC.
- Correct handling of input/output order to ensure logical consistency (FIFO).
- Supports unlimited number of warehouse files.
- Handles edge cases like reordering and repeated inputs cleanly.

## 📋 Output

- Per warehouse: item stock status and total profit
- Global master report aggregating all warehouse data
- All logs redirected for review and debugging

---

> Developed for the **Operating Systems** course – Fall 2024  
> University of Tehran | Department of Electrical and Computer Engineering  