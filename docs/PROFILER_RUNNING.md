Running profiling binary
==========================

  1. Install ADB support in your system. For MacOS, do
  ```sh
  brew install android-platform-tools
  ```
  For Ubuntu do
  ```sh
  apt-get install android-tools-adb
  ```
  2. Enable **USB Debugging** in your phine. Usually, this setting is
  found in System->Developper options. Ensure debugging is working
  by connecting the phone and executing
  ```sh
  adb devices
  ```
  
  3. Available profiler binaries are in "profiler_builds"


  4. Copy binary to device and make executable
     ```sh
     adb push profiler_builds/benchmark_model_9.0
     adb shell chmod +x /data/local/tmp/benchmark_model
     ```

  5. Copy model definition to device
     ```sh
     adb push deeplab_257.tflite /data/local/tmp
     ```

  6. Run the benchmark
     ```sh
     adb shell /data/local/tmp/benchmark_model \
     --graph=/data/local/tmp/deeplab_257.tflite \
     --num_threads=4
     ```
