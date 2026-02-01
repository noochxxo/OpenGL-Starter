# OpenGL-Starter

A cross-platform OpenGL starter project with platform-specific CMake configurations. All platforms will share a common set of dependencies (GLFW, GLAD, GLM) stored in the `dependencies/` folder.

This is aimed for beginners who want a quick start and not have to deal with too much setup.

## Platform Support

### ✅ Linux (Ubuntu)
- **Build System**: CMake
- **OpenGL Loader**: GLAD (OpenGL 4.1 Core)
- **Status**: ✅ Complete - includes rotating square example

### ⏳ Windows - Needs to be tested
- **Build System**: CMake (to be configured)
- **OpenGL Loader**: GLAD (OpenGL 4.1 Core)
- **Status**: Pending - will be updated to use shared dependencies and CMake

### ⏳ macOS - Needs to be tested
- **Build System**: CMake (to be configured)
- **OpenGL Loader**: GLAD (OpenGL 4.1 Core)
- **Status**: Pending - will be updated to use shared dependencies and CMake

## Dependencies

All platforms will use the same vendored dependencies located in `dependencies/`:

- [GLFW](https://www.glfw.org/) - Windowing and input
- [GLAD](https://glad.dav1d.de/) - OpenGL function loader (OpenGL 4.1 Core)
- [GLM](https://github.com/g-truc/glm) - OpenGL Mathematics library

## Project Structure
```
OpenGL-Starter/
├── dependencies/          # Shared dependencies for all platforms
│   ├── GLFW/
│   ├── GLAD/
│   └── GLM/
├── linux/                 # ✅ Linux setup (CMake) - WORKING
│   ├── src/
│   │   └── main.cpp
│   ├── CMakeLists.txt
│   └── README.md
├── windows/               # ⏳ Windows setup - TO BE CONFIGURED
└── osx/                   # ⏳ macOS setup - TO BE CONFIGURED
```

## Getting Started

Currently, only the Linux setup is functional:

- **Linux**: See [linux/README.md](linux/README.md) for build instructions

Windows and macOS setups will be added once access to those platforms is available.

## Philosophy

This repository is designed as a **starter template** - copy the platform folder you need to begin your own OpenGL project. It's not meant for building projects directly in this repo, but rather as a quick-start reference.

## TODO

- [x] Linux setup with CMake
- [x] Add OpenGL Mathematics Library (GLM)
- [x] Centralize dependencies in shared folder
- [ ] Configure Windows setup with CMake using shared dependencies
- [ ] Configure macOS setup with CMake using shared dependencies
- [ ] Document dependency versions and update process
