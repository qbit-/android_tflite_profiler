How to profile Tensorflow Lite on Android
=========================================

* Building profiling binary
  These instructions assume you are running macOS Catalina (ver. 10.15.2)
  In sublists are shown exact versions of libraries/packages which work.

  1. Go to tensorflow_src source folder
     ```sh
     cd tensorflow_src
     ```
  2. Checkout the needed version
     ```sh
     git checkout r2.1
     ```
  3. Install/use appropriate bazel from https://github.com/bazelbuild/bazel/releases
      * r2.1 == bazel 0.29.1

  4. Install/use android-studio
     ```sh
     brew cask install android-studio
     ```
  5. Select and install SDK/NDK in the Android studio
     * SDK - version of Android to support. SDK is found in the "About phone" menu
       + SDK 6.0 == Marshmallow
     * NDK - version of binaries to build C++ code. Can select with "show package details" checkbox
       + bazel 0.29.1 == NDK 18.1.5

  6. Configure tensorflow for the target. Accept defaults, on android version building say "y"
     ```sh
     ./configure
     ```
     ```sh
     Would you like to interactively configure ./WORKSPACE for Android builds? [y/N]:
     y
     ```
  7. Input paths to ndk. Select the API level corresponding to the lowest SDK API level required
     ```sh
     Please specify the home path of the Android NDK to use.
     /Users/roman/library/Android/Sdk/ndk/18.1.5063045
     ```
     ```sh
     Please specify the (min) Android NDK API level to use.
     23
     ```
     + 23 == Android version 6.0 (Marshmallow) and higher

  8. Input paths to SDK and the minimal API level to use. 
     ```sh
     Please specify the home path of the Android SDK to use.
     /Users/roman/library/Android/Sdk
     ```
     ```sh
     Please specify the Android SDK API level to use.
     23
     ```
     + 23 == Android version 6.0 (Marshmallow) and higher

  10. Compile profiling binary
      ```sh
      bazel build -c opt --config=android_arm --cxxopt='--std=c++11' --copt=-DTFLITE_PROFILING_ENABLED \
      tensorflow/lite/tools/benchmark:benchmark_model
      ```     

  11. Copy binary for future use
      ```sh
      cp bazel-bin/tensorflow/lite/tools/benchmark/benchmark_model ../benchmark_builds
      ```

