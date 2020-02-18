Android benchmarks
==================
This repository contains some benchmarks of ASR models. If you need to run the profiler
clone with 
```sh
git clone https://github.com/qbit-/android_tflite_benchmarks.git
```
and use binaries for your Android version. Android version means the lowest version supported by the 
profiler. If you would like to compile the profiler in your system clone with
```sh
git clone --recursive https://github.com/qbit-/android_tflite_benchmarks.git
```
and follow the instructions in [PROFILER_BUILDING.md](https://github.com/qbit-/android_tflite_benchmarks/blob/master/docs/PROFILER_BUILDING.md)
### Repository contents
| Content | Description |
| ------ | ------ |
| [docs/PROFILER_BUILDING.md](https://github.com/qbit-/android_tflite_benchmarks/blob/master/docs/PROFILER_BUILDING.md) |  Profiler building instructions |
| [docs/PROFILER_RUNNING.md](https://github.com/qbit-/android_tflite_benchmarks/blob/master/docs/PROFILER_RUNNING.md) | Profiler running instructions |
| [profiler_builds](https://github.com/qbit-/android_tflite_benchmarks/blob/master/profiler_builds) | binary profiler files, with suffixes referring to lowest Android version. |
| [tensorflow_src](https://github.com/qbit-/android_tflite_benchmarks/blob/master/tensorflow_src) | Tensorflow repository. Needed only if you need to build the profiler |
| [benchmark_data](https://github.com/qbit-/android_tflite_benchmarks/blob/master/benchmark_data) | Benchmarks by model and phone |
