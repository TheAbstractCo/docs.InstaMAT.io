---
title: Quick Search
description: Quick Search is a context-sensitive search box used to perform various functions in the Canvas such as instancing nodes, creating Graph Inputs and Outputs, and accessing the contents of the active package or Graph Library.
published: true
date: 2023-01-30T13:30:06.931Z
tags: instamat studio, canvas
editor: markdown
dateCreated: 2023-01-23T17:12:11.722Z
---

# Quick Search

![Quick Search showing multiple search examples](/instamat_studio/canvas/qs_options.gif){.align-center}

**Quick Search** is a context-sensitive search box used to perform various functions in the <a href="">Canvas</a> such as instancing nodes, creating Graph Inputs and Outputs, and accessing the contents of the active <a href="">package</a> or <a href="">Graph Library</a>.

## Accessing Quick Search

There are a few ways to bring up Quick Search:

- Press the <kbd>Spacebar</kbd>
- <kbd>Right Click</kbd> on an empty space in the Canvas
- <kbd>Left Click and drag</kbd> off a connection from a node's Input or Output and let go

## Context Sensitivity
Quick Search will automatically display suggestions based on the type of information it is working with. For example, dragging a connection off of an input expecting Mesh information will result in Quick Search showing nodes that provide meshes as outputs such as the <a href="">Mesh From Height</a> node or the <a href="">Mesh Shape Generator</a>. It will continue to filter out the results as you type to show any further compatible nodes.

![Quick Search context sensitivity examples with meshes](/instamat_studio/canvas/qs_mesh.gif){.align-center}

Nodes that are Grayscale/Color permutable will automatically switch to work in the proper permutation. For example, dragging a connection off of the output of a <a href="">Perlin Noise</a> node, which outputs grayscale information, then using Quick Search to bring in a <a href="">Blend</a> node, will set the Blend to work in grayscale to match the output of the Perlin Noise.

![Quick Search context sensitivity examples with node permutations](/instamat_studio/canvas/qs_permutations.gif){.align-center}

## Creating Graph Inputs, Outputs, and Local Variables
The quickest way to create Graph Inputs, Graph Outputs, and Local Variables is with Quick Search.

### Creating Graph Inputs

1. Drag a connection off of a node's Input and let go to invoke Quick Search
2. (Optional) Type the name you would like the Graph Input to receive. Otherwise, it will inherit the name of the origin node's input.
3. Choose `Expose as graph input` from the `Action` category

![Action Category in Quick Search](/instamat_studio/canvas/qs_expose_input.png =600x){.align-center}


The Graph Input will be created and can be adjusted in the <a href="">Graph Object Editor</a> or <a href="">Graph Variable Editor</a>.

### Creating Graph Outputs

1. Drag a connection off of a node's Output and let go to invoke Quick Search
2. (Optional) Type the name you would like the Graph Output to receive. Otherwise, it will inherit the name of the origin node's output.
3. Choose `Expose as graph output` from the `Action` category

> Some nodes such as the <a href="">Height to Normal</a> node already have the name "Normal" as an output. This makes it quicker to expose a material's Normal map output because the name is already assigned. Outputs that have common PBR Material Map names are automatically assigned to the proper channels in InstaMAT Studio's <a href="">Viewport</a>.
>
> ![GIF of Normal Map output example](/instamat_studio/canvas/qs_output.gif){.align-center}
{.is-info}

### Creating Local Variables
Local Variables are similar to Graph Inputs, however they are private and can only be accessed within the graph itself. To learn more about Local Variables, read our article on the <a href="/">Graph Object Editor</a>

1. Drag a connection off of a node's Input and let go to invoke Quick Search
2. (Optional) Type the name you would like the Local Variable to receive. Otherwise, it will inherit the name of the origin node's Input.
3. Choose `Expose as local variable` from the `Action` category

The Local Variable will be created and can be adjusted in the <a href="">Graph Object Editor</a> or <a href="">Graph Variable Editor</a>.

## Extracting Information from Data Types

Quick Search can easily extract pieces of data from data types that contain multiple properties.

For example, to extract the "X" property from a Vector3 data type:

1. Drag a connection off of the Vector3 Output
2. Type **".x"** into Quick Search
3. Press <kbd>Enter</kbd>

![GIF of extraction process](/instamat_studio/canvas/qs_extract.gif)

## Favorites
Quick Search has access to your Graph Library's **Favorites** list. Branching off a connection from a node's Input or Output will automatically show a list containing compatible nodes in your Favorites list. To learn more about Favorites, please read our dedicated section in the <a href="">Graph Library</a> article.

![GIF showing Favorites](/instamat_studio/canvas/qs_favorites.gif)