---
title: Canvas Toolbar
description: The Canvas Toolbar sits above the main Canvas view and provides shortcuts to many features and functions of the Canvas.
published: true
date: 2023-01-25T16:40:22.918Z
tags: instamat studio, canvas
editor: markdown
dateCreated: 2023-01-20T18:27:34.438Z
---

# Canvas Toolbar

![Canvas Toolbar with sections highlighted and numbered](/instamat_studio/canvas/canvas_toolbar.png)

The **Canvas Toolbar** sits above the main <a href="">Canvas</a> view and provides shortcuts to many features and functions of the Canvas. Each set of items is grouped together based on their functionality. This article goes into depth on each of these groups and items. 

> Additionally, you can view our dedicated YouTube Video overviewing the Canvas Toolbar <a href="">here</a>.
{.is-info}

## Groups Overview

The Canvas Toolbar is organized into the following groups:

1. **Undo History**: Displays a popup of the session's undo history allowing the user to jump back to a previous point.
2. **Global Execution Settings and Seed**: Controls the execution resolution, format and seed of the active graph.
3. **Center View Selection**: Determines which view takes up the center area (Canvas, Viewport, or Image Viewer)
4. **Project Management**: Creates a new project, saves the current project, or opens the  <a href="">Output Export Dialog</a>.
5. **Additional Panels**: Opens the <a href="">Baking Panel</a>, <a href="">Raytracing</a>, or Output Log.
6. **Canvas Tools and Display Functions**: Provides control over various Canvas functionality and display options.
7. **Graph Performance Tools**: Gives access to various graph performance and execution tools.

## <i class="fa-regular fa-circle-1"></i> Undo History

![undo_history_button.png](/instamat_studio/canvas/undo_history_button.png){.align-left} The **Undo History** button is divided into two sections: Undo Button, and Undo Popup. Clicking the left portion with the icon will perform an undo operation.

Additonally the keyboard shortcut <kbd>Cmd/Ctrl + Z</kbd> can be used to undo, and <kbd>Shift + Cmd/Ctrl + Z</kbd> will redo. Clicking the downward arrow will open up the **Undo History Popup**.
  
![Undo History Popup](/instamat_studio/canvas/undo_history_popup_2.png){.align-left} This popup displays the undo history for the active session. The order of the items are listed where the most recent action is at the bottom. Clicking on one of the items will undo back to the historical state where that operation took place. As long as no additional changes are made, clicking on future items at the bottom will restore and "redo" the subsequent actions until reaching the latest step.

<br style="clear:left;"/>

## <i class="fa-regular fa-circle-2"></i> Global Execution Settings and Seed

These items determine the global resolution, format and seed for the active graph.

<img src ="/instamat_studio/canvas/global_res_and_seed.png" width ="400" />

### Global Execution Settings
![Global Execution Resolution](/instamat_studio/canvas/global_res_and_seed_2.png){.align-left} The **Execution Settings Popup** controls the size and format of the active graph. Clicking the <i class="fa-regular fa-unlock"></i> icon will maintain the same `Width` and `Height` values so that they are always equal.

<br style="clear:left;" />

### Global Seed

![global_seed_2.png](/instamat_studio/canvas/global_seed_2.png){.align-left} The **Global Seed** value sets the seed for all randomized parameters and attributes in the active graph. This is useful to quickly preview variations of the same material in an <a href="">Element Graph</a>. This seed value is also used when exporting graph outputs to disk.

<br style="clear:left;" />

**Right Clicking** the seed provides a contextual menu allowing to reset the number to InstaMAT's default seed value.

## <i class="fa-regular fa-circle-3"></i> Center View Selection

These items determine which view takes up the center area of the Canvas interface. By clicking on the icon matching with the corresponding view, the interface will shift and reorganize accordingly. The icons correspond as follows:

- <i class="fa-regular fa-diagram-project"></i> Canvas
- <i class="fa-regular fa-cube"></i> Viewport
- <i class="fa-regular fa-image-polaroid"></i> Image Viewer

Additionally, the keyboard shortcut <kbd>Option/Alt + C</kbd> cycles through each option.

