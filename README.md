# Go Race Condition Example

This repository demonstrates a common race condition in Go when using counters in goroutines without proper synchronization mechanisms.

## Problem

The `bug.go` file shows a simple program that attempts to sum numbers concurrently using goroutines.  Because `count` is not protected by a mutex, multiple goroutines can modify it simultaneously, leading to unpredictable results.

## Solution

The `bugSolution.go` file provides a corrected version of the program.  It uses a `sync.Mutex` to protect access to the `count` variable, ensuring that only one goroutine can modify it at a time. 

## How to run

1.  Clone this repository.
2.  Navigate to the repository directory.
3.  Run `go run bug.go` to see the race condition in action.  The result will likely be incorrect.
4.  Run `go run bugSolution.go` to see the correct, synchronized version of the code.  The result will be 499500.
