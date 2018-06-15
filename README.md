# Dining Philosophers

## Compile
$ gcc dining.c -o dining

## Run
$ ./dining <number of philosophers> <number of times a philosopher should eat>

## Algorithm Explanation
I use a resource hierarchy solution to solve the dining philosophers problem. In particular, I create threads for each philosopher and mutexes for each chopstick, then in the thread for each philosopher, they think, pick up the chopstick with the lowest number, then the highest number, and if they got both they eat. Once they are done eating (specified by a random sleep() number), they give back the largest numbered chopstick, then the smallest number chopstick.

The chopsticks are numbered from 0 to the number of philosophers - 1. The philosophers only have access to the chopstick with the same number as their ID and the one with the number greater than their ID, or zero for the philosopher with the greatest ID.

## Assumptions
- The number of philosophers will fit on the stack
- Efficiency is not important
- The number of chopsticks in known at the beginning
