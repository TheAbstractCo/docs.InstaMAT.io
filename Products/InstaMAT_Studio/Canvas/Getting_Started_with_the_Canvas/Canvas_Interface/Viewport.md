---
title: Viewport
description: InstaMAT Studio's Viewport is a 3D view illuminated by an Environment Image. Use the Viewport to view your assets and materials in 3D with physically-based lighting and reflections.
published: true
date: 2023-01-23T17:45:27.925Z
tags: instamat studio
editor: markdown
dateCreated: 2023-01-23T17:32:24.266Z
---

# Viewport

<img src="/instamat_studio/canvas/viewport_communicator.png" alt="Viewport" width="600"/>

InstaMAT Studio's **Viewport** is a 3D view illuminated by an **Environment Image**. Use the Viewport to view your assets and materials in 3D with physically-based lighting and reflections. The Viewport is utilized in many different project types within InstaMAT Studio such as in the <a href="">Element Graph</a>, <a href="">Layering</a>, and <a href="">Materialize Image</a>.

The Viewport is more than just a viewer. Viewport Gizmos provide artistic control over the position, scale, and rotation of meshes in the scene. Gizmos can also control the position of gradients, decals, and projections in 3D space. Mesh modifiers like the <a href="">Mesh Bend</a> node can also be controlled directly in the Viewport. Most essentially, <a href="">painting</a> using InstaMAT's procedural 3D painting engine is done directly in the Viewport. Painting can be done in Layering and Canvas-based projects.

> To learn more about how to adjust aspects of the Viewport such as the Camera, Environment, and Render Settings, please read our article on the <a href="">Viewport Settings</a> Panel. Here you will learn how to change the Environment Image, adjust the Camera's Exposure, and dial in the scene's Tessellation and Displacement settings.
{.is-info}

## Interface Overview

<img src="/instamat_studio/canvas/viewport_numbered.png" alt="Viewport Numbered" width="600"/>

The Viewport is made up of four parts: The 3D View, the Toolbar, the Axis Gizmo, and the Viewport Status Bar.

### <img src="/instamat_studio/canvas/1.png" alt="1" width="22"/> 3D View

The following is how to navigate in the Viewport:

- **Orbit the camera around the scene**: hold the <kbd>Alt/Option</kbd> key, <kbd>Left Click</kbd>, and drag.
- **Zoom or Dolly In on the mouse position**: use the <kbd>Scroll Wheel</kbd>. This locks the camera's **Orbit Pivot Point** on where the mouse was pointing on the object in the scene.
- **Look Around in First Person mode**: **Right Click** and drag.
- **Focus**:  use the **F** key. This resets the view so that the entire scene fits the Viewport area and centers the **Orbit Pivot Point** to the origin.
- **Fly Through the Scene**: use the **Arrow Keys** or **W, A, S, D**.
- **Rotate the Environment Image**: hold the **Alt/Option** key, **Right Click** and drag.

### <img src="Images/2.png" alt="2" width="22"/> Toolbar

The Viewport contains a dedicated toolbar with the following actions:

