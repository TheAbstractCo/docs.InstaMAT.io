---
title: Graph Object Editor
description: The Graph Object Editor (GOE) panel provides contextual access to a selected object's properties.
published: true
date: 2023-01-26T17:51:25.925Z
tags: instamat studio
editor: markdown
dateCreated: 2023-01-20T19:07:34.713Z
---

# Graph Object Editor
> This page is currently under development. :construction:
{.is-warning}


<img src="/instamat_studio/canvas/goe.png" alt="Graph Object Editor Panel" width="400"/>

The **Graph Object Editor** (GOE) panel provides contextual access to a selected object's properties. From here, various operations such as the creation of inputs and outputs, the adjustment of a node's <a href="">exposed parameters</a>, and the assignment of various meta data to a graph can be performed. Much of the majority of the interaction within the Canvas involves selecting a node and making adjustments to its properties with this panel.

The GOE's UI and categories adjust based on the type of object selected. Selecting a *node* will display the properties of that node such as its Element Format settings, Instance Properties, Inputs, and Outputs. Clicking on the **Canvas** in a blank area will display the properties of the currently active *graph*. In addition to the graph's Inputs and Outputs, its Local Variables, Versioning, and the graph's Meta Data are also found in the GOE.

This article breaks down the interface of the Graph Object Editor based on the type of object selected.


## Node
When a node is selected, the Graph Object Editor displays the following information.

## Node {.tabset}

### Information

#### Information
When a node is selected in the Canvas, the following categories and interface elements appear in the GOE.

<img src="/instamat_studio/canvas/goe_top_node.png" width="400" />

At the top are the the following node attributes:

- Name
- Category
- Description
- Author
- Version Number

### Element Format

#### Element Format

This section determines the node's format and execution size.

<img src="/instamat_studio/canvas/goe_element_format.png" width="400" />

- **Format Type**: The method in which the node will be executed. The format can be set to the following options
	- **Normalized8, Normalized16, FullRange16, FullRange32**: This will manually set the format regardless of any parent graph inheritance or connected node inputs.
	- **Inherit**: The format will be inherited from the parent graph.
	- **DeriveFromFirstAvailableImageInput**: The format will be set based on the node connected to the first available 'Image' type graph input.
	- **InheritFormatDeriveSizeFromFirstAvailableImageInput**: The format will be inherited from the parent graph and the size will be set based on the node connected to the first available 'Image' type graph input.
- **Width** and **Height**: The size at which the node will be executed.
- **Absolute Size**: If enabled, the node's size will be determined by a specific resolution instead of a relative size.   

#### Relative and Absolute Execution Size
There are two methods to determine a node's execution size: Relative and Absolute. The method is chosen based on the status of the `Absolute Size` switch.

| 'Absolute Size' Switch | Method |
| --- | --- |
| Enabled | Absolute: The node will be executed at a constant size such as *'1024' x '1024'*. |
| Disabled | Relative: The node will either `Inherit` the size if selected, or be executed at a relative size to the parent graph such as */2* or **4*.

### Instance Properties

#### Instance Properties

This section determines the execution seed, if a node is active or disabled, and toggles the node's grayscale/color permutation resulting in the node outputting grayscale or color data.

<img src="/instamat_studio/canvas/goe_instance_properties_small.png" width="400" />

- **Seed**: The execution seed for the node. All parameters and internal nodes that supply variation derive their random attributes from this seed. For example: If the selected node is a material, changing the seed will result in a new variation of that material. If the node is a noise, changing the seed will result in a variation of that noise.
- **Active**: Sets whether the node is "Active" or "Disabled". Disabled nodes display a <i class="fa-regular fa-snooze"></i> icon in the top left corner next to their name in the Canvas view. Nodes that have a `Background` or `Image` input will pass that information through to the output. 

> A shortcut for disabling nodes is highlighting the node and pressing <kbd>H</kbd>. You can also <kbd>Right click</kbd> the node to bring up the contextual menu and choose `Enable/Disable Node`. To learn more about disabling nodes, check out our <a href="">dedicated video</a> on our YouTube channel.
{.is-info}

- **Grayscale**: Determines the grayscale/color permutation of the node. Enabling will output grayscale information.

> #### Grayscale and Color Information
> Nodes in InstaMAT can choose to output either grayscale or color information. When adding a node with <a href="Quick_Search.html">Quick Search</a>, the compatible permutation will automatically be enabled. When connecting a node already in the Canvas with the opposing permutation enabled, a converter node will be inserted between the two nodes.
>
> For example: spawning a node that outputs grayscale information from a color image input pin will result in a converter node inserting between the two.
>
> ![GIF of both scenarios: QS and Converter](/instamat_studio/canvas/canvas_permutations.gif)
{.is-info}

