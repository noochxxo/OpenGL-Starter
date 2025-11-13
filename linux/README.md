# OpenGL Starter - Linux

This is the Linux setup for the OpenGL starter project using CMake.

## Prerequisites

Make sure you have the following installed:
```bash
sudo apt update
sudo apt install build-essential cmake libx11-dev libxrandr-dev libxinerama-dev libxcursor-dev libxi-dev libgl1-mesa-dev
```

## Building

From the `linux/` directory:
```bash
mkdir build
cd build
cmake ..
make
```

## Running
```bash
./OpenGLStarter
```

## What's Included

- **GLFW** - Windowing and input
- **GLAD** - OpenGL function loader (OpenGL 4.1 Core)
- **GLM** - OpenGL Mathematics library

## Controls

- **ESC** - Close the window

## Project Structure
```
linux/
├── src/
│   └── main.cpp          # Main application code
├── CMakeLists.txt        # CMake build configuration
└── build/                # Build artifacts (generated, not in git)
```

## Notes

- The `build/` directory is generated and should not be committed to git
- Dependencies are shared from `../dependencies/`
- To rebuild from scratch: `rm -rf build/ && mkdir build && cd build && cmake .. && make`
```

---

### Add build/ to .gitignore

At your repo root, create or update `.gitignore`:
```
# Build directories
linux/build/
windows/build/
osx/build/

# IDE files
.vscode/
.vs/
*.suo
*.user

# macOS
.DS_Store

# Compiled files
*.o
*.exe
*.out
*.app