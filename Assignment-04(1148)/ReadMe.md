## OpenGL Animated Triangle — 0432320005101148
A simple OpenGL program that renders a single animated triangle using GLFW and GLAD.

## Description
The triangle animates smoothly between cyan and magenta using a sine-wave-based uniform color updated every frame. Keyboard controls allow the user to temporarily turn the triangle white or permanently stop the animation with red.

## Features

Animated color transition: Cyan → Magenta (looping)
Keyboard controls for color override
Clean shader setup with uniform color passing
Proper VAO/VBO setup and resource cleanup


## Controls
KeyActionWTurn triangle white (momentary — hold to keep, release to resume animation)RTurn triangle red permanently (animation stops and does not resume)MClose the window

## Dependencies

GLFW — Window creation and input handling
GLAD — OpenGL function pointer loader
OpenGL 3.3 Core Profile


## Project Structure
├── main.cpp       # Main source file
├── glad.h         # GLAD header
├── glfw3.h        # GLFW header
└── README.md

## How to Build
Linux / macOS
bashg++ main.cpp glad.c -o triangle -lglfw -ldl
./triangle
Windows (MinGW)
bashg++ main.cpp glad.c -o triangle.exe -lglfw3 -lopengl32 -lgdi32
triangle.exe

## Shader Details
Vertex Shader — passes vertex positions directly to clip space.
Fragment Shader — uses a uniform vec4 ourColor to receive color from the CPU each frame.
The animation works by computing:
cppfloat t = sin(glfwGetTime()) / 2.0 + 0.5;  // oscillates 0.0 → 1.0
glUniform4f(location, 1.0f - t, t, 1.0f, 1.0f);
// cyan (0,1,1) ↔ magenta (1,0,1)

## Screenshots

Attach screenshots showing:

Default animated state (cyan/magenta)
White state (W held)
Red state (R pressed)



## Author
## Student ID: 0432320005101148