### Inputs

#### Inputs

This section displays a node's **Graph Inputs** also known as the node's Input Parameters. Inputs have many different data types and an assortment of widgets to control them. Specific parameter values can be typed in with the keyboard either by <kbd>Double Clicking</kbd> on each parameter or using the <i class="fa-regular fa-pencil"></i> icon.

<img src="/instamat_studio/canvas/goe_inputs_node.png" width="400" />

<br style="clear: left" />

> To learn more about how to use InstaMAT's powerful set of widgets, please read our dedicated article: <a href="">A Guide to InstaMAT's Widgets</a>.
>
>![Widgets](/instamat_studio/canvas/widgets.png)
{.is-info}

> #### Overriding Input Parameters
>
>If the UI widget such as a slider does not reach the minimum or maximum value you require, the parameter can be overridden by <kbd>Right Clicking</kbd> it to bring up the contextual menu, then choosing `Override Slider Range` This value can then be overridden temporarily or persisted in the graph.
>
><img src="/instamat_studio/canvas/override_choice_dialog.png" alt="Override Choice Dialog" width="400"/> <img src="/instamat_studio/canvas/override_dialog.png" alt="Override Slider Range Dialog" width="300"/>{.is-info}

#### Contextual Menu

<img src="/instamat_studio/canvas/goe_input_context1.png" alt="GOE Inputs Contextual Menu" width="300"/>
<img src="/instamat_studio/canvas/goe_input_context2.png" alt="GOE Inputs Contextual Menu" width="300"/>

<kbd>Right Clicking</kbd> on a Graph Input brings up a contextual menu. The listed items will vary depending on the type of input clicked. The menu contains the following possible options:

- **Load Image from Local File**: If the Graph Input is an ElementImage or ElementImageGray type, a local file from the user's machine can quickly be imported and assigned.
- **Reset to Default Value**: Resets the Graph Input to the default value.
- **Expose as Input Parameter**: Exposes the parameter as a Graph Input for the parent graph.
- **Override**: Overrides the default minimum and maximum values for the parameter.

### Outputs

#### Outputs

This section displays a node's **Graph Outputs** and the category assigned to each output.
<img src="/instamat_studio/canvas/goe_node_outputs.png" width="400" />

#### Contextual Menu

<img src="/instamat_studio/canvas/goe_outputs_context.png" alt="GOE Outputs Contextual Menu" width="300"/>

<kbd>Right Clicking</kbd> on a Graph Output brings up a contextual menu with the following options:

- **View Image**: If the Graph Output is an ElementImage or ElementImageGray type, the image is loaded into the <a href="">Image Viewer</a>.
- **View Image in New Tab**: If the Graph Output is an ElementImage or ElementImageGray type, the image is loaded into the <a href="">Image Viewer</a> in a new tab.
- **Expose as Output Parameter**: Exposes the node's output as a Graph Output for the parent graph. Learn more about Graph Outputs below.

## Graph
When a graph is selected, the Graph Object Editor displays the following information.

## Graph {.tabset}

### Information

#### Information

When a graph is selected in the Canvas by <kbd>clicking</kbd> in an empty space, the following categories and interface elements appear in the GOE.

<img src="/instamat_studio/canvas/goe_top_graph.png" width="400" />

At the top are the following graph attributes:
- Name
- Category
- Description

Use the <i class="fa-regular fa-pencil"></i> icon to set the graph's name or <kbd>Double Click</kbd> on any of the information to begin editing. Adjusting the category of the graph will determine where it appears in the <a href="">Graph Library</a>.

### Inputs

#### Inputs

This section manages the creation and manipulation of a graph's Graph Inputs also known as Input Parameters or Exposed Parameters. These inputs are public and can be adjusted from within InstaMAT Studio, <a href="">InstaMAT Pipeline</a>, and through our <a href="">Integrated Plugins</a>.

<img src="/instamat_studio/canvas/goe_inputs_graph.png" alt="GOE Inputs with Graph Selected" width="400"/>

To create a new Input Parameter:

1. Click the <i class="fa-regular fa-octagon-plus"></i> button in the top right corner of this section
2. Choose the data type for the new input
3. <kbd>Double Click</kbd> the name of the parameter to rename it

The parameter's value set in this section will be its default value when the graph is instantiated. Parameters can be re-arranged by **dragging and dropping** them into the desired order. To customize them further, use the <a href="">Graph Variable Editor</a> to do things like organizing them into categories, setting the minimum and maximum ranges, changing the graphical UI widget best used to manipulate the data, and more.

