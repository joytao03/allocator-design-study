# Heap_Memory_Allocator

This project implements a simple heap memory allocator in C, inspired by the behavior of `malloc` and `free`.

## Features
- Implicit free list
- Block splitting
- Block coalescing
- Boundary-tag-based metadata management

## Overview
The allocator manages a contiguous heap region and supports dynamic allocation and deallocation. It tracks block metadata to identify free and allocated regions, and merges adjacent free blocks to reduce fragmentation.

## Skills Demonstrated
- C programming
- Memory management
- Pointer arithmetic
- Low-level debugging with GDB

## Status
Project structure and documentation are being prepared. Additional implementation details and examples will be added.
