---
title: Graph Object Editor
description: The Graph Object Editor (GOE) panel provides contextual access to a selected object's properties.
published: true
date: 2023-02-13T13:45:23.268Z
tags: instamat studio
editor: markdown
dateCreated: 2023-01-20T19:07:34.713Z
---

# Graph Object Editor

![Graph Object Editor Panel](/instamat_studio/canvas/goe.png =400x){.align-center}

The **Graph Object Editor** (GOE) panel provides contextual access to a selected object's properties. From here, various operations such as the creation of inputs and outputs, the adjustment of a node's <a href="">exposed parameters</a>, and the assignment of various meta data to a graph can be performed. Much of the majority of the interaction within the Canvas involves selecting a node and making adjustments to its properties with this panel.

The GOE's UI and categories adjust based on the type of object selected. Selecting a *node* will display the properties of that node such as its Element Format settings, Instance Properties, Inputs, and Outputs. Clicking on the **Canvas** in a blank area will display the properties of the currently active *graph*. In addition to the graph's Inputs and Outputs, its Local Variables, Versioning, and the graph's Meta Data are also found in the GOE.

This article breaks down the interface of the Graph Object Editor based on the type of object selected.


## Node
When a node is selected, the Graph Object Editor displays the following information.

## Node {.tabset}

### Information

#### Information
![Information](/instamat_studio/canvas/goe_top_node.png =400x){.align-right} This section displays the common node information.

The following node attributes are listed:

- Name
- Category
- Description
- Author
- Version Number

<br style="clear:right;"/>

### Element Format

#### Element Format

![Element Format](/instamat_studio/canvas/goe_element_format.png =400x){.align-right} This section determines the node's format and execution size.

- **Format Type**: The method in which the node will be executed. The format can be set to the following options
	- **Normalized8, Normalized16, FullRange16, FullRange32**: This will manually set the format regardless of any parent graph inheritance or connected node inputs.
	- **Inherit**: The format will be inherited from the parent graph.
	- **DeriveFromFirstAvailableImageInput**: The format will be set based on the node connected to the first available 'Image' type graph input.
	- **InheritFormatDeriveSizeFromFirstAvailableImageInput**: The format will be inherited from the parent graph and the size will be set based on the node connected to the first available 'Image' type graph input.
- **Width** and **Height**: The size at which the node will be executed.
- **Absolute Size**: If enabled, the node's size will be determined by a specific resolution instead of a relative size.   

#### Relative and Absolute Execution Size
There are two methods to determine a node's execution size: Relative and Absolute. The method is chosen based on the status of the `Absolute Size` switch.

| Absolute Size Switch | Method |
| --- | --- |
| Enabled | Absolute: The node will be executed at a constant size such as *'1024' x '1024'*. |
| Disabled | Relative: The node will either `Inherit` the size if selected, or be executed at a relative size to the parent graph such as */2* or **4*.
{.dense}

### Instance Properties

#### Instance Properties

![Instance Properties](/instamat_studio/canvas/goe_instance_properties.png =400x){.align-right} This section determines the execution seed, if a node is active or disabled, and toggles the node's grayscale/color permutation resulting in the node outputting grayscale or color data.

- **Seed**: The execution seed for the node. All parameters and internal nodes that supply variation derive their random attributes from this seed. For example: If the selected node is a material, changing the seed will result in a new variation of that material. If the node is a noise, changing the seed will result in a variation of that noise.
- **Active**: Sets whether the node is "Active" or "Disabled". Disabled nodes display a <i class="fa-regular fa-snooze"></i> icon in the top left corner next to their name in the Canvas view. Nodes that have a `Background` or `Image` input will pass that information through to the output. 

> A shortcut for disabling nodes is highlighting the node and pressing <kbd>H</kbd>. You can also <kbd>Right click</kbd> the node to bring up the contextual menu and choose `Enable/Disable Node`. To learn more about disabling nodes, check out our <a href="">dedicated video</a> on our YouTube channel.
{.is-info}

- **Grayscale**: Determines the grayscale/color permutation of the node. Enabling will output grayscale information.

> #### Grayscale and Color Information
> Nodes in InstaMAT can choose to output either grayscale or color information. When adding a node with [Quick Search](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Quick_Search), the compatible permutation will automatically be enabled. When connecting a node already in the Canvas with the opposing permutation enabled, a converter node will be inserted between the two nodes.
>
> For example: spawning a node that outputs grayscale information from a color image input pin will result in a converter node inserting between the two.
>
> ![GIF of both scenarios: QS and Converter](/instamat_studio/canvas/canvas_permutations.gif){.align-center}
{.is-info}

