---
title: Node-Based Workflow Key Concepts
description: This article overviews the important key concepts needed to understand while working in a node-based workflow in InstaMAT Studio's Canvas interface.
published: true
date: 2023-02-23T19:52:35.289Z
tags: instamat studio
editor: markdown
dateCreated: 2023-02-23T19:16:50.444Z
---

# Node-Based Workflow Key Concepts

This article overviews the important key concepts needed to understand while working in a node-based workflow in InstaMAT Studio's Canvas interface.

## Non-linear Node Concepts

Working in the Canvas is like building a recipe. Instead of performing each step manually, the **instructions** themselves are created in the form of `nodes`. These nodes pass information from left to right via node `connections` which then get processed down the chain until they reach a `graph output`. This graph output could be an image, mesh, value, point cloud... with the Canvas the possibilities are endless.

What makes this different from a linear process is that any node can be modified, removed, or replaced at any time which results in a non-linear workflow. Each set of instructions can build upon the next. A change earlier on in the sequence of nodes can have a significant effect on the end result. This makes working with nodes astronomically more powerful. Drastic changes can be made just as easily as small tweaks. Nodes are the graphical representation of a non-distructive workflow.

## Instancing Graphs

A node is a graph packaged up into a singular form. Every time a node is brought into the Canvas, the result is a graph that is being instanced. Any graph can be turned into a node by dragging it from the [Package Management](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Package_Management) panel into another graph in the Canvas.

> In InstaMAT Studio, entire projects such as a Layering project or Materialize Image project can be dragged into the Canvas and used as a singular node.{.is-info}

You can think of nodes as "sub-graphs". Being able to compartmentalize graphs into sub-graphs is one of the benefits of a node-based workflow. If you find yourself performing the same set of actions multiple times, extracting a set of nodes into a sub-graph will allow you to reuse that functionality as many times as you'd like.

> Most nodes in InstaMAT Studio are made with the same tools and project types available to you. For example, the `Blend` node is an Atom Graph. The `Mesh Scatter on Topology` node is an nPass Element Graph. Even the Mesh Render node, which is an entire PBR renderer, was created within InstaMAT Studio. To learn more about how they were constructed, <kbd>Double Click</kbd> on a node to dive into its contents. {.is-info}

## Creating and Exposing Graph Inputs (Custom Parameters)

## Global/Local Execution Resolution and Seed

## Graph Inheritance

## Templates