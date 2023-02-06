---
title: Viewport Settings
description: The Viewport Settings Panel provides access to all of the adjustments and parameters needed to control InstaMAT Studio's 3D Viewport.
published: true
date: 2023-02-06T11:01:01.158Z
tags: instamat studio, canvas
editor: markdown
dateCreated: 2023-01-23T17:21:17.648Z
---

# Viewport Settings

![Viewport Settings Panel](/instamat_studio/canvas/viewport_settings.png =300x){.align-center}

The **Viewport Settings** Panel provides access to all of the adjustments and parameters needed to control InstaMAT Studio's 3D <a href="">Viewport</a>. In addition, there are a few settings to control the <a href="">Image Viewer</a> and, when working in the <a href="">Canvas</a>, adjust the Canvas thumbnail previews.

## Interface Overview

### Camera Settings

These settings control the tonemapping, exposure, and other typical adjustments for the camera used in the Viewport.

- **Tonemap Operator**: Sets the tonemapping type for the Viewport.
- **Automatic Exposure**: Automatically adjusts the exposure of the camera based on lighting changes.
- **Exposure**: Manually sets the exposure of the camera effectively setting the amount of light it captures.
- **Field Of View**: Sets the horizontal field of view of the camera in degrees.
- **Hue**: Performs an overall adjustment to the hue of the image.
- **Saturation**: Performs an overall adjustment to the saturation of the image.
- **Lightness**: Performs an overall adjustment to the lightness of the image. 
- **Contrast**: Performs an overall adjustment to the contrast of the image.

### Canvas and Image Viewer Settings

These settings control the <a href="">Canvas</a> thumbnail previews and <a href="">Image Viewer</a>.

- **Tonemap Operator**: Sets the tonemapping type for the Canvas previews and Image Viewer.
- **Exposure**: Manually sets the exposure of the image.

### Environment Settings

These settings determine the <a href="">Render Mode</a> for the Viewport and control the **Environment Image** that is used to illuminate the scene.

- **Render Mode**: Sets the active render mode. By default this is set to the `PBR` render mode for physically-based lighting and reflections.

> To learn more about the different render modes, read our dedicated article: <a href="">Render Modes</a>.
{.is-info}

- **Environment**: Sets the Environment Image used as a background and illuminates the scene.
- **Opacity**: Sets the opacity of the Environment Image. Setting to `0` will remove the appearance of the environment while still generating lighting and reflections.
- **Blur**: Sets the blur amount for the background Environment Image.
- **Rotation**: Sets the rotation of the Environment Image. In addition to this setting, the keyboard shortcut <kbd>Alt/Option + Right Click</kbd> and dragging left and right on the Viewport will rotate the environment.
- **Continuous Rotation**: Enabling this will continuously rotate the Environment Image.
- **Orbit Camera**: Enabling this will continuously orbit the camera around the scene effectively creating a "turntable" for quick design reviews.

### Scene Settings

These settings enable additional GUI elements in the Viewport.

- **Show Grid**: Renders a grid that automatically adjusts its cell size based on the position of the camera.
- **Show Normals**: Shows the vertex normals of the objects in the scene.

### Gizmo Settings

These settings adjust the gizmos used in the Viewport. These gizmos provide manual and visual adjustment of objects and effects directly within the Viewport itself.

- **Positional Increment**: Sets the interval gizmos will snap to. To enable snapping, hold the <kbd>J</kbd> key when *moving* a gizmo.
- **Angular Increment**: Sets the interval gizmos will snap to. To enable snapping, hold the <kbd>J</kbd> key when *rotating* a gizmo.

> To learn more about gizmos, read our dedicated article: <a href="">Viewport Gizmos</a>.
{.is-info}

### Render Settings

These settings enable and adjust many useful rendering features in the Viewport.

- **Wireframe Overlay**: Renders a wireframe on the meshes in the scene.
- **Show Backfaces**: Toggles rendering backfaces.
- **(FXAA) Anti-Aliasing**: When enabled, renders the scene with Fast Approximate Anti-Aliasing.
- **Mip Mapping**: Toggles Mip Mapping when rendering textures. By default, Mip Mapping is disabled in <a href="">Layering</a> projects. To force enable, use the `Allow Mip Mapping in Layering` setting in the <a href="">Preferences</a> panel under the `Layering` tab.
- **Material AO Intensity**: Adjusts the intensity of the Ambient Occlusion channel in the Viewport. This does not affect the levels of AO map directly but the visual appearance in the Viewport only.
- **Mesh UV Scale**: Controls the UV scale of all meshes in the scene. To quickly cycle through a UV scale of 1-5, press the <kbd>U</kbd> key.
- **Scene Point Scale**: Adjust the scale of all rendered points when viewing point clouds.
- **Displacement Mode**: The mode used when rendering displacement in the scene. Choose between `Tessellation` and `POM`: Parallax Occlusion Mapping.

> Choosing `Tessellation` will tessellate the geometry in the scene and displace the vertices based on their normal directions. `POM` or "Parallax Occlusion Mapping" is useful to render displacement over meshes that have sparse topology or a low level of subdivision.
{.is-info}

- **Displacement Factor**: Controls the factor at which displacement gets applied.
- **Tessellation Level**: Controls the tessellation factor of the scene. Increasing the level of tessellation on a mesh with already dense topology will decrease performance.
- **Use Physical Size**: When enabled, a physical size can be specified for the graph.