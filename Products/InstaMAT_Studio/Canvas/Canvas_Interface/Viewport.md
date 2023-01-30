---
title: Viewport
description: InstaMAT Studio's Viewport is a 3D view illuminated by an Environment Image. Use the Viewport to view your assets and materials in 3D with physically-based lighting and reflections.
published: true
date: 2023-01-23T19:54:12.662Z
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

### <img src="/instamat_studio/canvas/2.png" alt="2" width="22"/> Toolbar

The Viewport contains a dedicated toolbar with the following actions:

- ![Translate_Icon](/instamat_studio/canvas/translate_icon.png) **Translate (W)**: Sets the active viewport gizmo to translate the position of the selected mesh.
- ![Rotate_Icon](/instamat_studio/canvas/rotate_icon.png) **Rotate (E)**: Sets the active viewport gizmo to rotate the orientation of the selected mesh around its pivot point.
- ![Scale_Icon](/instamat_studio/canvas/scale_icon.png) **Scale (R)**: Sets the active viewport gizmo to Scale the size of the selected mesh.
- ![Gizmo_Control_Icon](/instamat_studio/canvas/gizmo_control_icon.png) **Gizmo Control**: Displays a popup menu to select the active gizmo to control if there are multiple available. Additionally the **Page Up** and **Page Down** keys can be used to cycle through the available gizmos.
- ![Export_Viewport_Scene_Icon](/instamat_studio/canvas/export_viewport_scene_icon.png) **Export Viewport Scene**: Exports the scene in the viewport to disk.
- ![Copy_Image_To_Clipboard_Icon](/instamat_studio/canvas/copy_image_to_clipboard_icon.png) **Copy Image to Clipboard**: Captures the current view to the Clipboard.
- ![Focus_Scene_Icon](/instamat_studio/canvas/focus_scene_icon.png) **Focus Scene**: Resets the view so that the entire scene fits within the Viewport area. Additionally the keyboard shortcut to do this is **F**.
- ![Toggle_Vertex_Displacement_Mapping_Icon](/instamat_studio/canvas/toggle_vertex_displacement_mapping_icon.png) **Toggle Vertex Displacement Mapping**: Toggles displacement along the mesh's vertex normals. To adjust the `Displacement Factor`, use the <a href="">Viewport Settings</a> Panel under `Render Settings`.
- ![Toggle_Material_Ambient_Occlusion_Icon](/instamat_studio/canvas/toggle_material_ambient_occlusion_icon.png) **Toggle Material Ambient Occlusion Intensity**: Toggles the visibility of the Ambient Occlusion channel of the material loaded into the Viewport.
- ![UV_Scale_Icon](/instamat_studio/canvas/uv_scale_icon.png) **Select Next Mesh UV Scale**: Cycles through UV scale increments from 1 to 5. This is a quick way to see how a material will tile when loaded on a 3D object.
- ![Toggle_Mip_Mapping_Icon](/instamat_studio/canvas/toggle_mip_mapping_icon.png) **Toggle Mip Mapping**: Toggles Mip Mapping when rendering textures. By default, Mip Mapping is disabled in <a href="">Layering</a> projects. To force enable, use the `Allow Mip Mapping in Layering` setting in the <a href="">Preferences</a> Panel under the `Layering` tab.
- ![Automatic_Exposure_Icon](/instamat_studio/canvas/automatic_exposure_icon.png) **Toggle Automatic Exposure**: Automatically adjusts the exposure of the camera based on lighting changes.
- ![Toggle_Environment_Icon](/instamat_studio/canvas/toggle_environment_icon.png) **Toggle Environment**: Toggles the visibility of the Environment Image. When the visibility is off, the scene is still illuminated by the image but is invisible to remove distractions.
- ![Choose_Environment_Icon](/instamat_studio/canvas/choose_environment_icon.png) **Choose Environment**: Shows a popup to choose the Environment image illuminating the scene. Additionally the **O** hotkey can be used.
- ![Load_Mesh_Icon](/instamat_studio/canvas/load_mesh_icon.png) **Load Mesh**: Brings up the **Pick Mesh** Panel to load a mesh into the Viewport.

> Click the ![Move_To_The_Left_Icon](/instamat_studio/canvas/move_to_the_left_icon.png) button above the toolbar to move the Viewport and <a href="Image_Viewer.html">Image Viewer</a> over to the left panel. This allows both the Viewport and the Image Viewer to be seen at the same time.
{.is-info}

### <img src="/instamat_studio/canvas/3.png" alt="3" width="22"/> Axis Gizmo

![Axis Gizmo](/instamat_studio/canvas/viewport_gizmo.png)

The **Axis Gizmo** shows the world space orientation of the scene. Additionally, the sphere reflects the current Environment Image lighting position in the highlights. 

The following can be done with the Axis Gizmo:

- **Orbit the Camera**: **Left Click** and drag the sphere
- **Snap to an Orthographic View**: hover over the gizmo and click on the dot corresponding to the orthographic view's axis.

### <img src="/instamat_studio/canvas/4.png" alt="4" width="22"/> Viewport Status Bar

The **Viewport Status Bar** displays the total polygon and drawcall count for the scene.

## Loading Meshes and Assets

Here are some methods to load meshes into the Viewport:

- **Double Click** a mesh in the <a href="">Package Management</a> Panel.
- Bring up the **Pick Mesh** Panel by pressing the <kbd>V</kbd> key or by using the ![Load_Mesh_Icon](/instamat_studio/canvas/load_mesh_icon.png) Viewport toolbar button.
- If mesh information is used in the <a href="">Canvas</a>, either <kbd>Left Click</kbd> the node's mesh input or output connection point, or <kbd>Right Click</kbd> the node to bring up the contextual menu and choose `View Mesh`.

> To learn more about loading meshes into the Viewport, check out our dedicated YouTube Video <a href="">here.</a>
{.is-info}

## Soloing Individual Channels

<img src="/instamat_studio/canvas/viewport_channels.gif" alt="GIF cycling through the different channels in the viewport" width="600"/>

Individual texture channels can be soloed directly on the meshes in the current scene. Soloing channels makes it easy to visually understand the intensities and locations of particular material attributes such as the roughness or height displacement.

To solo and cycle through individual channels in the Viewport:

1. Make sure the Viewport is selected.
2. Press <kbd>C</kbd>. Continuing to press <kbd>C</kbd> will cycle through the available channels.

> Alternatively, the `Solo Material Channel` Render Mode can be selected under the `Environment Settings` section in the <a href="">Viewport Settings</a> Panel.
{.is-info}

To return to `PBR` or "Material" mode, press <kbd>M</kbd>.

## Maximize Viewport

To maximize the real estate of the Viewport in the <a href="">Canvas</a> interface, use the ![Viewport Icon](/instamat_studio/canvas/viewport.png) button in the <a href="">Canvas Toolbar</a> to shift it so that it takes up the center section of the UI. You can then maximize it further by hiding the left and right panel sections by clicking on their respective top tab icons.

<img src="/instamat_studio/canvas/viewport_maximized.jpg" alt="GIF of maximizing the Viewport size" />

<!-- Originally had a GIF here but it was 10MB and wouldn't upload even after the change by Rogiel -->