To work with a parameter in the Canvas, <kbd>drag and drop</kbd> it directly into the Canvas view where it will become a node. It can then either be connected to a matching input type, or converted using one of the many conversion nodes built into InstaMAT Studio's node library. Conversion nodes can easily be created using <a href="">Quick Search</a>.

![GIF of dragging an input into the Canvas, then using Quick Search to convert to another type.](/instamat_studio/canvas/param_convert.gif)

> To learn more about how to create and manipulate Graph Inputs, please read our article: <a href="">Node-Based Workflow Key Concepts</a>.
{.is-info}

#### Contextual Menu

<img src="/instamat_studio/canvas/goe_input_context3.png" alt="GOE Input Contextual Menu with Graph Selected" width="300"/>
<img src="/instamat_studio/canvas/goe_input_context4.png" alt="GOE Input Contextual Menu with Graph Selected" width="300"/>

<kbd>Right Clicking</kbd> on a Graph Input brings up a contextual menu with the following options:

- **Show in Variable Editor**: Shows the currently selected Graph Inputs in the <a href="">Graph Variable Editor.</a> Multiple inputs can be selected to assign the same information.
- **Load Image from Local File**: If the Graph Input is an ElementImage or ElementImageGray type, a local file from the user's machine can quickly be imported and assigned.
- **Demote to Local Variable**: Demotes the selected public Graph Input to a private Local Variable. Learn more about Local Variables below.
- **Change Variable Type to**: Quickly changes the Graph Input's data type.
- **Change UI Control Type to**: Quickly changes the Graph Input's UI control widget.
- **Search for**: Automatically populates the name of the Graph Input into the Canvas's search bar and searches for any instances of it in the graph.
- **Add Keyframe to Dope Sheet**: Creates a keyframe in the <a href="">Dope Sheet</a> at the playhead's current frame index.


### Outputs

#### Outputs

This section manages a graph's Graph Outputs. When building a procedural PBR material with the <a href="">Element Graph</a>, these outputs are the maps that generate a material's fundamental channels such as *Base Color*, *Normal*, and *Roughness.*

<img src="/instamat_studio/canvas/goe_outputs_graph.png" alt="GOE Outputs with Graph Selected" width="500"/>

To create a new Graph Output:

1. Click the <i class="fa-regular fa-octagon-plus"></i> button in the top right corner of this section
2. Choose the type for the new output
3. <kbd>Double Click</kbd> the name of the output to rename it

> When giving an ElementImage or ElementImageGray Graph Output a common PBR Material map name such as "Base Color", "Roughness", or "Ambient Occlusion", InstaMAT will automatically connect these outputs to their proper channel for viewing in the <a href="">Viewport</a>.{.is-info}

Outputs that export Image, Mesh, or Point Cloud data will be utilized in the <a href="">Output Export Dialog</a>.

>#### A Note about Categories and Link Category Mode
> Graph Inputs and Outputs can be assigned a **Category** in the <a href="Graph_Variable_Editor.html">Graph Variable Editor</a>. If multiple Graph Inputs and Outputs share the same category, they can be combined and connected together with <a href="">Link Category Mode</a>. This mode visually combines connections that share the same category making it easy to connect multiple pieces of information together. Once combined, a single connection can be dragged from the outputs of one node to the inputs of a corresponding node that shares the same category.
>
> ![GIF of using LC mode](/instamat_studio/canvas/lc_mode.gif)
{.is-info}


#### Contextual Menu

<img src="/instamat_studio/canvas/goe_output_graph_context.png" alt="GOE Output Context Menu when Graph Selected" width="300"/>
<img src="/instamat_studio/canvas/goe_output_graph_context2.png" alt="GOE Output Context Menu when Graph Selected" width="300"/>

<kbd>Right Clicking</kbd> on a Graph Output brings up a contextual menu with the following options:

- **View Image**: If the Graph Output is an *ElementImage* or *ElementImageGray* type, the image is loaded into the <a href="">Image Viewer</a>.
- **View Image in New Tab**: If the Graph Output is an *ElementImage* or *ElementImageGray* type, the image is loaded into the <a href="">Image Viewer</a> in a new tab.
- **Show in Variable Editor**: Shows the currently selected Graph Outputs in the <a href="Graph_Variable_Editor.html">Graph Variable Editor.</a> Multiple outputs can be selected to assign the same information.
- **Change Variable Type to**: Quickly changes the Graph Output's data type.
- **Change UI Control Type to**: Quickly changes the Graph Output's UI control widget.
- **Search for**: Automatically populates the name of the Graph Output into the Canvas's search bar and searches for any instances of it in the graph.
- **Add Keyframe to Dope Sheet**: Creates a keyframe in the <a href="">Dope Sheet</a> at the playhead's current frame index.

### Pickles

This section contains information about pickles. This is a test.