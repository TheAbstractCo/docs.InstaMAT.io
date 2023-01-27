---
title: Image and Data Output Export
description: The Image and Data Output Export window is a comprehensive interface for exporting a project's outputs to disk.
published: true
date: 2023-01-27T17:53:36.623Z
tags: instamat studio
editor: markdown
dateCreated: 2023-01-23T20:20:31.730Z
---

# Image and Data Output Export

![Export Window](/instamat_studio/canvas/output_export_dialog.png)

The **Image and Data Output Export** window is a comprehensive interface for exporting a project's outputs to disk. For images, this includes all maps generated from a PBR material or Layering project. In addition to images, meshes and point clouds from an <a href="">Element Graph</a> can also be exported here. The Export window's template system makes it easy to combine multiple maps into one file through channel packing. This places maps that contain values in the pixels from 0 to 1 into separate Red, Green, Blue, and Alpha channels of an RGBA image. This packed image then contains multiple maps of information and reduces the texturing footprint of the asset. Additionally, many common map conversions can take place during export such as converting an OpenGL Normal map to a DirectX Normal map or switching from a Metallic/Roughness workflow to Specular/Glossy.

## Interface Overview

The UI for the Export window is divided into four parts: Output Settings, Image and Data Outputs, Output Template Configuration, and Export Template.

<img src="/instamat_studio/canvas/export_dialog_numbered.png" alt="Export Dialog Numbered" />

### <i class="fa-regular fa-circle-1"></i> Output Settings

![Image](/instamat_studio/canvas/output_export_output_settings.png =500x){.align-right} This section determines where to export the outputs, the naming convention for each file, the file's format extension, and format settings.


Format extension dropdown menus will appear based on the type of outputs used for the project. An image output's export resolution and format is determined separately from the project's current execution settings found in the main toolbar of InstaMAT Studio's UI. This means that the export resolution can be different from the working resolution.
<br style="clear: right;"/>

- **Output Path**: Determines the folder location to export the outputs
- **File Name Format**: Provides a format using variables for the file name of each baking result. Tokens can be selected using the <i class="fa-regular fa-bars"></i> button located to the right of the input field.
- **Image/Mesh/Point Cloud Format Extension**: Determines the format extension for the exported file of that type
- **Format Preview**: Provides a preview of the naming convention used in the `File Name Format` setting
- **Format Settings**: Sets the export resolution and format of an image output. This setting is separate from the "working" resolution and format found in InstaMAT Studio's main toolbar.

### <i class="fa-regular fa-circle-2"></i> Image and Data Outputs

![Image](/instamat_studio/canvas/output_export_image_and_data_outputs.png =500x){.align-right} This section sets which outputs are exported. Outputs with their toggle enabled "inner circle to the right" will be exported. If an export template is chosen, the `Managed by Output Template` toggle will be enabled and the switches for each output will be toggled based on their usage in the chosen template.
<br style="clear: right;"/>

### <i class="fa-regular fa-circle-3"></i> Output Template Configuration

![Output Template Configuration](/instamat_studio/canvas/output_export_output_template_configuration.png =500x){.align-right} This section provides access to InstaMAT Studio's powerful template configuration system.
<br style="clear: right"/>

![Template Selection](/instamat_studio/canvas/output_export_template_selection.png =500x){.align-right} With the large dropdown at the top, a template can be selected. By default this says "No Template Active". Add or remove a template by clicking the <i class="fa-regular fa-plus"></i> or <i class="fa-regular fa-minus"></i> buttons to the right of the dropdown. To duplicate a template, make sure it is active and click the <i class="fa-regular fa-clone"></i> button.
<br style="clear: right"/>

![Output Template Table](/instamat_studio/canvas/output_export_table.png =500x){.align-right} The Output Template table shows each **Custom Output** in a row. The first column displays the output's name. The second and third columns display how a particular project output is mapped to the channels of the Custom Output image.
<br style="clear: right"/>

![Outputs and Converters](/instamat_studio/canvas/output_export_options.png =500x){.align-right}Options from the `Output Templates` and `Output Converters` lists can be dragged onto a Custom Output's channels to map or pack the information.
<br style="clear: right"/>

> To learn more about creating custom Output Templates, please read the <a href="#creating-output-templates">Creating Output Templates</a> section below.
{.is-info}

### <i class="fa-regular fa-circle-4"></i> Export Template

![Export Template](/instamat_studio/canvas/output_export_export_template.png =500x){.align-right} This section shows the active Output Template used for export. Each output file is listed along with its file type expressed as a dot with a corresponding type color. Use the dropdown menu to quickly select an Output Template.
<br style="clear: right"/>

## Creating Output Templates

**Custom Output Templates** can be created to dynamically export, map, and pack project outputs into a predefined set of output images. The following section illustrates how to create a Custom Output Template.

### 1. Create a New User Template

Click the <i class="fa-regular fa-plus"></i> button to create a new User Template. From the popup dialog, provide the template with a name and, if needed, a description. The template is now selected as the active template and can be found again from the large dropdown menu at the top of the window under the `User Templates` submenu.

![New Template GIF](/instamat_studio/canvas/new_template.gif =600x){.align-center}

> Templates are stored in InstaMAT's home directory. This is typically found here: `~/Documents/InstaMAT/Output Templates`.
{.is-info}

### 2. Configure the Template

Now that the template has been created, **Custom Outputs** can be added and configured using the Output Template table. Click the `Add Custom Output` button and choose from an `RGBA` or `Grayscale` image.

<kbd>Double Click</kbd> the name of the Custom Output in the first column of the table to rename it.

InstaMAT Studio ships with many common Output Template options. These options are populated in the `Output Templates` section below the table. Options can be mapped or packed into specific Custom Output channels by <kbd>dragging and dropping</kbd> them into their respective slots on the table. Project or graph outputs that have matching names to these options will automatically be assigned to their proper Custom Output and channel upon export.

For example, to map a "Roughness" output to the Red channel of a Custom RGBA Output called "RoughMetalAO", <kbd>drag</kbd> the `Roughness` option in the Output Templates area onto the `Red` column of the Custom Output. Additionally the "Metalness" and "AmbientOcclusion" Output Template options can be dragged into the Green and Blue channels to pack the information into one Custom Output image.

![Configuring the template](/instamat_studio/canvas/template_configuration.gif =600x){.align-center}

Clicking `More` at the bottom of the list will reveal additional options. If an output that you need is not listed, a custom option can be created by clicking the <i class="fa-regular fa-plus"></i> at the top of the list. You can then choose whether it is an RGBA or Grayscale option, then InstaMAT Studio will ask for a default color or value to be chosen. This value is used if the Export Output Template is used, but a matching output from the project is not provided. To rename the option, <kbd>double click</kbd> it.

![Custom Output Template Creation](/instamat_studio/canvas/template_custom_output_template.gif =600x){.align-center}