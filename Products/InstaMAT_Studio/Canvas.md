---
title: Canvas
description: The Canvas is InstaMAT's node-based interface used to build 3D assets, PBR materials, and powerful workflows with immense flexibility.
published: true
date: 2023-03-08T16:38:11.363Z
tags: instamat studio, canvas
editor: markdown
dateCreated: 2023-01-24T08:04:55.732Z
---

The Canvas is InstaMAT's node-based interface used to build 3D assets, PBR materials, and  powerful workflows with immense flexibility. With an assortment of graph types, easy drag-and-drop integration with other InstaMAT projects, and the ability to combine images, meshes, and point clouds, the Canvas becomes an infinite playground for building dynamic assets and procedural pipelines.

## Getting Started with the Canvas

![canvas_ui_rounded_preview2.jpeg](/instamat_studio/canvas/canvas_ui_rounded_preview2.jpeg =400x){.align-right} Learn how to begin working in InstaMAT's flexible and powerful node-based interface with the following articles:

- [Canvas Interface](/Products/InstaMAT_Studio/Canvas/Canvas_Interface): Discover and learn the interface elements that make up InstaMAT's Canvas UI.
- [Canvas Navigation](/Products/InstaMAT_Studio/Canvas/Canvas_Navigation): Learn how to navigate the Canvas interface.
- [Node-Based Workflow Key Concepts](/Products/InstaMAT_Studio/Canvas/Node_Based_Workflow_Key_Concepts): Uncover the power of a node-based workflow by tapping into its non-linear nature. Learn about graph inheritance, making connections, exposing inputs and outputs, and how to create infinite variations by changing a graph's execution seed.
- [InstaMAT Project Integration](/Products/InstaMAT_Studio/InstaMAT_Project_Integration): Learn how to extend the functionality of InstaMAT's many project types by integrating them into an Element Graph. Blend a Materialize Image project with a few of the many stunning materials within InstaMAT's built-in [library](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Graph_Library). Expand upon a Layering project by supplying it with all of the Canvas's nodes and features. 

> The Canvas is one of many ways to approach texture and material creation. With `Layering`, artists can create scalable workflows using a familiar layer-based approach to build up an asset from scratch. `Material Layering` is a powerful project type making it easy to combine materials together to form a more complex result. What's more is that these layer-based projects can be extended by [exposing adjustable parameters](/Products/InstaMAT_Studio/Canvas/Node_Based_Workflow_Key_Concepts#creating-and-exposing-graph-inputs-custom-parameters) and [instancing them](/Products/InstaMAT_Studio/Canvas/Node_Based_Workflow_Key_Concepts#instancing-graphs) in an `Element Graph`. The sky's the limit on how to approach your projects!
{.is-info}

## Canvas Project Types

Learn about the different project types that can be built using the Canvas.

### Atom Graph

![atom_preview.png](/instamat_studio/canvas/atom_preview.png =400x){.align-right} An **Atom** is an image-processing program that runs on the GPU. With the intuitive `Control Flow` connection system, traditional programing operations such as branching and looping are possible determining the order in which the graph is executed.

[Click here to learn more about the Atom Graph]()
<br style="clear: right;"/>

### Element Graph

![element_preview.png](/instamat_studio/canvas/element_preview.png =400x){.align-right} The **Element Graph** is the Swiss Army knife of project types in InstaMAT. Create stunning materials, build powerful mesh-processing pipelines, and combine different mediums such as images, meshes, and point clouds. Expressions and arithmetic can also be integrated directly into the same graph along side your materials to customize and direct [exposed parameters](/Products/InstaMAT_Studio/Canvas/Node_Based_Workflow_Key_Concepts#creating-and-exposing-graph-inputs-custom-parameters). These parameters can be adjusted within InstaMAT Studio, [InstaMAT Pipeline](/Products/InstaMAT_Pipeline), or in our [integrated plugins](/Products/Integrations).


[Click here to learn more about the Element Graph]()
<br style="clear: right;"/>

### nPass Element Graph

![npass_preview.png](/instamat_studio/canvas/npass_preview.png =400x){.align-right} The **nPass Element Graph** unlocks the power of iteration by persisting data across multiple passes. This makes complex processes like simulations and scatters a streamlined and straightforward process. There is no limit to the type of data that can be iterated upon such as mesh data, strings, and image buffers. Many nodes within InstaMAT's node library were created with the nPass graph such as `Mesh Drop On Topology` and the `Mesh Array` node.

[Click here to learn more about the nPass Element Graph]()
<br style="clear: right;"/>

### Function Graph

![function_preview.png](/instamat_studio/canvas/function_preview.png =400x){.align-right} The **Function Graph** is a small function node that can be reused inside <a href="">Atom Graphs</a>. While this is similar to the Atom Graph, the difference is that a Function Graph can have non-image output parameters.


[Click here to learn more about the Function Graph]()
<br style="clear: right;"/>