#  Build-and-Install Matrix for Multi Architecture
 

The purpose of this diagram is to provide a clear and concise visual representation of the different build and installation options available for a software project across various platforms (desktop, ARM boards, and mobile). It serves as a roadmap for developers, helping them quickly identify the appropriate build method based on their target environment and preferred tools. This facilitates easier navigation of the build process, reducing confusion and saving time. It also helps in understanding the project's build system complexity and dependencies.

It's organized hierarchically:

**Build and Install (Top Level):** The overarching process encompasses all the following methods.

**Desktop:** Covers builds for traditional desktop operating systems.

*Pre Built (pip):* Simplest installation using pre-built packages (likely Python, given the "pip" reference). Supports Linux, macOS, and Windows (native or via WSL).

*Build From Source:* Building the project from source code. Provides options for Linux, macOS, and Windows, using Bazel or Docker for build management.

**ARM Boards (Edge):** Focuses on building for ARM-based devices (e.g., Raspberry Pi, Coral). Employs cross-compilation techniques (using CMake or Bazel) to build on a different architecture than the target device. Targets include AArch64, ARMv7 with NEON, and Raspberry Pi Zero (ARMv6).

**Mobile:** Deals with building for mobile platforms.

*iOS:* Supports pre-built CocoaPods (stable or nightly), local builds using Xcode, or Bazel for framework builds (with dynamic, static, or selective linking).

*Android:* Offers nightly snapshots, local builds, Docker builds, or manual builds using Bazel.



****Build-and-Install Mindmap****

```mermaid
graph TD
    A[Build and Install] --> B[Desktop]
    B --> C[PreBuilt]
    C --> D[Linux]
    click D "https://www.tensorflow.org/install/pip#linux"
    C --> E[MacOS]
    click E "https://www.tensorflow.org/install/pip#macos"
    C --> F(Windows<br>Native)
    click F "https://www.tensorflow.org/install/pip#windows-native"
    C --> G(Windows<br>WSL)
    click G "https://www.tensorflow.org/install/pip#windows-wsl2"
    B --> H(Build From Source)
    H --> I[Linux]
    click I "https://www.tensorflow.org/install/source#ubuntu"
    H --> J[Mac]
    click J "https://www.tensorflow.org/install/source#macos"
    J --> K[Bazel]
    click K "https://www.tensorflow.org/install/source#install_bazel"
    I --> L[Bazel]
    click L "https://www.tensorflow.org/install/source#install_bazel"
    I --> M[Docker]
    click M "https://www.tensorflow.org/install/source#docker_linux_builds"
    H --> N[Windows]
    click N "https://www.tensorflow.org/install/source_windows"
    N --> O[Bazel]
    click O "https://www.tensorflow.org/install/source_windows"

    A --> P[ARM Boards]
    click P "https://ai.google.dev/edge/litert/build/arm"
    P --> Q[Cross Compilation Cmake]
    click Q "https://ai.google.dev/edge/litert/build/cmake_arm"
    P --> R[Cross Compilation Bazel]
    click R "https://ai.google.dev/edge/litert/build/arm#cross-compilation_for_arm_with_bazel"
    Q --> S[AArch64 ARM64]
    click S "https://ai.google.dev/edge/litert/build/cmake_arm#build_for_aarch64_arm64"
    Q --> T[ARMv7 NEON enabled]
    click T "https://ai.google.dev/edge/litert/build/cmake_arm#build_for_armv7_neon_enabled"
    R --> U[Raspberry Pi Zero ARMv6]
    click U "https://ai.google.dev/edge/litert/build/cmake_arm#build_for_raspberry_pi_zero_armv6"


    A --> V[Mobile]
    V --> W[Ios]
    click W "https://ai.google.dev/edge/litert/build/ios"
    W --> X[Prebuilt Cocopods Stable/Nightly]
    click X "https://ai.google.dev/edge/litert/ios/quickstart"
    W --> Y[Local Build]
    click Y "https://ai.google.dev/edge/litert/build/ios#building_locally"
    X --> Z[Xcode]
    click Z "https://ai.google.dev/edge/litert/build/ios#install_xcode"
    Y --> AA[Bazel Framework Build]
    click AA "https://ai.google.dev/edge/litert/build/ios#install_bazel"
    AA --> AB[Dynamic Build]
    click AB "https://ai.google.dev/edge/litert/build/ios#build_tensorflowlitec_dynamic_framework_recommended"
    AA --> AC[Static Build]
    click AC "https://ai.google.dev/edge/litert/build/ios#build_tensorflowlitec_static_framework"
    AA --> AD[Selectively Build]
    click AD "https://ai.google.dev/edge/litert/build/ios#selectively_build_tflite_frameworks"

    V --> AE[Android]
    click AE "https://ai.google.dev/edge/litert/build/android"
    AE --> AF[Nightly Snapshots]
    click AF "https://ai.google.dev/edge/litert/build/android#use_nightly_snapshots"
    AE --> AG[Local Build]
    click AE "https://ai.google.dev/edge/litert/build/android#build_litert_locally"
    AG --> AH[Docker Build]
    click AH "https://ai.google.dev/edge/litert/build/android#set_up_build_environment_using_docker"
    AG --> AI[Manual Build Bazel]
    click AI "https://ai.google.dev/edge/litert/build/android#install_bazel_and_android_prerequisites"







