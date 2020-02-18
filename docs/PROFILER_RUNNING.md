Running profiling binary
==========================

  1. Available profiler binaries are in "profiler_builds"


  2. Copy binary to device and make executable
     ```sh
     adb push profiler_builds/benchmark_model_9.0
     adb shell chmod +x /data/local/tmp/benchmark_model
     ```

  3. Copy model definition to device
     ```sh
     adb push deeplab_257.tflite /data/local/tmp
     ```

  4. Run the benchmark
     ```sh
     adb shell /data/local/tmp/benchmark_model \
     --graph=/data/local/tmp/deeplab_257.tflite \
     --num_threads=4
     ```
