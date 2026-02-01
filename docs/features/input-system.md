---
layout: default
title: Input Architecture
parent: Features
nav_order: 1
---

# Dual-Layer Input Architecture

ModuPlane Pro implements a unique **Mode-less Input System** that allows simultaneous control of a character and UI without switching contexts. This is achieved through a custom arbitration layer in `InteractionManager` and `PlayerController`.

## How It Works

### 1. The Strategy: "Additive Control"
Most games switch between "Menu Mode" (Mouse cursor visible, Player frozen) and "Gameplay Mode" (Cursor locked, Player active). ModuPlane Pro keeps **both active**.

*   **Player Control**: Handled by the **Input System** via direct callbacks (`OnMove`, `OnRotate`).
    *   Keyboard Vectors (WASD) and Joystick Vectors are calculated separately.
    *   They are **Summed** together: `FinalMovement = JoystickInput + KeyboardInput`.
    *   This ensures 100% control authority from either device instantly.

### 2. UI Interaction: "Priority Raycasting"
Since the mouse is free, we need to know what the user is clicking on. The `InteractionManager` performs a prioritized check every frame:

1.  **Screen-Space Check**: Is the mouse over a Screen-Space UI element?
    *   *If YES*: Interact with that element. Ignore 3D world.
2.  **World-Space Check**: Is the mouse over a 3D Plane Button?
    *   *If YES*: Interact with the 3D button.
3.  **World-Plane Check**: Is the mouse hitting the ground plane?
    *   *If YES*: Prepare to move/manipulate the plane itself.

## Code Highlight

Here is how the Input Arbitration handles simultaneous data:

```csharp
// PlayerController.cs - Additive Input
public void OnMove(InputValue value) {
    if (Keyboard.current.wKey.isPressed) _keyboardInput.y = 1;
    // ...
    _joystickInput = value.Get<Vector2>();
}

private void Update() {
    // Both inputs contribute 100% to the movement
    Vector3 logicalMove = _keyboardInput + _joystickInput; 
    Move(logicalMove);
}
```

This ensures that a second operator (or the same user) can use the joystick to adjust the player's position while using the mouse to arrange UI elements, with zero input conflict.
