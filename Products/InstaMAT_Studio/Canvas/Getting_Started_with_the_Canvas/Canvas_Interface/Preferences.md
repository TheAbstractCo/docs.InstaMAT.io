---
title: Preferences
description: The Preferences Panel provides access to all of InstaMAT Studio's settings.
published: true
date: 2023-01-23T20:41:23.348Z
tags: instamat studio
editor: markdown
dateCreated: 2023-01-23T20:33:20.852Z
---

# Preferences

![Preferences](/instamat_studio/canvas/preferences.png)

The **Preferences** Panel provides access to all of InstaMAT Studio's settings. The panel is divided into tabs for different areas of the application and project types. Additionally, <a href="#shortcuts">Keyboard Shortcuts</a> can be referenced and assigned for application operations, <a href="">Favorites</a>, and node **Quick Actions** in this panel. It is recommended to overview each of these settings to better understand how InstaMAT Studio operates and how it can be tailored to your workflow.

To reset any of the settings to their defaults, click the ![Arrow Icon](/instamat_studio/canvas/arrow_icon.png) icon next to the respective setting.

## Accessing the Preferences Panel

The Preferences Panel can be accessed from the appropriate menu based on the computer's platform.

| Platform | Menu Location |
| ---| ---|
| macOS | InstaMAT > Preferences |
| Windows | Edit > Preferences |

Additionally, the panel can be opened with the keyboard shortcut <kbd>Cmd/Ctrl + ,</kbd> (comma).

## Interface Overview

The following overviews each tab and the subsequent settings within them.

### Application

These settings apply to the general application.

#### User Paths

<img src="/instamat_studio/canvas/preferences_user_paths.png" alt="User Paths section in Preferences" />

This area allows the user to provide multiple paths for InstaMAT's <a href="../Graph_Library.html/#user-library">User Library</a>. Directories listed here will be organized with InstaMAT's folder structure. Packages placed in the "Library" subdirectory will be accessible within InstaMAT Studio through the <a href="">Graph Library</a>, <a href="">Quick Search</a>, and the <a href="">Asset Picker</a> Panel.


#### Application

- **Output Log Line Count**: The amount of lines visible in the <a href="">Output Log</a>
- **Auto-Save**: Enables, Disables, and sets the duration for when the project and package is automatically saved

> Auto-Saved packages are found in the "AutoSave" directory commonly found in the `~/Documents/InstaMAT` folder. If a disruption to InstaMAT Studio occurs, an Auto-Saved package can be restored upon relaunch.
{.is-info}

- **Application Skin**: The skin applied to the application's interface. Choose between `Dark` and `Light` Adjustments to this setting occur after restarting the application.

### Interface

These settings apply to the application's interface.

#### General

- **Maximum Graph Execution Size**: Sets the maximum execution size for a graph. Limiting this size can prevent accidentally selecting a large resolution that would result in issues with the GPU.
- **Wheel Scrolling Mode**: Determines the behavior of some UI elements and widgets when interacting with the scroll wheel
- **Reset Button Policy**: Determines the behavior of the ![Rest Button Icon](/instamat_studio/canvas/arrow_icon.png) button in the <a href="">Graph Object Editor</a> when resetting a parameter back to its default value. The button can be set to `Always Show` when a change has been made, or `Show When Hovered`.
- **Show Welcome Screen**: Toggles, showing the <a href="">Welcome Screen</a> upon application startup
- **Show Contextual Help**: Toggles displaying extra help and information on how certain controls can be used. This information is displayed in the status bar along the bottom of the application.
- **Reset Preferences and Settings**: Resets the application preferences and settings. This action occurs after restarting the application.
- **Reset Warnings**: Resets warnings that have been set to not be shown again
- **Generate Previews**: Toggles the automatic generation of a cached thumbnail if it is not already available

#### Image Viewer

- **Automatic Tonemapping**: Toggles automatically turning on Tonemapping in the <a href="../Image_Viewer.html">Image Viewer</a>. This is determined based on the color space of the previewed output.

### Shortcuts

<img src="/instamat_studio/canvas/preferences_shortcuts.png" alt="Shortcuts tab in Preferences" />

This tab is where all of InstaMAT Studio's shortcut hotkeys can be referenced and set. Shortcuts can be filtered using the dedicated search bar at the top of the tab.

To set a shortcut: 

1. Find or search for the desired action or node
2. Click the entry field next to the shortcut's name
3. Enter the desired key combination

A dialog will appear if a key combination is already in use. To reset a shortcut to its default, click the ![Reset Icon](/instamat_studio/canvas/arrow_icon.png) icon. Once a shortcut is assigned or adjusted, the application will need to restart in order for it to come into effect.

Shortcuts are broken down into categories for the general application, <a href="">Canvas</a> and <a href="">Layering</a> interfaces, <a href="">Viewport</a>, <a href="">Favorites</a> and Quick Actions.

#### Favorites