> Switching the <a href="">Viewport</a> to the center view is a great way to quickly perform design reviews of your 3D assets and materials.
{.is-info}

## <i class="fa-regular fa-circle-4"></i> Project Management

These items provide shortcuts to common project management actions.

- <i class="fa-regular fa-octagon-plus"></i> **New Project**: Opens the New Project screen.
- <i class="fa-regular fa-floppy-disk"></i> **Save Project**: Saves the active project.
- <i class="fa-regular fa-share"></i> **Export Image and Data Outputs**: Opens the <a href="">Image and Data Output Export Dialog</a>. Use this dialog to export the graph's outputs to disk.

## <i class="fa-regular fa-circle-5"></i> Additional Panels

These items provide access to additional panels and features in InstaMAT Studio.

- <i class="fa-regular fa-oven"></i> **Mesh Baking**: Opens the <a href="">Mesh Baking Panel</a>. Baked mesh maps will be added to the active package and found in the <a href="Package_Management.html">Package Management Panel</a>.
- ![Raytracing](/instamat_studio/canvas/raytracing.png) **Raytracing**: Opens the <a href="">Raytracing Panel</a>.
- <i class="fa-regular fa-square-terminal"></i> **Show Output Log**: Displays the Output Log at the bottom of the interface below the Canvas view.

## <i class="fa-regular fa-circle-6"></i> Canvas Tools and Display Functions

These items provide quick access to additional Canvas tools and functions.

- <i class="fa-regular fa-unlock"></i> **Automatically Render Graph**: When enabled, the graph will automatically render when a change is made. Useful to turn off if there are a few changes to be made and the graph requires intensive processing.
- <i class="fa-regular fa-bolt"></i> **Flash Rendered Nodes**: When enabled, nodes that are executed will flash with a yellow outline. This helps to visually determine which section of the graph is being utilized when changes are being made.
- <i class="fa-regular fa-wave-sine"></i> **Connection Rendering Mode**: Determines the style in which connections are drawn in the Canvas. Cycle between Smooth, Angular, and straight lines.
- <i class="fa-regular fa-link"></i> **Link Category Mode**: Combines related Input and Output pins that share the same category. Useful when blending multiple materials together or working with Mesh Bake Data. Connections turn blue, and nodes in the Canvas feature a blue line on the bottom to signify that Link Category Mode is active.
- <i class="fa-regular fa-images"></i> **Canvas Previews**: Toggles the Canvas Previews for nodes in the graph. Disabling can reduce a graph's memory footprint.
- <i class="fa-regular fa-globe"></i> **Minimap**: Displays the [Minimap](./Minimap#555).
- <i class="fa-regular fa-square-a-lock"></i> **Lock Comments**: When enabled, comments are locked and cannot be accidentally selected or moved.

## <i class="fa-regular fa-circle-7"></i> Graph Performance Tools

These items assist in diagnosing the performance and execution of the active graph.

- <i class="fa-regular fa-network-wired"></i> **Render Unconnected Nodes**: When disabled, nodes that are disconnected from a graph output are not rendered. Useful when optimizing a graph to only execute nodes that are actively used.
- <i class="fa-regular fa-stopwatch"></i> **Show Timings**: Toggles the execution timings which are visible on both the Canvas background and on individual nodes.

> To view timing information about a particular set of nodes, use <kbd>Shift + Left Click and Drag</kbd> to drag a selection over multiple. A table will appear in the <a href="">Graph Object Editor</a> displaying the Name, Format, Size, and Execution Time of each node. Each column of the table is sortable making it easy to understand which portions of the graph take the most amount of compilation time. Additionally using the shortcut <kbd>Cmd/Ctrl + A</kbd> can be used to **Select All** nodes in the active graph.
{.is-info}

- <i class="fa-regular fa-gauge-simple-max"></i> **Canvas Update Time Mode**: Determines the rendering priority of the <a href="">Image Viewer</a> versus the Canvas Previews. Toggling the speedometer to the right will prioritize rendering the Canvas Previews. Toggling to the left prioritizes the Image Viewer.