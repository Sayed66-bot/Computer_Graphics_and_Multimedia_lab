# OpenGL Animated Rectangle

This project demonstrates a simple animated rectangle using OpenGL, GLFW, GLAD, and GLM.

The rectangle:

- Changes color gradually from red to white
- Rotates continuously in the XY plane
- Magnifies and shrinks smoothly over time

---

# Features

- OpenGL 3.3 Core Profile
- Vertex & Fragment Shaders
- Rectangle rendering using 2 triangles
- Real-time color animation
- Rotation transformation
- Scaling transformation
- GLM matrix transformations

---

# Technologies Used

- OpenGL
- GLFW
- GLAD
- GLM
- stb_image

---

# Animation Details

## 1. Color Animation

The rectangle smoothly changes from red to white.

```cpp
float greenValue =
    static_cast<float>(sin(timeValue) / 2.0 + 0.5);

glUniform4f(vertexColorLocation,
            1.0f,
            greenValue,
            greenValue,
            1.0f);
```

### Color Transition

| Value | Color |
|------|------|
| (1,0,0) | Red |
| (1,1,1) | White |

---

## 2. Rotation Animation

The rectangle rotates around the Z-axis.

```cpp
transform = glm::rotate(transform,
                        (float)glfwGetTime(),
                        glm::vec3(0.0f, 0.0f, 1.0f));
```

Since the Z-axis is perpendicular to the screen,
the rotation appears in the XY plane.

---

## 3. Magnification Animation

The rectangle continuously magnifies and shrinks.

```cpp
float scaleFactor =
    sin(glfwGetTime()) * 0.5f + 1.0f;

transform = glm::scale(transform,
                       glm::vec3(scaleFactor,
                                 scaleFactor,
                                 1.0f));
```

### Scale Range

```text
0.5 → 1.5
```

---

# Project Structure

```text
.
├── main.cpp
├── shader_m.h
├── stb_image.h
├── glad/
├── glm/
└── README.md
```

---

# Build Requirements

Make sure these libraries are installed:

- GLFW
- GLAD
- GLM

---

# Compilation

## Windows (MinGW)

```bash
g++ main.cpp glad.c -o app -lglfw -lopengl32
```

## Linux

```bash
g++ main.cpp glad.c -o app -lglfw -ldl -lGL
```

---

# Controls

| Key | Action |
|-----|--------|
| M | Close Window |

---

# Learning Concepts

This project demonstrates:

- OpenGL rendering pipeline
- GLSL shaders
- Uniform variables
- Matrix transformations
- Real-time animation
- VAO & VBO usage
- Color interpolation using sine wave

---

# Output

The final output shows:

- A rotating rectangle
- Smooth scaling animation
- Gradual color transition from red to white

---

# Author

Md Sayed <br>
Id:0432320005101148