Assigning a hotkey to a favorited node automatically instances it in the Canvas.

#### Quick Actions

Some nodes such as the <a href="">Blend</a> node have Quick Actions. These are useful actions associated with that particular node. In the case of the Blend node, a Quick Action can be performed to swap the `Foreground` and `Background` input connections.

<img src="/instamat_studio/canvas/swap_input_parameters.gif" alt="Swapping Input Parameters on a Blend node" />

To assign a shortcut to a Quick Action:

1. Click on the node with an available Quick Action in the Canvas
2. Open the Preferences Panel and choose the `Shortcuts` tab
3. Scroll to the bottom to find Quick Actions that can receive an assigned Shortcut
4. Click the entry field next to the shortcut's name
5. Enter the desired key combination

### Advanced

These settings are for advanced features and functions.

- **Allow GPU Use for Neural Nodes**: Determines if AI-based nodes can use the GPU or if they are executed on the CPU only
- **Execute Rendering on Idle Mouse**: Executes rendering only if the mouse is idling
- **Show Advanced Features**: Shows advanced features in InstaMAT Studio's UI
	- **Library Objects**: Shows advanced nodes in the <a href="">Graph Library</a>. These nodes appear with a ![Advanced icon](/instamat_studio/canvas/advanced_icon.png) in the top left corner when instanced in a graph.
	- **Parameters**: Shows advanced parameters in the <a href="../Graph_Object_Editor.html">Graph Object Editor</a> and <a href="../Graph_Variable_Editor.html">Graph Variable Editor</a>

### Canvas

These settings apply to the <a href="../../../Canvas_Overview.html">Canvas</a> interface. Many of these settings also have <a href="../Canvas_Toolbar.html">Canvas Toolbar</a> button counterparts.

- **Canvas Update Time Delay Mode**: Determines the rendering priority of the <a href="">Image Viewer</a> versus the Canvas Previews. Increasing the speed will result in faster Canvas Preview generation. A slower speed will prioritize the <a href="../Image_Viewer.html">Image Viewer</a>'s preview.
- **Connection Rendering Mode**: Determines the style in which connections are drawn in the Canvas
- **Mouse Wheel Behavior**: Determines how the Canvas reacts to scrolling the mouse wheel
- **Mouse Drag Zoom Speed**: Determines the speed at which the Canvas will zoom when <kbd>Right Clicking</kbd> and dragging
- **Double Click Behavior**: Determines the behavior when <kbd>Double Clicking</kbd> a node in the Canvas. The action can result in opening the graph or previewing its output.
- **Arithmetic Font Size**: Adjusts the font size for expression elements
- **Arithmetic Row View**: Determines which representation to use for expression elements - row or column
- **Automatically Render Graph**: Enables the graph to automatically render if a change is made
- **Automatically Switch Grayscale Modes**: When enabled, a node in the Canvas can automatically switch between grayscale and color information when connected to a graph input
- **Flash Rendered Entities**:  When enabled, nodes that are executed will flash with a yellow outline. This helps to visually determine which section of the graph is being utilized when changes are being made.
- **Preview Images**: Toggles the Canvas Previews
- **Visualize Constants**: Displays a popup visualization of disconnected input values on nodes in the Canvas
- **Render Unconnected Nodes**: When disabled, nodes that are disconnected from a graph output are not rendered. Useful when optimizing a graph to only execute nodes that are actively used.
- **Show Timings**: Toggles the execution timings which are visible on both the Canvas background and on individual nodes
- **Collapse Colors and Images**: Represents constant colors and images in the Canvas with a smaller form factor
- **Anti-Aliasing**: Performs Anti-Aliasing on rendering in the Canvas. This action requires the application to restart.
- **Auto-Scrolling**: Enables automatic scrolling when dragging a node close to a border of the Canvas graph view
- **Show Snapshot Settings**: Shows the **Snapshot Settings** Dialog first when taking a **Canvas Snapshot**

> A Canvas Snapshot is an image of the Canvas's graph layout. To take a Canvas Snapshot, go **Canvas** > **Canvas Snapshot**.
{.is-info}

- **Lock Comments**: When enabled, comments are locked and cannot be accidentally selected or moved
- **Show Minimap**: Enables the <a href="../Minimap.html">Minimap</a>
- **Minimap Position**: Determines which corner of the Canvas the <a href="../Minimap.html">Minimap</a> will appear
- **Minimap Opacity**: Sets the visual opacity of the <a href="../Minimap.html">Minimap</a>

### Layering

These settings apply to the <a href="">Layering</a> interface.

- **Hide Brush Preview for Hovering Pen**: Hides the **Brush Preview** when painting. This is useful when using an input device that does not have 'hover' capabilities.
- **Allow Mip Mapping in Layering**: Allows Mip Mapping in Layering projects. By default, Mip Mapping is disabled to improve performance.

### Viewport

![GPU Info](/instamat_studio/canvas/preferences_gpu_info.png)

This tab displays information on the computer's GPU.