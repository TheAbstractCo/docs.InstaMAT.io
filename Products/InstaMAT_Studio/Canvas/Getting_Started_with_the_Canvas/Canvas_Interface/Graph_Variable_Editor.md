---
title: Graph Variable Editor
description: The Graph Variable Editor (GVE) provides fine tune control and adjustments to variables such as Graph Inputs, Local Variables, and Graph Outputs.
published: true
date: 2023-01-27T17:46:35.187Z
tags: instamat studio, canvas
editor: markdown
dateCreated: 2023-01-23T15:42:40.580Z
---

# Graph Variable Editor

<img src="/instamat_studio/canvas/graph_variable_editor_elementimage.png" width="400"/>

The **Graph Variable Editor** (GVE) provides fine tune control and adjustments to variables such as Graph Inputs, Local Variables, and Graph Outputs. To learn more about these variables, please read our article on the <a href="">Graph Object Editor</a>. 

## Interface Overview

![Graph Variable Editor Editing a Value](/instamat_studio/canvas/graph_variable_editor_value.png =400x){.align-right} The Graph Variable Editor's list of controls adapts depending on the item selected in the <a href="">Canvas</a>. The following is an overview of the available controls.

- **Name**: The name of the variable.
- **Type**: The variable's type.
- **Control**: The UI control widget used to manipulate the data. Depending on the variable's type this list will change based on the available compatible widgets.
- **Color Space**: The colorspace used if the variable type is an ElementImage.
- **Color**: The default color/value used if the variable type is an ElementImage or ElementImageGray.
- **Image**: The default image used if the variable type is an ElementImage or ElementImageGray.
- **Value**: The default value of the variable.
- **Rotation Start**: The location of 0 degrees if the chosen widget is a VectorAngular.
- **Rotation Direction**: The rotation direction of `Clockwise` or `Counterclockwise` if the chosen widget is a VectorAngular.
- **Range**: The minimum and maximum range if the chosen widget is a Slider.
- **Category**: The category assigned to the variable. Input parameters with the same category will be grouped together in the <a href="">Graph Object Editor</a> and can be combined together using <a href="">Link Category Mode</a>.
- **Documentation**: Documentation text for the variable. This can be used to provide the user with information about the effect on the resulting image or graph. The text appears in a tooltip when hovering over the variable in the <a href="">Graph Object Editor</a>.
- **Visibility Expression**: An expression used to hide an Input Parameter based on a condition.

> To learn more about Visibility Expressions or *VisEx*, please read our dedicated article: <a href="">Visibility Expressions</a>.
{.is-info}


- **Usage Semantic**: A semantic that can be used to perform additional soft validation on Input Parameters. If the semantic does not match, a warning will be emitted but the graph will still execute.