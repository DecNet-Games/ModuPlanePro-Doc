---
layout: default
title: Quick Start
nav_order: 3
---

# Quick Start Guide

Once installed, you can immediately start using ModuPlane Pro. This guide covers the basic controls and interactions available in the demo.

## Controls Overview

The system supports simultaneous input from **Keyboard**, **Mouse**, and **Joystick**.

### 🎮 Player Movement
*   **Move**: `W`, `A`, `S`, `D` (Keyboard) OR Joystick Analog Stick.
    *   *Note: Inputs are additive! Holding 'W' while pushing Joystick forward results in double speed.*
*   **Rotate**: `Q`, `E` (Keyboard) OR Joystick Twist.

### 🖱️ UI Interaction (Mouse)
The mouse is used to interact with both Screen-Space and World-Space UI elements.

| Action | Control | Target |
| :--- | :--- | :--- |
| **Click** | Left Mouse Button | Buttons |
| **Drag** | Left Click + Drag | Buttons, World Plane |
| **Resize** | Drag Corner / Scroll | Buttons, Plane Edges |
| **Rotate** | Right Click + Drag | Buttons, World Plane |
| **Select** | Long Press (Left) | Buttons (for editing) |
| **Snap** | Hold `SHIFT` | Any Transform Action |

## Interactive Elements

### 1. Screen-Space UI
Buttons located along the edges of your screen (Buttons 11-20).
*   **Behavior**: They "stick" to the screen edges even if you resize the game window.
*   **Priority**: These buttons float *above* the 3D world.

### 2. World-Space UI
Buttons located on the grey plane in the 3D world (Buttons 1-10).
*   **Behavior**: They move with the plane but can also be rearranged individually.
*   **3D Nature**: As you move your player, these buttons change perspective.

### 3. The World Plane
The ground itself is interactive!
*   **Move**: Click and drag any empty space on the plane to move it relative to the player.
*   **Constraint**: The plane movement is constrained by the player's position to prevent losing it.

## Debugging

Check the **Debug Info** overlay in the bottom-right corner of the screen. It displays:
*   Currently **Active** element.
*   Current **Action** (Dragging, Resizing, etc.).
*   Currently **Selected** button.