### Inputs

#### Inputs

![Instance Properties](/instamat_studio/canvas/goe_inputs_node.png =400x){.align-right} This section displays a node's **Graph Inputs** also known as the node's Input Parameters. Inputs have many different data types and an assortment of widgets to control them. Specific parameter values can be typed in with the keyboard either by <kbd>Double Clicking</kbd> on each parameter or using the <i class="fa-regular fa-pencil"></i> icon.

<br style="clear: right" />

#### Image and Color Input Widgets
![image_input.gif](/instamat_studio/canvas/image_input.gif =300x){.align-right} Image inputs in InstaMAT can provide both an image or a solid color. Clicking the <i class="fa-regular fa-pencil"></i> icon brings up the [Resource Picker](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Resource_Picker) panel to input an image. If an image is already utilized, clicking the <i class="fa-regular fa-xmark"></i> will clear out the image and allow for a solid color to be chosen.
<br style="clear: right;"/>

![color_picker.png](/instamat_studio/canvas/color_picker.png =300x){.align-right} A dedicated color picker panel can be invoked by clicking on the square that represents the chosen color. Additionaly, the color picker can be invoked by <kbd>Right Clicking</kbd> on the widget. This color panel provides 

<br style="clear: right;"/>

#### Overriding Input Parameters

If the UI widget such as a slider does not reach the minimum or maximum value you require, the parameter can be overridden. There are two ways to override the value range of a parameter:

1. <kbd>Right Click</kbd> it to bring up the contextual menu, then choose `Override Slider Range`. A dialog will appear whith fields to input the new minimum and maximum values.
2. Type in a value that is above or below the range. A popup will appear by default notifying that the value excedes the bounds of the range.

![Override Choice Dialog](/instamat_studio/canvas/override_choice_dialog.png =700x){.align-center}

#### Formulas in Fields
Mathematical formulas can be entered into input fields to perform quick calculations. To enter a formula, begin by typing `=` followed by the mathetmatical expression. For example: `=5*3`

This will input the result of `15` into the input field. Additionally, equasions like `sin(1.6)` are also possible.

![formulas_in_fields.gif](/instamat_studio/canvas/formulas_in_fields.gif =600x){.align-center}


#### Contextual Menu
![Instance Properties](/instamat_studio/canvas/goe_input_context1.png =250x){.align-right} <kbd>Right Clicking</kbd> on a Graph Input brings up a contextual menu. The listed items will vary depending on the type of input clicked. The menu contains the following possible options:

- **Load Image from Local File**: If the Graph Input is an ElementImage or ElementImageGray type, a local file from the user's machine can quickly be imported and assigned.
- **Reset to Default Value**: Resets the Graph Input to the default value.
- **Expose as Input Parameter**: Exposes the parameter as a Graph Input for the parent graph.
- **Override**: Overrides the default minimum and maximum values for the parameter.

>To learn more about how to use InstaMAT's powerful set of widgets, please read our dedicated article: <a href="">A Guide to InstaMAT's Widgets</a>.
>
> ![Widgets](/instamat_studio/canvas/widgets.png =700x){.align-center}
{.is-info}


### Outputs

#### Outputs

![GOE Node Outputs](/instamat_studio/canvas/goe_node_outputs.png =400x){.align-right} This section displays a node's **Graph Outputs** and the category assigned to each output.
<br style="clear:right"/>

#### Contextual Menu

![GOE Node Outputs Context Menu](/instamat_studio/canvas/goe_outputs_context.png =300x){.align-right} <kbd>Right Clicking</kbd> on a Graph Output brings up a contextual menu with the following options:

- **View Image**: If the Graph Output is an ElementImage or ElementImageGray type, the image is loaded into the [Image Viewer](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Image_Viewer).
- **View Image in New Tab**: If the Graph Output is an ElementImage or ElementImageGray type, the image is loaded into the [Image Viewer](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Image_Viewer) in a new tab.
- **Expose as Output Parameter**: Exposes the node's output as a Graph Output for the parent graph. Learn more about Graph Outputs below.

## Graph
When a graph is selected, the Graph Object Editor displays the following information. To view information on a graph <kbd>Left Click</kbd> on an empty space in the Canvas.

## Graph {.tabset}

### Information

#### Information

![GOE Node Information](/instamat_studio/canvas/goe_top_graph.png =400x){.align-right} This section displays common graph information.

The following graph attributes are listed:
- Name
- Category
- Description