- ![Translate_Icon](Images/Translate_Icon.png) **Translate (W)**: Sets the active viewport gizmo to translate the position of the selected mesh.
- ![Rotate_Icon](Images/Rotate_Icon.png) **Rotate (E)**: Sets the active viewport gizmo to rotate the orientation of the selected mesh around its pivot point.
- ![Scale_Icon](Images/Scale_Icon.png) **Scale (R)**: Sets the active viewport gizmo to Scale the size of the selected mesh.
- ![Gizmo_Control_Icon](Images/Gizmo_Control_Icon.png) **Gizmo Control**: Displays a popup menu to select the active gizmo to control if there are multiple available. Additionally the **Page Up** and **Page Down** keys can be used to cycle through the available gizmos.
- ![Export_Viewport_Scene_Icon](Images/Export_Viewport_Scene_Icon.png) **Export Viewport Scene**: Exports the scene in the viewport to disk.
- ![Copy_Image_To_Clipboard_Icon](Images/Copy_Image_To_Clipboard_Icon.png) **Copy Image to Clipboard**: Captures the current view to the Clipboard.
- ![Focus_Scene_Icon](Images/Focus_Scene_Icon.png) **Focus Scene**: Resets the view so that the entire scene fits within the Viewport area. Additionally the keyboard shortcut to do this is **F**.
- ![Toggle_Vertex_Displacement_Mapping_Icon](Images/Toggle_Vertex_Displacement_Mapping_Icon.png) **Toggle Vertex Displacement Mapping**: Toggles displacement along the mesh's vertex normals. To adjust the **'Displacement Factor'**, use the <a href="Viewport_Settings.html">Viewport Settings</a> Panel under **'Render Settings'**.
- ![Toggle_Material_Ambient_Occlusion_Icon](Images/Toggle_Material_Ambient_Occlusion_Icon.png) **Toggle Material Ambient Occlusion Intensity**: Toggles the visibility of the Ambient Occlusion channel of the material loaded into the Viewport.
- ![UV_Scale_Icon](Images/UV_Scale_Icon.png) **Select Next Mesh UV Scale**: Cycles through UV scale increments from 1 to 5. This is a quick way to see how a material will tile when loaded on a 3D object.
- ![Toggle_Mip_Mapping_Icon](Images/Toggle_Mip_Mapping_Icon.png) **Toggle Mip Mapping**: Toggles Mip Mapping when rendering textures. By default, Mip Mapping is disabled in <a href="">Layering</a> projects. To force enable, use the **'Allow Mip Mapping in Layering'** setting in the <a href="">Preferences</a> Panel under the **Layering** tab.
- ![Automatic_Exposure_Icon](Images/Automatic_Exposure_Icon.png) **Toggle Automatic Exposure**: Automatically adjusts the exposure of the camera based on lighting changes.
- ![Toggle_Environment_Icon](Images/Toggle_Environment_Icon.png) **Toggle Environment**: Toggles the visibility of the Environment Image. When the visibility is off, the scene is still illuminated by the image but is invisible to remove distractions.
- ![Choose_Environment_Icon](Images/Choose_Environment_Icon.png) **Choose Environment**: Shows a popup to choose the Environment image illuminating the scene. Additionally the **O** hotkey can be used.
- ![Load_Mesh_Icon](Images/Load_Mesh_Icon.png) **Load Mesh**: Brings up the **Pick Mesh** Panel to load a mesh into the Viewport.

> Click the ![Move_To_The_Left_Icon](Images/Move_To_The_Left_Icon.png) button above the toolbar to move the Viewport and <a href="Image_Viewer.html">Image Viewer</a> over to the left panel. This allows both the Viewport and the Image Viewer to be seen at the same time.

### <img src="Images/3.png" alt="3" width="22"/> Axis Gizmo

![Axis Gizmo](Images/Viewport_Gizmo.png)

The **Axis Gizmo** shows the world space orientation of the scene. Additionally, the sphere reflects the current Environment Image lighting position in the highlights. 

The following can be done with the Axis Gizmo:

- **Orbit the Camera**: **Left Click** and drag the sphere
- **Snap to an Orthographic View**: hover over the gizmo and click on the dot corresponding to the orthographic view's axis.

### <img src="Images/4.png" alt="4" width="22"/> Viewport Status Bar

The **Viewport Status Bar** displays the total polygon and drawcall count for the scene.

## Loading Meshes and Assets

Here are some methods to load meshes into the Viewport:

- **Double Click** a mesh in the <a href="Package_Management.html">Package Management</a> Panel.
- Bring up the **Pick Mesh** Panel by pressing the **V** key or by using the ![Load_Mesh_Icon](Images/Load_Mesh_Icon.png) Viewport toolbar button.
- If mesh information is used in the <a href="../../Canvas_Overview.html">Canvas</a>, either **Left Click** the node's mesh input or output connection point, or **Right Click** the node to bring up the contextual menu and choose **'View Mesh'**.

> To learn more about loading meshes into the Viewport, check out our dedicated YouTube Video <a href="">here.</a>

## Soloing Individual Channels

<img src="Images/Viewport_Channels.gif" alt="GIF cycling through the different channels in the viewport" width="600"/>

Individual texture channels can be soloed directly on the meshes in the current scene. Soloing channels makes it easy to visually understand the intensities and locations of particular material attributes such as the roughness or height displacement.

To solo and cycle through individual channels in the Viewport:

1. Make sure the Viewport is selected.
2. Press **C**. Continuing to press **C** will cycle through the available channels.

> Alternatively, the **'Solo Material Channel'** Render Mode can be selected under the **Environment Settings** section in the <a href="Viewport_Settings.html">Viewport Settings</a> Panel.

To return to **'PBR'** or "Material" mode, press **M**.

## Maximize Viewport

To maximize the real estate of the Viewport in the <a href="../../Canvas_Overview.html">Canvas</a> interface, use the ![Viewport Icon](Images/Viewport.png) button in the <a href="Canvas_Toolbar.html">Canvas Toolbar</a> to shift it so that it takes up the center section of the UI. You can then maximize it further by hiding the left and right panel sections by clicking on their respective top tab icons.

<img src="Images/Viewport_Maximized.gif" alt="GIF of maximizing the Viewport size" />