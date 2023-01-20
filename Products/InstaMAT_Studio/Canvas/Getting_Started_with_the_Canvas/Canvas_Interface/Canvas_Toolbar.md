---
title: Canvas Toolbar
description: The Canvas Toolbar sits above the main Canvas view and provides shortcuts to many features and functions of the Canvas.
published: true
date: 2023-01-20T18:43:19.948Z
tags: instamat studio, canvas
editor: markdown
dateCreated: 2023-01-20T18:27:34.438Z
---

# Canvas Toolbar

![Canvas Toolbar with sections highlighted and numbered](/instamat_studio/canvas/canvas_toolbar.png)

The **Canvas Toolbar** sits above the main <a href="">Canvas</a> view and provides shortcuts to many features and functions of the Canvas. Each set of items is grouped together based on their functionality. This article goes into depth on each of these groups and items. 

> Additionally, you can view our dedicated YouTube Video overviewing the Canvas Toolbar <a href="">here</a>.

## Groups Overview

The Canvas Toolbar is organized into the following groups:

1. **Undo History**: Displays a popup of the session's undo history allowing the user to jump back to a previous point.
2. **Global Execution Settings and Seed**: Controls the execution resolution, format and seed of the active graph.
3. **Center View Selection**: Determines which view takes up the center area (Canvas, Viewport, or Image Viewer)
4. **Project Management**: Creates a new project, saves the current project, or opens the  <a href="">Output Export Dialog</a>.
5. **Additional Panels**: Opens the <a href="">Baking Panel</a>, <a href="">Raytracing</a>, or Output Log.
6. **Canvas Tools and Display Functions**: Provides control over various Canvas functionality and display options.
7. **Graph Performance Tools**: Gives access to various graph performance and execution tools.

## <img src="/instamat_studio/canvas/1.png" alt="1" width="30"/> Undo History

![Undo History Icon](/instamat_studio/canvas/undo_history_icon.png)

The **Undo History** button is divided into two sections: Undo Button, and Undo Popup. Clicking the left portion with the icon will perform an undo operation. Additonally the keyboard shortcut **Cmd/Ctrl + Z** can be used to undo, and **Shift + Cmd/Ctrl + Z** will redo. Clicking the downward arrow will open up the **Undo History Popup**.

<img src="/instamat_studio/canvas/undo_history_popup.png" width="500"/>

This popup displays the undo history for the active session. The order of the items are listed where the most recent action is at the bottom. Clicking on one of the items will undo back to the historical state where that operation took place. As long as no additional changes are made, clicking on future items at the bottom will restore and "redo" the subsequent actions until reaching the latest step.

## <img src="/instamat_studio/canvas/2.png" alt="2" width="30"/> Global Execution Settings and Seed

![Global Res and Seed](/instamat_studio/canvas/global_res_and_seed.png)

These items determine the global resolution, format and seed for the active graph.

### Global Execution Settings

<img src="/instamat_studio/canvas/global_res.png" width="600"/>

The **Execution Settings Popup** controls the size and format of the active graph. Clicking the ![lock](/instamat_studio/canvas/lock_icon.png) icon will maintain the same **'Width'** and **'Height'** values so that they are always equal.

### Global Seed

![Global Seed item](/instamat_studio/canvas/global_seed.png)

The **Global Seed** value sets the seed for all randomized parameters and attributes in the active graph. This is useful to quickly preview variations of the same material in an <a href="">Element Graph</a>. This seed value is also used when exporting graph outputs to disk.

**Right Clicking** the seed provides a contextual menu allowing to reset the number to InstaMAT's default seed value.

## <img src="/instamat_studio/canvas/3.png" alt="3" width="30"/> Center View Selection

![Center View Selection Icons](/instamat_studio/canvas/center_view_selection.png)

These items determine which view takes up the center area of the Canvas interface. By clicking on the icon matching with the corresponding view, the interface will shift and reorganize accordingly. The icons correspond as follows:

- ![Canvas](/instamat_studio/canvas/canavs.png) Canvas
- ![Viewport](/instamat_studio/canvas/viewport.png) Viewport
- ![Image Viewer](/instamat_studio/canvas/image_viewer.png) Image Viewer

Additionally, the keyboard shortcut **Option/Alt + C** cycles through each option.

> Switching the <a href="">Viewport</a> to the center view is a great way to quickly perform design reviews of your 3D assets and materials.

## <img src="/instamat_studio/canvas/4.png" alt="4" width="30"/> Project Management