Use the <i class="fa-regular fa-pencil"></i> icon to set the graph's name or <kbd>Double Click</kbd> on any of the information to begin editing. Adjusting the category of the graph will determine where it appears in the [Graph Library](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Graph_Library).

### Inputs

#### Inputs

![GOE Inputs with Graph Selected](/instamat_studio/canvas/goe_inputs_graph.png =400x){.align-right} This section manages the creation and manipulation of a graph's Graph Inputs also known as Input Parameters or Exposed Parameters. These inputs are public and can be adjusted from within InstaMAT Studio, <a href="">InstaMAT Pipeline</a>, and through our <a href="">Integrated Plugins</a>.

To create a new Input Parameter:

1. Click the <i class="fa-regular fa-octagon-plus"></i> button in the top right corner of this section
2. Choose the data type for the new input
3. <kbd>Double Click</kbd> the name of the parameter to rename it

The parameter's value set in this section will be its default value when the graph is instantiated. Parameters can be re-arranged by **dragging and dropping** them into the desired order. To customize them further, use the [Graph Variable Editor](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Graph_Variable_Editor) to do things like organizing them into categories, setting the minimum and maximum ranges, changing the graphical UI widget best used to manipulate the data, and more.
<br style="clear: right;"/>
To work with a parameter in the Canvas, <kbd>drag and drop</kbd> it directly into the Canvas view where it will become a node. It can then either be connected to a matching input type, or converted using one of the many conversion nodes built into InstaMAT Studio's node library. Conversion nodes can easily be created using [Quick Search](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Quick_Search).

![GIF of dragging an input into the Canvas, then using Quick Search to convert to another type.](/instamat_studio/canvas/param_convert.gif){.align-center}

> To learn more about how to create and manipulate Graph Inputs, please read our article: <a href="">Node-Based Workflow Key Concepts</a>.
{.is-info}

#### Contextual Menu

![GOE Input Contextual Menu with Graph Selected](/instamat_studio/canvas/goe_input_context3.png =250x){.align-right} <kbd>Right Clicking</kbd> on a Graph Input brings up a contextual menu with the following options:

- **Show in Variable Editor**: Shows the currently selected Graph Inputs in the [Graph Variable Editor](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Graph_Variable_Editor). Multiple inputs can be selected to assign the same information.
- **Load Image from Local File**: If the Graph Input is an ElementImage or ElementImageGray type, a local file from the user's machine can quickly be imported and assigned.
- **Demote to Local Variable**: Demotes the selected public Graph Input to a private Local Variable. Learn more about Local Variables below.
- **Change Variable Type to**: Quickly changes the Graph Input's data type.
- **Change UI Control Type to**: Quickly changes the Graph Input's UI control widget.
- **Search for**: Automatically populates the name of the Graph Input into the Canvas's search bar and searches for any instances of it in the graph.
- **Add Keyframe to Dope Sheet**: Creates a keyframe in the <a href="">Dope Sheet</a> at the playhead's current frame index.


### Outputs

#### Outputs

![GOE Outputs with Graph Selected](/instamat_studio/canvas/goe_outputs_graph.png =400x){.align-right} This section manages a graph's Graph Outputs. When building a procedural PBR material with the <a href="">Element Graph</a>, these outputs are the maps that generate a material's fundamental channels such as *Base Color*, *Normal*, and *Roughness.*

To create a new Graph Output:

1. Click the <i class="fa-regular fa-octagon-plus"></i> button in the top right corner of this section
2. Choose the type for the new output
3. <kbd>Double Click</kbd> the name of the output to rename it

> When giving an ElementImage or ElementImageGray Graph Output a common PBR Material map name such as "Base Color", "Roughness", or "Ambient Occlusion", InstaMAT will automatically connect these outputs to their proper channel for viewing in the [Viewport](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Viewport).{.is-info}

Outputs that export Image, Mesh, or Point Cloud data will be utilized in the <a href="">Output Export Dialog</a>.

>#### A Note about Categories and Link Category Mode
> Graph Inputs and Outputs can be assigned a **Category** in the [Graph Variable Editor](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Graph_Variable_Editor). If multiple Graph Inputs and Outputs share the same category, they can be combined and connected together with <a href="">Link Category Mode</a>. This mode visually combines connections that share the same category making it easy to connect multiple pieces of information together. Once combined, a single connection can be dragged from the outputs of one node to the inputs of a corresponding node that shares the same category.
>
> ![GIF of using LC mode](/instamat_studio/canvas/lc_mode.gif){.align-center}
{.is-info}


