---
title: Node-Based Workflow Key Concepts
description: This article overviews the important key concepts needed to understand while working in a node-based workflow in InstaMAT Studio's Canvas interface.
published: true
date: 2023-02-26T18:18:01.247Z
tags: instamat studio
editor: markdown
dateCreated: 2023-02-23T19:16:50.444Z
---

# Node-Based Workflow Key Concepts

This article overviews the important key concepts needed to understand while working in a node-based workflow in InstaMAT Studio's [Canvas](/Products/InstaMAT_Studio/Canvas) interface.

## Non-linear Node Concepts

Working in the Canvas is like building a recipe. Instead of performing each step manually, the **instructions** themselves are created in the form of `nodes`. These nodes pass information from left to right via node `connections` which then get processed down the chain until they reach a `graph output`. This graph output could be an image, mesh, value, point cloud... with the Canvas the possibilities are endless.

What makes this different from a linear process is that a node can be modified, removed, or replaced at any time which results in a non-linear workflow. Each set of instructions can build upon the next. A change earlier on in the sequence of nodes can have a significant effect on the end result. This makes working with nodes astronomically more powerful. Drastic changes can be made just as easily as small tweaks. Nodes are the graphical representation of a non-distructive workflow.

## Instancing Graphs

A node is a graph packaged up into a singular form. Every time a node is brought into the Canvas, the result is a graph that is being instanced. This means that any change to the parameters or properties of this node are specific to this instance and do not change the defaults of the original graph. Any graph can be turned into a node by dragging it from the [Package Management](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Package_Management) panel into another graph in the Canvas.

> In InstaMAT Studio, entire projects such as a `Layering` project or `Materialize Image` project can be dragged into the Canvas and used as a singular node.{.is-info}

You can think of nodes as "sub-graphs". Being able to compartmentalize graphs into sub-graphs is one of the benefits of a node-based workflow. If you find yourself performing the same set of actions multiple times, packaging up a set of nodes into a sub-graph will allow you to reuse that functionality as many times as you'd like.

> Most nodes in InstaMAT Studio are made with the same tools and project types available to you. For example, the `Blend` node is an `Atom Graph`. The `Mesh Scatter on Topology` node is an `nPass Element Graph`. Even the `Mesh Render` node, which is an entire PBR renderer, was created within InstaMAT Studio. To learn more about how they were constructed, <kbd>Double Click</kbd> on a node to dive into its contents. {.is-info}

## Creating and Exposing Graph Inputs (Custom Parameters)

InstaMAT Studio lets you pick and choose properties from the nodes within a graph and combine those settings together into one location for easy tweaking. This process is called exposing graph inputs. Once exposed, these properties can be controlled from outside of the graph, whether it has been instanced in another graph, used in another project like in `Layering`, or controlled with one of our Integrated Plugins.

With exposed graph inputs, InstaMAT materials become infinately more reusable. For example, a forest ground material with options to change the amount of grass, twigs, and scattered leaves now has the ability to be used in any future project where there is a forest ground. The material only needs to be created once, then an artist can adjust the physical characteristics at will.

## Global/Local Execution Resolution and Seed

Each graph has a `Global Seed` number. This can be found in the [Canvas Toolbar](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Canvas_Toolbar) marked with a <i class="fa-regular fa-seedling"></i> icon. This number is used to generate the randomized values for the nodes that contain varried characteristics within it.

For example, the `Tile Scatter` node which randomly distributes images across the texture square has an `Offset Varaince` parameter. When increased, the tiles will have randomized positions. Once changed, the `Global Seed` will reshuffle all nodes that have randomized attributes like this one.

When building a procedural material in the `Element Graph`, adjusting the `Global Seed` value will result in a new material that follows the same recipe but with varried results. This makes it easy to provide an infinite amount of variations of the same material.

The `Local Seed` belongs to a singular node. Changing this value will only reshuffle the randomized properties of the node it belongs to. This is useful if you'd like to find an alternative result without changing the outcome of every other node in the graph.

The `Local Seed` can be found at the top of the [Graph Object Editor](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Graph_Object_Editor) under the `Instance Properties` section after selecting a node in the Canvas.

## Inheritance

In the Canvas, nodes are able to pick up particular attributes from either their parent graph or the node providing them input information. In other words, nodes can *inherit* traits.

The traits that can be inherited are:

- Format Type
- Width
- Height

This means that a node can determine its size and format based on the size and format of the node providing its input information or the graph that it resides in. Therefore, if the parent's traits change, these adjustments cary through to any nodes that inherit that information.

These properties can be located at the top of the [Graph Object Editor](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Graph_Object_Editor) panel under the  `Element Format` section after selecting a node in the Canvas.

Inheritance can be applied by setting the node's `Format Type` to any of the following:

- **Inherit**: The format will be inherited from the parent graph.
- **DeriveFromFirstAvailableImageInput**: The format will be set based on the node connected to the first available 'Image' type graph input.
- **InheritFormatDeriveSizeFromFirstAvailableImageInput**: The format will be inherited from the parent graph and the size will be set based on the node connected to the first available 'Image' type graph input.

## Templates

`Templates` are a special type of graph instance. Templates appear as a resource in the [Package Management](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Package_Management) panel and in the [Graph Library](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Graph_Library). They allow for a node's parameters to be saved as a preset which can then be reused in other graphs. They then can then be added to a machine's [User Library](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Graph_Library#user-library) for use in other `Packages`. 

Templates appear as "first-class citizens" meaning that when searching for them with [Quick Search](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Quick_Search) or in the `Graph Library` they will appear the same as an item made directly from a graph.

For example, when creating a PBR material using the `Element Graph`, templates can be made for often-used variations. These templates can be assigned to a category in the library and easily accessed with `Quick Search`.

> Many of the materials that ship with InstaMAT Studio are created using the Template system. To discover how these materials were created, <kbd>Double Click</kbd> them in the `Graph Library`. If a material is a template, a special graph will be shown in the Canvas view. <kbd>Double Clicking</kbd> the node in this graph will reveal the original Element that the template was made from. {.is-info}


To create a template:

1. Select a single node instance in the Canvas
2. Go to `Canvas` > `Create Template From Instance` or use the keyboard shortcut <kbd>Cmd/Ctrl</kbd> + <kbd>T</kbd>
3. In the provided dialog, give the template a Name, Category, and Description and click `Okay`