![Project Management Icons](/instamat_studio/canvas/project_management.png)

These items provide shortcuts to common project management actions.

- ![New Project](Images/New_Project.png) **New Project**: Opens the New Project screen.
- ![Save Project](Images/Save_Project.png) **Save Project**: Saves the active project.
- ![Export Image and Data Outputs](Images/Export.png) **Export Image and Data Outputs**: Opens the <a href="">Image and Data Output Export Dialog</a>. Use this dialog to export the graph's outputs to disk.

## <img src="/instamat_studio/canvas/5.png" alt="5" width="30"/> Additional Panels

![Additional Panels](/instamat_studio/canvas/additional_panels.png)

These items provide access to additional panels and features in InstaMAT Studio.

- ![Mesh Baking](/instamat_studio/canvas/mesh_bake.png) **Mesh Baking**: Opens the <a href="">Mesh Baking Panel</a>. Baked mesh maps will be added to the active package and found in the <a href="Package_Management.html">Package Management Panel</a>.
- ![Raytracing](/instamat_studio/canvas/raytracing.png) **Raytracing**: Opens the <a href="">Raytracing Panel</a>.
- ![Output Log](/instamat_studio/canvas/output_log.png) **Show Output Log**: Displays the Output Log at the bottom of the interface below the Canvas view.

## <img src="/instamat_studio/canvas/6.png" alt="6" width="30"/> Canvas Tools and Display Functions

![Canvas Tools and Display Functions](/instamat_studio/canvas/canvas_tools.png)

These items provide quick access to additional Canvas tools and functions.

- ![Automatically Render Graph](/instamat_studio/canvas/auto_render.png) **Automatically Render Graph**: When enabled, the graph will automatically render when a change is made. Useful to turn off if there are a few changes to be made and the graph requires intensive processing.
- ![Flash Rendered Nodes](/instamat_studio/canvas/flash.png) **Flash Rendered Nodes**: When enabled, nodes that are executed will flash with a yellow outline. This helps to visually determine which section of the graph is being utilized when changes are being made.
- ![Connection Rendering Mode](/instamat_studio/canvas/connection_mode.png) **Connection Rendering Mode**: Determines the style in which connections are drawn in the Canvas. Cycle between Smooth, Angular, and straight lines.
- ![Link Category Mode](/instamat_studio/canvas/lcm.png) **Link Category Mode**: Combines related Input and Output pins that share the same category. Useful when blending multiple materials together or working with Mesh Bake Data. Connections turn blue, and nodes in the Canvas feature a blue line on the bottom to signify that Link Category Mode is active.
- ![Canvas Previews](/instamat_studio/canvas/canvas_previews.png) **Canvas Previews**: Toggles the Canvas Previews for nodes in the graph. Disabling can reduce a graph's memory footprint.
- ![Minimap](/instamat_studio/canvas/minimap.png) **Minimap**: Displays the <a href="">Minimap</a>.
- ![Lock Comments](/instamat_studio/canvas/lock_comments.png) **Lock Comments**: When enabled, comments are locked and cannot be accidentally selected or moved.

## <img src="/instamat_studio/canvas/7.png" alt="7" width="30"/> Graph Performance Tools

![Graph Performance Tools](Images/Graph_Performance.png)

These items assist in diagnosing the performance and execution of the active graph.

- ![Render Unconnected Nodes](Images/Render_Unconnected.png) **Render Unconnected Nodes**: When disabled, nodes that are disconnected from a graph output are not rendered. Useful when optimizing a graph to only execute nodes that are actively used.
- ![Show Timings](Images/Canvas_Timings.png) **Show Timings**: Toggles the execution timings which are visible on both the Canvas background and on individual nodes.
> To view timing information about a particular set of nodes, use **Shift + Left Click and Drag** to drag a selection over multiple. A table will appear in the <a href="Graph_Object_Editor.html">Graph Object Editor</a> displaying the Name, Format, Size, and Execution Time of each node. Each column of the table is sortable making it easy to understand which portions of the graph take the most amount of compilation time. Additionally using the shortcut **Cmd/Ctrl + A** can be used to **Select All** nodes in the active graph.
- ![Canvas Update Time Mode](Images/Render_Priority.png) **Canvas Update Time Mode**: Determines the rendering priority of the <a href="">Image Viewer</a> versus the Canvas Previews. Toggling the speedometer to the right will prioritize rendering the Canvas Previews. Toggling to the left prioritizes the Image Viewer.