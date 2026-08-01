# v8-Zane (Zane V8 Build Engine)

> [!NOTE]
> Builds for Windows (x64, ARM64), Linux (x64, ARM64), and macOS (arm64, x64) are supported via GitHub Actions workflows.

This repository contains the CI/CD infrastructure to build the **V8 JavaScript Engine** as a monolithic library for Windows, Linux, and macOS using **Clang**.

## 🚀 Purpose

V8 is notoriously difficult to build across multiple platforms. This project provides a reliable, automated way to generate a `v8_monolith` static library that is compatible with modern toolchains (like MSVC, Clang, and GCC).

## 🛠 Build Configuration

The build is optimized for use with the **Zane** project:

- **Targets**: Windows (x64, ARM64), Linux (x64, ARM64), macOS (x64, arm64)
- **Toolchain**: Google Clang (via Depot Tools)
- **Mode**: Monolithic (Static Library)
- **Features**:
  - `v8_monolithic = true`
  - `is_clang = true`
  - `v8_use_external_startup_data = false` (Snapshots are embedded in the library)

## 📦 Artifacts

Each successful run of the [GitHub Actions workflow](https://github.com/Zane-JS/v8-Zane/actions) produces artifacts containing:

1. `v8_monolith.lib` / `libv8_monolith.a`: The main library for linking.
2. `icudtl.dat`: Necessary data for internationalization (I18N).
3. `include/`: All necessary V8 headers.

## 📥 How to Use

1. Go to the **Actions** tab of this repository.
2. Select the latest successful build run for your target platform.
3. Download the artifact (e.g. `v8_monolith_Windows_x64`, `v8_monolith_macOS_ARM64`, etc.).
4. Extract the contents into the appropriate dependencies folder of your Zane project.

---

Part of the **Zane Ecosystem**.
