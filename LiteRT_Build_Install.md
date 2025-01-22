#  LiteRT Build-and-Install Roadmap for Multi Architecture
 

The purpose of this diagram is to provide a clear and concise visual representation of the different LiteRT build and installation options available for a software project across various platforms (desktop, ARM boards, and mobile). It serves as a roadmap for developers, helping them quickly identify the appropriate build method based on their target environment and preferred tools. This facilitates easier navigation of the build process, reducing confusion and saving time. It also helps in understanding the project's build system complexity and dependencies.

It's organized hierarchically:

**Mobile:** Deals with building for mobile platforms, covering topics such as compilation, linking, and packaging

*iOS:* Supports pre-built CocoaPods (stable or nightly), local builds using Xcode, or Bazel for framework builds (with dynamic, static, or selective linking).

*Android:* Offers nightly snapshots, local builds, Docker builds, or manual builds using Bazel.

**ARM Boards (Edge):** Focuses on building for ARM-based devices (e.g., Raspberry Pi, Coral). Employs cross-compilation techniques (using CMake or Bazel) to build on a different architecture than the target device. Targets include AArch64, ARMv7 with NEON, and Raspberry Pi Zero (ARMv6).


****LiteRT Build-and-Install Mindmap:****

```mermaid
   %%{init: { 'themeVariables': {'titleFontSize': '50px','fontSize': '40px' } } }%%
graph TD

    A --> V[Mobile]
    V --> W[Ios]
    click W "https://ai.google.dev/edge/litert/build/ios"
    W --> X[Prebuilt Cocopods Stable/Nightly]
    click X "https://ai.google.dev/edge/litert/ios/quickstart"
    W --> Y[Local Build]
    click Y "https://ai.google.dev/edge/litert/build/ios#building_locally"
    X --> Z[Cocopod Developers]
    click Z "https://ai.google.dev/edge/litert/ios/quickstart#cocoapods_developers"
    X --> AA[Bazel Developers]
    click AA "https://ai.google.dev/edge/litert/ios/quickstart#bazel_developers"
    Y --> AB[Bazel Framework Build]
    click AB "https://ai.google.dev/edge/litert/build/ios#install_bazel"
    AB --> AC[Dynamic Build]
    click AC "https://ai.google.dev/edge/litert/build/ios#build_tensorflowlitec_dynamic_framework_recommended"
    AB --> AD[Static Build]
    click AD "https://ai.google.dev/edge/litert/build/ios#build_tensorflowlitec_static_framework"
    AB --> AE[Selectively Build]
    click AE "https://ai.google.dev/edge/litert/build/ios#selectively_build_tflite_frameworks"

    V --> AF[Android]
    click AF "https://ai.google.dev/edge/litert/build/android"
    AF --> AG[Nightly Snapshots]
    click AG "https://ai.google.dev/edge/litert/build/android#use_nightly_snapshots"
    AF --> AH[Local Build]
    click AH "https://ai.google.dev/edge/litert/build/android#build_litert_locally"
    AH --> AI[Docker Build]
    click AI "https://ai.google.dev/edge/litert/build/android#set_up_build_environment_using_docker"
    AH --> AJ[Without Docker using Bazel]
    click AJ "https://ai.google.dev/edge/litert/build/android#install_bazel_and_android_prerequisites"

    A[Build and Install] --> P[ARM Boards]
    P --> Q[Cross Compilation Bazel]
    click Q "https://ai.google.dev/edge/litert/build/arm#cross-compilation_for_arm_with_bazel"
    P --> R[Cross Compilation Cmake]
    click R "https://ai.google.dev/edge/litert/build/cmake_arm"
    R --> S[AArch64 ARM64]
    click S "https://ai.google.dev/edge/litert/build/cmake_arm#build_for_aarch64_arm64"
    R --> T[ARMv7 NEON enabled]
    click T "https://ai.google.dev/edge/litert/build/cmake_arm#build_for_armv7_neon_enabled"
    R --> U[Raspberry Pi Zero ARMv6]
    click U "https://ai.google.dev/edge/litert/build/cmake_arm#build_for_raspberry_pi_zero_armv6"


    







