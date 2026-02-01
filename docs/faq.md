---
layout: default
title: FAQ
nav_order: 5
---

# Frequently Asked Questions

### Q: Does this support Multiplayer?
**A:** The current architecture simulates a "local multi-user" experience (one person on joystick/keyboard, another on mouse), but it is not networked. However, the input separation logic is a perfect foundation for creating a split-screen or networked multiplayer game.

### Q: Why isn't the UI showing up?
**A:** 
1.  Ensure you have `PanelSettings` assigned in the `AppManager`.
2.  If using URP/Built-in, you may need to change the shader in `ProceduralEnvironment.cs` from HDRP/Lit to Standard.

### Q: Can I use my own Joystick?
**A:** Yes! The system uses Unity's Input System. You can rebind the controls in the `DemoInput` asset to match your specific hardware (XBox controller, Flight Stick, etc.).

### Q: Is the code editable?
**A:** Absolutely. usage of `[Region]` blocks and clear comments makes it easy to extend. The `InteractionManager` is the core place to modify interaction logic.

### Q: How do I change the plane size?
**A:** You can change the initial generation logic in `ProceduralEnvironment.cs`, or simply drage the edges of the plane in Play Mode!
