# v8-z8 (Zane V8 Build Engine)

This repository contains the CI/CD infrastructure to build the **V8 JavaScript Engine** as a monolithic library for Windows using **Clang**.

## 🚀 Purpose

V8 is notoriously difficult to build on Windows. This project provides a reliable, automated way to generate a `v8_monolith.lib` that is compatible with modern toolchains (like MSVC and Clang).

## 🛠 Build Configuration

The build is optimized for use with the **Zane V8 (Z8)** project:

- **Target**: Windows x64
- **Toolchain**: Google Clang (via Depot Tools)
- **Mode**: Monolithic (Static Library)
- **Features**:
  - `v8_monolithic = true`
  - `is_clang = true`
  - `use_custom_libcxx = false` (Uses standard MSVC-compatible headers)
  - `v8_use_external_startup_data = false` (Snapshots are embedded in the .lib)

## 📦 Artifacts

Each successful run of the [GitHub Actions workflow](https://github.com/Z8-JS/v8-z8/actions) produces an artifact containing:

1. `v8_monolith.lib`: The main library for linking.
2. `icudtl.dat`: Necessary data for internationalization (I18N).
3. `include/`: All necessary V8 headers.

## 📥 How to Use

1. Go to the **Actions** tab of this repository.
2. Select the latest successful "Build V8 with Clang" run.
3. Download the `v8_monolith_clang_windows_x64` artifact.
4. Extract the contents into the `libs/` and `include/` folders of your Z8 project.

---

Part of the **Z8 JavaScript Ecosystem**.
