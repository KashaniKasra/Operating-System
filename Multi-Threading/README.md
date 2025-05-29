
# Audio Filtering and Signal Processing – Multi-Threading Project

This project implements a multi-threaded audio processing system for applying digital filters on WAV audio files using C++. It allows users to apply Band-pass, Notch, FIR, and IIR filters, measuring performance in both serial and parallel implementations.

## Objectives

- Understand and implement real-time digital signal processing techniques.
- Develop multi-threaded C++ applications using `pthreads` for audio filtering.
- Compare execution performance between serial and parallel approaches.

## Filters Implemented

- **Band-pass Filter**: Allows only a specific frequency band to pass, blocking others.
- **Notch Filter**: Removes a specific frequency (e.g., electrical noise at 50 Hz).
- **FIR Filter**: Finite impulse response, based on feedforward-only structure.
- **IIR Filter**: Infinite impulse response, uses both current and past inputs/outputs.

## Features

- Audio input and output in `.wav` format using `libsndfile`.
- CLI interface to choose filter and apply on input file.
- Multi-threaded implementation using `pthreads` with intelligent workload distribution.
- Outputs processing time and saves filtered result as `output.wav`.

## Build Instructions

Make sure `libsndfile` is installed. Compile using the provided `Makefile`.

```bash
make
```

## Run Instructions

### Serial Execution
```bash
./VoiceFilters.out serial input.wav
```

### Parallel Execution
```bash
./VoiceFilters.out parallel input.wav
```
## Dependencies

- C++11 or newer
- libsndfile (for reading/writing WAV files)
- POSIX threads (`pthread.h`)

## Performance Metric

Speed-up measured by:

```
speedup = serial_execution_time / parallel_execution_time
```

> Developed for the **Operating Systems** course – Fall 2024  
> University of Tehran | Department of Electrical and Computer Engineering  