#### Contextual Menu
![GOE Output Context Menu when Graph Selected](/instamat_studio/canvas/goe_output_graph_context.png =250x){.align-right} <kbd>Right Clicking</kbd> on a Graph Output brings up a contextual menu with the following options:

- **View Image**: If the Graph Output is an *ElementImage* or *ElementImageGray* type, the image is loaded into the [Image Viewer](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Image_Viewer).
- **View Image in New Tab**: If the Graph Output is an *ElementImage* or *ElementImageGray* type, the image is loaded into the [Image Viewer](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Image_Viewer) in a new tab.
- **Show in Variable Editor**: Shows the currently selected Graph Outputs in the [Graph Variable Editor](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Graph_Variable_Editor). Multiple outputs can be selected to assign the same information.
- **Change Variable Type to**: Quickly changes the Graph Output's data type.
- **Change UI Control Type to**: Quickly changes the Graph Output's UI control widget.
- **Search for**: Automatically populates the name of the Graph Output into the Canvas's search bar and searches for any instances of it in the graph.
- **Add Keyframe to Dope Sheet**: Creates a keyframe in the <a href="">Dope Sheet</a> at the playhead's current frame index.


### Local Variables

#### Local Variables

![GOE Local Variables](/instamat_studio/canvas/goe_local_variables.png =400x){.align-right} This section displays a graph's **Local Variables**. Local Variables are private and can only be accessed within the graph itself. These variables are useful when multiple parts of a graph need to privately share the same source of information. 
<br style="clear:right;"/>
> #### Did You Know?
> Multiple instances of the same variable can be dragged into a graph regardless if it's a public Graph Input or private Local Variable. Each instance will update if the variable's value changes.
{.is-info}

#### Contextual Menu

![GOE Local Variables Context Menu when Graph Selected](/instamat_studio/canvas/goe_local_variables_context1.png =300x){.align-right} <kbd>Right Clicking</kbd> on a Local Variable brings up a contextual menu with the following options:

- **Show in Variable Editor**: Shows the currently selected Local Variable in the [Graph Variable Editor](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Graph_Variable_Editor). Multiple inputs can be selected to assign the same information.
- **Load Image from Local File**: If the Local Variable is an *ElementImage* or *ElementImageGray* type, a local file from the user's machine can quickly be imported and assigned.
- **Promote to Input Parameter**: Promotes the selected private Local Variable to a public Graph Input.
- **Change Variable Type to**: Quickly changes the Local Variable's data type.
- **Change UI Control Type to**: Quickly changes the Local Variable's UI control widget.
- **Search for**: Automatically populates the name of the Local Variable into the Canvas's search bar and searches for any instances of it in the graph.
- **Add Keyframe to Dope Sheet**: Creates a keyframe in the <a href="">Dope Sheet</a> at the playhead's current frame index.

### Versioning

#### Versioning

![Versioning]()

> Information coming soon.
{.is-warning}

### Meta Data

#### Meta Data

![GOE Meta Data Section with Graph Selected](/instamat_studio/canvas/goe_meta_data.png =400x){.align-right} This section allows the user to input attributes for the graph that are used across various parts of InstaMAT.

- **Author**: Sets the author of the graph.
- **Tags**: Assigns various tags to the graph. These tags are searchable throughout InstaMAT Studio.
- **Version**: Sets the graph's version number.
- **Use Physical Size**: When enabled, the entered physical size in centimeters is assigned to the graph.
- **Private**: When enabled, private graphs are not displayed in the [Graph Library](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Graph_Library). This is useful when building out a project into subgraphs or "helper graphs" that should be concealed from the library.
- **Deprecation**: Sets the message to display when the graph is deprecated. All graphs that instance this graph will display this deprecation message when the graph loaded.
- **Default Image**: Sets the default image for the graph's image parameters.
- **Preview Mesh**: Assigns a mesh used when previewing the graph outputs in 3D.
- **Expose Seed**: When enabled, exposes the graph's seed so the user can configure the randomization from the outside.
- **Layering Compatibility**: Determines if and how the graph can be used with <a href="">Layering</a> projects. Setting the compatibility to `Auto` allows InstaMAT to choose the right compatibility based on the graph's category and parameter configuration.
- **Grayscale Permutable**: When enabled, allows the graph to automatically change between outputting grayscale and color information.

>Grayscale permutable Atoms and Elements can automatically change their color inputs to grayscale inputs. Most of the heavy lifting is done by InstaMAT and most Atoms will just work. However, conditional behavior can be implemented by branching on the "is Grayscale Permutation" value.
{.is-info}