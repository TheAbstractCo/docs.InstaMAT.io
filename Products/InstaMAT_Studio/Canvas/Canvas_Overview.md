---
title: Canvas Overview
description: The Canvas is InstaMAT's node-based interface used to build 3D assets, PBR materials, and  powerful workflows with immense flexibility.
published: true
date: 2023-01-20T16:46:26.914Z
tags: instamat studio, canvas
editor: markdown
dateCreated: 2023-01-20T16:46:26.914Z
---

# Canvas Overview

The Canvas is InstaMAT's node-based interface used to build 3D assets, PBR materials, and  powerful workflows with immense flexibility. With an assortment of graph types, easy drag-and-drop integration with other InstaMAT projects, and the ability to combine images, meshes, and point clouds, the Canvas becomes an infinite playground for building dynamic assets and procedural pipelines.

Check out the topics below to dive in.

## Getting Started with the Canvas

![canvas_ui_rounded_preview2.jpeg](/instant_studio/canvas/canvas_ui_rounded_preview2.jpeg)

Learn how to begin working in InstaMAT's flexible and powerful node-based interface with the following articles:

- <a href="Getting Started with the Canvas/Canvas Interface/Canvas_Interface.html">Canvas Interface</a>: Discover and learn the interface elements that make up InstaMAT's Canvas UI.
- <a href="">Working in the Canvas</a>: Learn how to navigate and work within InstaMAT's Canvas to begin building procedural materials, assets, and workflows.
- <a href="">Node-Based Workflow Key Concepts</a>: Uncover the power of a node-based workflow by tapping into its non-linear nature. Learn about graph inheritance, making connections, exposing inputs and outputs, and how to create infinite variations by changing a graph's execution seed.
- <a href="">InstaMAT Project Integration</a>: Learn how to extend the functionality of InstaMAT's many project types by integrating them into an <a href="">Element Graph</a>. Blend a <a href="">Materialize Image</a> project with a few of the many stunning materials within InstaMAT's built-in <a href="">library</a>. Expand upon a <a href="">Layering</a> project by supplying it with all of the Canvas's nodes and features. 

> ### Did you know?
> The Canvas is one of many ways to approach texture and material creation. With <a href="">Layering</a>, artists can create scalable workflows using a familiar layer-based approach to build up an asset from scratch. <a href="">Material Layering</a> is a powerful project type making it easy to combine materials together to form a more complex result. What's more is that these layer-based projects can be extended by <a href="">exposing adjustable parameters</a> and <a href="">instancing them</a> in an <a href="">Element Graph</a>. The sky's the limit on how to approach your projects!

## Atom Graph!

![atom_rounded_preview.jpeg](/instant_studio/canvas/atom_rounded_preview.jpeg)

An **Atom** is an image-processing program that runs on the GPU. With the intuitive <a href="">Control Flow</a> connection system, traditional programing operations such as branching and looping are possible determining the order in which the graph is executed.

## Element Graph

![element_rounded_preview.jpeg](/instant_studio/canvas/element_rounded_preview.jpeg)

The **Element Graph** is the Swiss Army knife of project types in InstaMAT. Create stunning materials, build powerful mesh-processing pipelines, and combine different mediums such as images, meshes, and point clouds. Expressions and arithmetic can also be integrated directly into the same graph along side your materials to customize and direct <a href="">exposed parameters</a>. These parameters can be adjusted within InstaMAT Studio, <a href="">InstaMAT Pipeline</a>, or in our <a href="">Integrated Plugins</a>.

## nPass Element Graph

![npass_rounded_preview.jpeg](/instant_studio/canvas/npass_rounded_preview.jpeg)

The **nPass Element Graph** unlocks the power of iteration by persisting data across multiple passes. This makes complex processes like simulations and scatters a streamlined and straightforward process. There is no limit to the type of data that can be iterated upon such as mesh data, strings, and image buffers. Many nodes within InstaMAT's node library were created with the nPass graph such as <a href="">Mesh Drop On Topology</a> and the <a href="">Mesh Array</a> node.

## Function Graph

![Function Graph](/instant_studio/canvas/Function_Rounded_Preview.png)

The **Function Graph** is a small function node that can be reused inside <a href="">Atom Graphs</a>. While this is similar to the Atom Graph, the difference is that a Function Graph can have non-image output parameters.