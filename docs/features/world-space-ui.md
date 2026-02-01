---
layout: default
title: World Space UI
parent: Features
nav_order: 2
---

# World Space UI

ModuPlane Pro takes Unity's **UI Toolkit** and projects it into the 3D world, maintaining full interactivity.

## The Challenge
Standard World Space Canvases are static. ModuPlane Pro makes them dynamic, physical objects.

## Capabilities

### 1. Procedural Plane Generation
The system generates a plane at runtime. No prefabs are required. The `ProceduralEnvironment` script creates the mesh, applies materials, and constructs the UI hierarchy efficiently.

### 2. Interaction Logic
The `InteractionManager` handles complex state machines for the buttons:

*   **Corner Detection**: Hovering near the corner of a button changes the interaction mode to `Resizing`.
*   **Right-Click**: Initiates `Rotation`.
*   **Grid Snapping**: Logic that rounds position/rotation values to the nearest increment (e.g., 50 units) when `SHIFT` is held.

### 3. Rendering Technique
We use a **RenderTexture** approach to map the UI Toolkit document onto the 3D Plane. This ensures crisp UI rendering that responds correctly to lighting and perspective changes in the High Definition Render Pipeline (HDRP).

```csharp
// ProceduralUIBuilder.cs
var renderTexture = new RenderTexture(1024, 768, 0, RenderTextureFormat.ARGB32);
panelSettings.targetTexture = renderTexture;
plane.GetComponent<Renderer>().material.mainTexture = renderTexture;
```

This method creates a seamless bridge between the 2D UI authoring workflow and 3D world interaction.
