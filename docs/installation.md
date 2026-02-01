---
layout: default
title: Installation
nav_order: 2
parent: Getting Started
---

# Installation

ModuPlane Pro is delivered as a custom Unity Package. Follow these steps to integrate it into your project.

## Prerequisites

Ensure your project meets the following requirements:
*   **Unity Version**: 2022.3 LTS or higher (Developed on Unity 6.3.2).
*   **Render Pipeline**: HDRP is recommended, but URP/Built-in are supported with material adjustments.
*   **Input System**: The **New Input System** package must be installed and active (`Project Settings > Player > Active Input Handling`).

## Installing the Package

1.  **Import Package**:
    *   Go to `Assets > Import Package > Custom Package...`
    *   Select the `ModuPlanePro.unitypackage` file.
    *   Click **Import All**.

2.  **Setup Input Actions**:
    *   ModuPlane Pro uses the Input System. Ensure the `DemoInput.inputactions` file (included in Resources) is recognized.
    *   If using a custom Joystick, rebind the `Move` and `Rotate` actions in the Input System debugger if necessary.

## Verifying Installation

To verify that the installation was successful:
1.  Open the **Bootstrap Scene** (or create a new Scene).
2.  Add the `AppManager` component to a GameObject if using a blank scene.
3.  Press **Play**.
4.  The system will procedurally generate:
    *   A **Player** character.
    *   A **World Plane** with UI buttons.
    *   **Screen-Space UI** interaction elements.

---
**Note**: This asset creates files procedurally. It does not require pre-made prefabs, ensuring a clean project structure.
