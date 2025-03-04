# Goat Simulation

This program simulates the Monty Hall problem using multiple threads to perform a large number of iterations. It compares the outcomes of two strategies: staying with the initial choice and switching to the other door.

## Features

- Multi-threaded simulation for faster execution
- Command-line arguments for customization
- Progress monitoring during the simulation
- Formatted output for readability

## Download

To download goat.exe or goat-fast.exe, download the artifact from the latest action run.

## Requirements

- C++11 or later
- Standard C++ library

## Usage

Compile the program using a C++ compiler:

```sh
cl /EHsc goat.cpp
```

Run the program with the following command-line options:

```sh
goat [options]
```

## Options

- `-t, --threads <number>`: Number of threads to use for the simulation.
- `-i, --iterations <number>`: Number of iterations to run.
- `-im, --iterations-millions <number>`: Number of iterations to run in millions.
- `-ib, --iterations-billions <number>`: Number of iterations to run in billions.
- `-y, --yes`: Skip confirmation prompt before starting the simulation.

## Example

Run the simulation with 4 threads and 10 million iterations:

```sh
goat -t 4 -im 10
```

## Output

The program will display the progress of the simulation, including the number of iterations completed, the number of wins for each strategy, and the time taken per million iterations. At the end of the simulation, it will provide a summary of the results.

On my PC (Ryzen 7 7700), the simulation takes approximately 20 ms per million iterations with 8 threads.

# Goat-Fast

The `goat-fast` version of the simulation uses SIMD (Single Instruction, Multiple Data) instructions to further optimize the performance. This version requires a CPU with AVX512 support.

## Usage

Compile the `goat-fast` program using a C++ compiler with AVX512 support:

```sh
cl /EHsc /arch:AVX512 goat-fast.cpp
```

Run the program with the same command-line options as the standard version:

```sh
goat-fast [options]
```

## Example

Run the `goat-fast` simulation with 4 threads and 10 million iterations:

```sh
goat-fast -t 4 -im 10
```

## Output

The `goat-fast` program will display the progress of the simulation, including the number of iterations completed, the number of wins for each strategy, and the time taken per million iterations. At the end of the simulation, it will provide a summary of the results.

On my PC (Ryzen 7 7700), the `goat-fast` simulation takes approximately 3 ms per million iterations with 8 threads.
