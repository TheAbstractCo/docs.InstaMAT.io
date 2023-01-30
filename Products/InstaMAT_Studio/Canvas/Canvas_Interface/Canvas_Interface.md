---
title: Canvas Interface 2
description: InstaMAT Studio's Canvas UI provides a flexible working environment to focus on the task at hand.
published: true
date: 2023-01-30T13:45:37.100Z
tags: instamat studio, canvas
editor: markdown
dateCreated: 2023-01-24T08:07:42.220Z
---

# Canvas Interface Overview

![canvas_interface_numbered.png](/instamat_studio/canvas/canvas_interface_numbered.png)


InstaMAT Studio's Canvas interface is made up of four parts: The Left Panel, Right Panel, Center Area, and the Toolbar.

## <i class="fa-regular fa-circle-1"></i> Left Panel

![Left Panel](/instamat_studio/canvas/left_panel_gif.gif =400x){.align-right}The left panel contains the following tabs:

- <i class="fa-regular fa-flux-capacitor"></i> [Graph Library](/Products/InstaMAT_Studio/Canvas/Getting_Started_with_the_Canvas/Canvas_Interface/Graph_Library): Provides access to the vast node library that is built into InstaMAT Studio. Nodes are broken down into categories and are easily searchable either from the dedicated search box or by using <a href="">Quick Search</a>. The Graph Library also contains the items from your personal <a href="">User Library</a> and is sorted based on a graph's assigned category.
- <i class="fa-regular fa-box-open"></i> [Package Management](/Products/InstaMAT_Studio/Canvas/Getting_Started_with_the_Canvas/Canvas_Interface/Package_Management): Contains all of the resources within the active package file. This includes projects, images, meshes, point clouds, baked mesh data, and baking settings. At the bottom of the panel is the **Meta Data** section containing the meta data for the active package.
- <i class="fa-regular fa-gear"></i> [Viewport Settings](/Products/InstaMAT_Studio/Canvas/Getting_Started_with_the_Canvas/Canvas_Interface/Viewport_Settings): Houses the various camera, environment, and render settings for InstaMAT Studio's 3D viewport. Some additional settings are included for the generated Canvas node previews and <a href="">Image Viewer</a>.

<br style="clear: right;"/>

## <i class="fa-regular fa-circle-2"></i> Right Panel

![Right Panel](/instamat_studio/canvas/right_panel_gif.gif =500x){.align-right} By default, the right panel is split into two parts. The top contains the following tabs:

- <i class="fa-regular fa-flux-capacitor"></i> [Graph Object Editor](/Products/InstaMAT_Studio/Canvas/Getting_Started_with_the_Canvas/Canvas_Interface/Graph_Object_Editor): Provides contextual access to a selected object's properties. From here various operations such as the creation of inputs and outputs, the adjustment of a node's <a href="">exposed parameters</a>, and the assignment of various meta data to a graph can be performed. By selecting multiple nodes in the Canvas, the Graph Object Editor (GOE) displays a table of execution times making it easier to determine which nodes require more processing time.
- <i class="fa-regular fa-lambda"></i> [Graph Variable Editor](/Products/InstaMAT_Studio/Canvas/Getting_Started_with_the_Canvas/Canvas_Interface/Graph_Variable_Editor): Provides specific adjustments for graph variables such as a public **Graph Input** or a private **Local Variable**.

<br style="clear: right;"/>

![Viewport and Image Viewer](/instamat_studio/canvas/viewport_image_viewer_gif.gif =500x){.align-right} By default, the bottom contains:

- <i class="fa-regular fa-cube"></i> <a href="">Viewport</a>: A physically-based 3D viewport illuminated by an environment image. Many aspects of the viewport can be customized with the [Viewport Settings](/Products/InstaMAT_Studio/Canvas/Getting_Started_with_the_Canvas/Canvas_Interface/Viewport_Settings) panel.
- <i class="fa-regular fa-image-polaroid"></i> <a href="">Image Viewer</a>: A 2D Image Viewer that provides access to various useful features such as a tiling preview, rulers, individual channel filtering, and tabs that can simplify A/B testing.

<br style="clear: right;"/>

## <i class="fa-regular fa-circle-3"></i> Center Area


By default, the center area contains the Canvas itself where nodes are instanced and connections are made between them. Various nodes, projects, media types, and variables can be dragged into the canvas or instantiated with <a href="">Quick Search</a> to build out the graph. Connections can be made by dragging from a node's input or output.

![canvas_center_view.gif](/instamat_studio/canvas/canvas_center_view.gif =700x){.align-center}

>### Learn the Ins and Outs of the Canvas
>To learn more about working in the Canvas check out these articles:
>
>- <a href="">Working in the Canvas</a>: Learn how to navigate and work within InstaMAT's Canvas to begin building procedural materials and workflows. Leverage how the Canvas UI can adapt to different use cases by swapping the position of the Viewport, Canvas, and Image Viewer to your liking. Discover how to take advantage of the many tools at your disposal to clean up your graphs with comments and reroute nodes as your projects get more complex.
> - <a href="">Node-Based Workflow Key Concepts</a>: Uncover the power of a node-based workflow by tapping into its non-linear nature. Learn about graph inheritance, how to expose input parameters and create outputs, and explore the power of changing a graph's execution resolution and seed. These key concepts drive the core of working within the Canvas.
{.is-info}

## <i class="fa-regular fa-circle-4"></i> Toolbar

![Canvas Toolbar with sections numbered](/instamat_studio/canvas/canvas_toolbar_2.png)


The **Canvas Toolbar** is divided up into multiple sections and contains shortcuts to many of the various tools and Canvas functionality. The toolbar is organized into the following groups:

1. **Undo History**: Displays a popup of the session's undo history allowing the user to jump back to a previous point.
2. **Global Execution Resolution**: Controls the execution resolution and format for the active graph.
3. **Global Seed**: Controls the global seed of the active graph.
4. **Center View Selection**: Determines which view takes up the center area (Canvas, Viewport, or Image Viewer)
5. **Project Management**: Creates a new project, saves the current project, or opens the  <a href="">Output Export Dialog</a>.
6. **Additional Panels**: Opens the <a href="">Baking Panel</a>, <a href="">Raytracing</a>, or Output Log.
7. **Canvas Tools and Display Functions**: Provides control over various Canvas functionality and display options.
8. **Graph Performance Tools**: Gives access to various graph performance and execution tools.

>To learn more about the Canvas Toolbar and each individual section, please read our dedicated article: <a href="">Canvas Toolbar</a>. You can also view our <a href="">walkthrough video</a> on our YouTube channel.
{.is-info}

![Tab bar with a few open projects](/instamat_studio/canvas/tab_bar.png)

Below the toolbar is the **Tab Bar** filled with the projects that are currently open. Tabs can be reordered by dragging and dropping. <kbd>Right Click</kbd> a tab to bring up a contextual menu that does the following:

- Close all tabs
- Close this tab
- Close other tabs