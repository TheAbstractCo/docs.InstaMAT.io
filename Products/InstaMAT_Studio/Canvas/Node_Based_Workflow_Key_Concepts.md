---
title: Node-Based Workflow Key Concepts
description: This article overviews the important key concepts needed to understand while working in a node-based workflow in InstaMAT Studio's Canvas interface.
published: true
date: 2023-02-23T19:39:23.369Z
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

A node is a graph packaged up into a singular form. Every time a node is brought into the Canvas, the result is a graph that is being instanced. Any graph can be turned into a node. In InstaMAT Studio, entire projects can be dragged into the Canvas and used as a singular node.

## Creating and Exposing Graph Inputs (Custom Parameters)

## Global/Local Execution Resolution and Seed

## Graph Inheritance

## Templates