# Comparative Study of Parallel Programming Frameworks for HPC Architectures (umd-714-project)

This project compares several parallel programming frameworks for high-performance computing workloads on an AMD-based HPC cluster.

## Overview

The project evaluates both shared-memory and distributed-memory parallel programming models using scientific benchmarks. The goal is to compare performance, scalability, and implementation trade-offs across different frameworks.

Evaluated frameworks:

- OpenMP
- Intel oneTBB
- C++ Parallel STL
- OpenMPI
- Intel MPI

Experiments were conducted on the University of Maryland Zaratan HPC cluster using AMD EPYC 7763 compute nodes.

## Benchmarks

### Shared-Memory Benchmarks

NAS Parallel Benchmarks:

- SP
- BT
- LU

These benchmarks were used to compare OpenMP, Intel oneTBB, and C++ Parallel STL.

### Distributed-Memory Benchmarks

SPEC HPC 2021 benchmarks:

- LBM
- SOMA
- Tealeaf
- Cloverleaf
- MiniSweep
- POT3D
- HPGMG-FV
- miniWeather

These benchmarks were used to compare OpenMPI and Intel MPI across multiple nodes.

## Methodology

The shared-memory benchmarks were implemented and evaluated using different threading frameworks. The MPI benchmarks were executed with different rank and node configurations using SLURM job scripts.

Profiling and bottleneck analysis were performed using:

- Intel VTune Profiler
- HPCToolkit
- Custom MPI instrumentation wrappers

The analysis focused on runtime, scalability, synchronization overhead, NUMA effects, and communication costs.

## Key Findings

- OpenMP provided the most stable shared-memory performance across the tested workloads.
- Intel oneTBB performed well in some cases but showed higher scheduling overhead at large thread counts.
- C++ Parallel STL simplified implementation but generally had lower performance due to abstraction overhead.
- OpenMPI outperformed Intel MPI on most SPEC HPC workloads on the AMD-based cluster.
- Performance depended strongly on workload structure, memory behavior, and communication patterns.

## Technologies Used

- C / C++
- OpenMP
- Intel oneTBB
- C++17 Parallel STL
- OpenMPI
- Intel MPI
- SLURM
- Intel VTune Profiler
- HPCToolkit
- NAS Parallel Benchmarks
- SPEC HPC 2021
