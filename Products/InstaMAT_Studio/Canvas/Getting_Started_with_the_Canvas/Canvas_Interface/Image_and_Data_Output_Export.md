---
title: Image and Data Output Export
description: The Image and Data Output Export window is a comprehensive interface for exporting a project's outputs to disk.
published: true
date: 2023-01-23T20:26:42.801Z
tags: instamat studio
editor: markdown
dateCreated: 2023-01-23T20:20:31.730Z
---

# Image and Data Output Export

![Export Window](/instamat_studio/canvas/output_export_dialog.png)

The **Image and Data Output Export** window is a comprehensive interface for exporting a project's outputs to disk. For images, this includes all maps generated from a PBR material or Layering project. In addition to images, meshes and point clouds from an <a href="">Element Graph</a> can also be exported here. The Export window's template system makes it easy to combine multiple maps into one file through channel packing. This places maps that contain values in the pixels from 0 to 1 into separate Red, Green, Blue, and Alpha channels of an RGBA image. This packed image then contains multiple maps of information and reduces the texturing footprint of the asset. Additionally, many common map conversions can take place during export such as converting an OpenGL Normal map to a DirectX Normal map or switching from a Metallic/Roughness workflow to Specular/Glossy.

## Interface Overview

<img src="/instamat_studio/canvas/export_dialog_numbered.png" alt="Export Dialog Numbered" />

The UI for the Export window is divided into four parts: Output Settings, Image and Data Outputs, Output Template Configuration, and Export Template.

### <img src="/instamat_studio/canvas/1.png" alt="1" width="22"/> Output Settings

<img src="/instamat_studio/canvas/output_export_output_settings.png" alt="Output Settings" width="600"/>

This section determines where to export the outputs, the naming convention for each file, the file's format extension, and format settings. Format extension dropdown menus will appear based on the type of outputs used for the project. An image output's export resolution and format is determined separately from the project's current execution settings found in the main toolbar of InstaMAT Studio's UI. This means that the export resolution can be different from the working resolution.

- **Output Path**: Determines the folder location to export the outputs
- **File Name Format**: Provides a format using variables for the file name of each baking result. Tokens can be selected using the ![Tokens Icon](/instamat_studio/canvas/tokens_icon.png) button located to the right of the input field.
- **Image/Mesh/Point Cloud Format Extension**: Determines the format extension for the exported file of that type
- **Format Preview**: Provides a preview of the naming convention used in the `File Name Format` setting
- **Format Settings**: Sets the export resolution and format of an image output. This setting is separate from the "working" resolution and format found in InstaMAT Studio's main toolbar.

### <img src="/instamat_studio/canvas/2.png" alt="2" width="22"/> Image and Data Outputs

<img src="/instamat_studio/canvas/output_export_image_and_data_outputs.png" alt="Image and Data Outputs" width="600"/>

This section sets which outputs are exported. Outputs with their toggle enabled "inner circle to the right" will be exported. If an export template is chosen, the `Managed by Output Template` toggle will be enabled and the switches for each output will be toggled based on their usage in the chosen template.

### <img src="/instamat_studio/canvas/3.png" alt="3" width="22"/> Output Template Configuration

<img src="/instamat_studio/canvas/output_export_output_template_configuration.png" alt="Output Template Configuration" width="600"/>

This section provides access to InstaMAT Studio's powerful template configuration system. With the large dropdown at the top, a template can be selected. By default this says "No Template Active".

<img src="/instamat_studio/canvas/output_export_template_selection.png" alt="Template Selection" width="600"/>

Add or remove a template by clicking the ![+](/instamat_studio/canvas/add_template_icon.png) or ![-](/instamat_studio/canvas/remove_template_icon.png) buttons to the right of the dropdown. To duplicate a template, make sure it is active and click the ![Duplicate](/instamat_studio/canvas/duplicate_template_icon.png) button.

<img src="/instamat_studio/canvas/output_export_table.png" alt="Output Template Table" width="600"/>

The Output Template table shows each **Custom Output** in a row. The first column displays the output's name. The second and third columns display how a particular project output is mapped to the channels of the Custom Output image.

<img src="Images/Output_Export_Options.png" alt="Outputs and Converters" width="600"/>

Options from the **'Output Templates'** and **'Output Converters'** lists can be dragged onto a Custom Output's channels to map or pack the information.

> To learn more about creating custom Output Templates, please read the <a href="#creating-output-templates">Creating Output Templates</a> section below.

### <img src="Images/4.png" alt="4" width="22"/> Export Template

<img src="Images/Output_Export_Export_Template.png" alt="Export Template" width="600"/>

This section shows the active Output Template used for export. Each output file is listed along with its file type expressed as a dot with a corresponding type color. Use the dropdown menu to quickly select an Output Template.

## Creating Output Templates

**Custom Output Templates** can be created to dynamically export, map, and pack project outputs into a predefined set of output images. The following section illustrates how to create a Custom Output Template.

### 1. Create a New User Template

<img src="Images/New_Template.gif" alt="New Template GIF" />

Click the ![+](Images/Add_Template_Icon.png) button to create a new User Template. From the popup dialog, provide the template with a name and, if needed, a description. The template is now selected as the active template and can be found again from the large dropdown menu at the top of the window under the **'User Templates'** submenu.

> Templates are stored in InstaMAT's home directory. This is typically found here: `~/Documents/InstaMAT/Output Templates`.

### 2. Configure the Template

<img src="Images/Template_Configuration.gif" alt="Configuring the template" width="600"/>

Now that the template has been created, **Custom Outputs** can be added and configured using the Output Template table. Click the **'Add Custom Output'** button and choose from an **'RGBA'** or **'Grayscale'** image.

**Double Click** the name of the Custom Output in the first column of the table to rename it.

InstaMAT Studio ships with many common Output Template options. These options are populated in the **Output Templates** section below the table. Options can be mapped or packed into specific Custom Output channels by **dragging and dropping** them into their respective slots on the table. Project or graph outputs that have matching names to these options will automatically be assigned to their proper Custom Output and channel upon export.

For example, to map a "Roughness" output to the Red channel of a Custom RGBA Output called "RoughMetalAO", **drag** the **'Roughness'** option in the Output Templates area onto the **'Red'** column of the Custom Output. Additionally the "Metalness" and "AmbientOcclusion" Output Template options can be dragged into the Green and Blue channels to pack the information into one Custom Output image.

Clicking **'More'** at the bottom of the list will reveal additional options. If an output that you need is not listed, a custom option can be created by clicking the ![+](Images/Add_Template_Icon.png) at the top of the list. You can then choose whether it is an RGBA or Grayscale option, then InstaMAT Studio will ask for a default color or value to be chosen. This value is used if the Export Output Template is used, but a matching output from the project is not provided. To rename the option, **double click** it.

<img src="Images/Template_Custom_Output_Template.gif" alt="Custom Output Template Creation" width="600"/>