# Philosophers

A solution to the classic **dining philosophers** concurrency problem in C, using POSIX threads and mutexes. Project of the 42 Common Core.

Each philosopher is a thread, each fork is a mutex. Philosophers eat, sleep and think; the simulation stops as soon as one of them starves or, optionally, when everyone has eaten enough times.

## Highlights

- One thread per philosopher plus a monitor that checks for deaths with millisecond precision
- Fork acquisition order designed to avoid deadlocks; shared state protected against data races
- Thread-safe logging so status messages never overlap
- Edge cases handled (single philosopher, invalid input) and all resources released on exit

## Build & run

```bash
make
./philo <number_of_philosophers> <time_to_die> <time_to_eat> <time_to_sleep> [number_of_meals]
# example
./philo 5 800 200 200
```

Times are in milliseconds.

## What I learned

Multithreading with `pthread`, mutex-based synchronization, deadlock and race-condition prevention, and precise time handling in C.
