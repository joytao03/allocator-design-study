# Allocator design study
### Implicit vs Explicit Free List Design

## Overview

This project implements and compares two heap memory allocator designs in C:
- **Implicit free list allocator**
- **Explicit free list allocator**

The goal is to explore how different free-list strategies affect allocation efficiency, traversal cost, and memory utilization.

The allocator simulates the behavior of `malloc` and `free` over a contiguous heap region, using low-level pointer arithmetic and custom metadata management.

---

## Features

- Contiguous heap memory simulation
- Boundary-tag metadata (header/footer)
- Block splitting during allocation
- Immediate coalescing on free
- Implicit free-list traversal
- Explicit doubly linked free list
- Trace-driven testing and benchmarking

---

## Project Structure
```text
.
├── src/
│   ├── implicit_allocator.c
│   ├── explicit_allocator.c
│   └── heap_common.c
├── include/
│   └── allocator.h
├── tests/
│   ├── traces/
│   └── benchmark.c
├── docs/
│   ├── design.md
│   └── results.md
├── Makefile
└── README.md
```

---

## Design Overview

### Implicit Free List

- Traverses the entire heap to find a suitable free block
- Simpler implementation
- Higher search overhead for large heaps

### Explicit Free List

- Maintains a doubly linked list of free blocks
- Traverses only free blocks during allocation
- Faster allocation with additional metadata complexity

---

## Allocation Strategy

- First-fit (baseline)
- Optional extensions: next-fit, best-fit

---

## How It Works

### Allocation

1. Search for a suitable free block
2. Split the block if it is larger than required
3. Mark allocated portion as used

### Free

1. Mark block as free
2. Check adjacent blocks
3. Coalesce neighboring free blocks

---

## Benchmarking

The project includes trace-driven tests to evaluate:

- Allocation throughput
- Number of blocks traversed
- Heap utilization
- Fragmentation behavior

---

## Key Insights

- Implicit free lists are simple but scale poorly with heap size
- Explicit free lists significantly reduce traversal cost
- Trade-off between implementation complexity and runtime performance

---

## Skills Demonstrated

- Systems programming in C
- Manual memory management
- Pointer arithmetic
- Data structure design (linked lists)
- Debugging with GDB
- Performance analysis

---

## Future Improvements

- Realloc support
- Segregated free lists
- Best-fit / next-fit comparison
- Heap consistency checker
- Performance visualization

---

## Why This Project Matters

This project reflects core concepts used in:

- Operating systems
- Game engines
- Memory allocators (e.g., malloc implementations)
- Performance-critical systems

---

## Author
Joy Tao
