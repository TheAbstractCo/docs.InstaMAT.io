---
title: Mesh Baking
description: The Mesh Baking Panel provides access to InstaMAT's powerful and sophisticated texture bakers. These bakers can be used to generate texture maps by extracting information from incoming mesh geometry.
published: true
date: 2023-01-27T18:37:27.888Z
tags: instamat studio
editor: markdown
dateCreated: 2023-01-23T19:56:47.226Z
---

# Mesh Baking

![Mesh Baking Panel](/instamat_studio/canvas/mesh_baking_panel.png){.align-center}

The **Mesh Baking** Panel provides access to InstaMAT's powerful and sophisticated texture bakers. These bakers can be used to generate texture maps by extracting information from incoming mesh geometry. Specialized maps such as Ambient Occlusion, Position, Curvature, and Thickness can provide useful information on the physical characteristics of the mesh allowing for bespoke texturing and effects. 

Mesh Baking is an integral part of the texturing process and is built into many parts of InstaMAT. There is even a <a href="">Mesh Bake</a> node that can be instanced in the <a href="">Canvas</a> unlocking <a href="">scalable texturing workflows</a> where a mesh is imported, texture maps are baked, and materials are applied with one <a href="">Element Graph</a>.

These incredibly optimized bakers are built with the same industry-proven technology from <a href="https://InstaLOD.com">InstaLOD</a> meaning that they are fully scalable in terms of both output texture dimensions and polygon counts. Meshes can be targeted by name and custom baking cages can have different topology from the target mesh. With **Super Sampling**, texture maps can be baked at 2-16x their resolution and then sampled down to retain their quality with a lighter footprint. Depending on your workstation, both CPU and GPU bakers are available.

> InstaMAT also includes powerful automatic UV unwrapping features making it possible to construct an entire mesh creation and processing pipeline from start to finish. To learn more, please read our dedicated article: <a href="">Automatic UV Unwrapping</a>.
{.is-info}

## Accessing the Mesh Baking Panel

There are a few ways to access the Mesh Baking Panel:

- Click the <i class="fa-regular fa-oven"></i> icon in the <a href="">Canvas Toolbar</a>
- Go to **Window > Mesh Baking** in the main menu
- In a <a href="">Layering</a> project, open the `Material Sections` dropdown in the <a href="">Layering Project Editor</a> panel and click the hamburger menu <i class="fa-regular fa-bars"></i> button. From the popup menu, choose `Bake Mesh Data`.

## Interface Overview
The following section overviews the interface for the Mesh Baking panel.

The Mesh Baking Panel is divided into two parts. The left contains the **Baking Settings**. The right is where **Bakers** can be toggled on and off. Some bakers have additional options that can be configured if needed. Hovering over a setting provides additional helpful information at the bottom of the panel in its status bar.

![Mesh Baking Panel UI](/instamat_studio/canvas/mesh_baking_ui.png){.align-center}

### Baking Settings

This section sets up all of the necessary information to perform the baking operation.

![Baking Settings](/instamat_studio/canvas/baking_settings.png =600x){.align-center}

#### Mesh Baking

These are the main baking operation settings. They determine the input meshes, baking engine, image output resolution, and other output settings for the resulting images.

- **Target Mesh**: Sets the target mesh. Typically this is the "low-poly" counterpart in a "High to Low Poly" baking workflow. Details from the `Source Mesh` will be baked onto this mesh.
- **Source Mesh**: Sets the source mesh. Typically this is the "high-poly" counterpart in a "High to Low Poly" baking workflow. Details from this mesh will be baked onto the `Target Mesh`.
- **Baking Engine**: Determines whether to use the CPU or GPU baking engine
- **Resolution**: Sets the resolution of the baked image
- **Super Sampling**: When enabled, multiplies the `Resolution` by the chosen amount. The result is then sampled down to the original resolution.

> The "Super Sampled" result retains a majority of the quality from the higher resolution bake providing a higher quality output with a smaller footprint. Note that increasing the `Super Sampling` amount will also exponentially increase memory usage and processing time.
{.is-info}

- **Store Result in Package**: Stores the baking results in the currently active package. If disabled, an output path can be provided.
- **File Name Format**: Provides a format using variables for the file name of each baking result. Tokens can be selected using the <i class="fa-regular fa-bars"></i> button located to the right of the input field.
- **Image File Format Extension**: Determines the image output format for the baking results
- **Format Preview**: Provides a preview of the naming convention used in the `File Name Format` setting

#### Advanced Settings

These settings provide access to more advanced baking operations. They determine how meshes are targeted, provide options to dial in the outward and inward ray lengths, and supply further baking functionality.

- **Targeting Mode**: Determines how meshes are targeted during the bake. The options are `All Source Meshes` and `By Mesh Name`.
- **Target Mesh Suffix**: Sets the mesh name suffix used to determine if a mesh is a target
- **Source Mesh Suffix**: Sets the mesh name suffix used to determine if a mesh is a source

> Setting the `Targeting Mode` to `By Mesh Name` will selectively bake matching submeshes from the `Source Mesh` onto the `Target Mesh`. Matches are made based on the `Source Mesh Suffix` and `Target Mesh Suffix`. This prevents baking artifacts by isolating each source/target component.
>
> For example, with a `Source Mesh Suffix` set to "_high" and a `Target Mesh Suffix` set to "_low", a source mesh mesh named "Round_Part_high" will bake onto a target mesh named "Round_Part_low".
{.is-info}

- **Outwards Ray Length in %**: Sets the outward ray length by a percentage based on the bounding sphere of the **'Source Mesh'**
- **Inwards Ray Length in %**: Sets the inward ray length by a percentage based on the bounding sphere of the **'Source Mesh'**
- **Ignore Backfaces**: When enabled, backfaces will not occlude geometry
- **Average Normals**: Uses averaged face normals of the `Target Mesh` as ray directions. This only applies when not using cage mesh normals as ray directions.
- **Dilation in Pixels**: Sets the dilation size in pixels to avoid mip map pixel bleed

#### Cage Mesh

These settings apply to any cage meshes in the baking process. With InstaMAT, cage meshes do not need to have the same topology as the `Target Mesh`.

- **Cage Mesh Suffix**: Sets the mesh name suffix used to determine if a mesh is utilized as a cage mesh
- **Use Cage Mesh Normals**: When enabled, uses the cage mesh normals when computing ray directions instead of the `Target Mesh` normals


### Bakers

To enable a baker, toggle its switch on the right. The baker will move to its Active or Inactive position in the panel. To access a baker's options, use the <i class="fa-regular fa-greater-than"></i> to the left of the baker's name.

![Bakers](/instamat_studio/canvas/bakers.png =400x){.align-center}

The following bakers have additional options:

#### Ambient Occlusion, Bent Normals, Reflectance

These bakers share their settings.

- **Ray Length in %**: Sets the ray length by a percentage based on the bounding sphere of the mesh
- **Intensity**: Sets the scale factor for the Ambient Occlusion value
- **Surface Offset in %**: Sets the surface offset by a percentage based on the bounding sphere of the mesh
- **Cone Angle**: Sets the minimum angle for the sampling cone. Set to 0 for a 180º rotation or to 1 for a 0º rotation.
- **Attenuate By Distance**: Enable to attenuate Ambient Occlusion values by distance
- **Random Deviation**: Randomizes the deviation for each sample. This results in the common noisy appearance seen in baked Ambient Occlusion maps.
- **Submesh Filtering**: Filters the rays based on the submesh filtering settings
- **Fall-Off Square**: Sets the fall-off to square which results in a smoother map
- **Sample Count**: Sets the amount of sub rays to cast for each pixel.

> Increasing the Sample Count increases both the quality of the output texture and the processing time.
{.is-info}

- **AO Blur Kernel**: If enabled by having a value greater than 0, sets the size of the Ambient Occlusion blur kernel

> The Bent Normals baker output will not be blurred.
{.is-warning}

- **Sampling Type**: Determines the sampling type used when generating ray directions.

#### Curvature

- **Strength**: Sets the visibility of the details on the Curvature map

#### Mesh ID

- **By Individual Source Mesh**: When enabled, calculates the Mesh ID map based on the individual source meshes

#### Position

- **Normalize Position by AABB**: Normalizes the Position map output by the Axis-Aligned Bounding Box. If disabled, the Position map is normalized using the mesh's bounding sphere.

#### Thickness

- **Ray Length in %**: Sets the ray length by a percentage based on the bounding sphere of the mesh
- **Surface Offset in %**: Sets the surface offset by a percentage based on the bounding sphere of the mesh
- **Cone Angle**: Sets the minimum angle for the sampling cone. Set to 0 for a 180º rotation or to 1 for a 0º rotation.
- **Normalize**: Normalizes the minimum and maximum thickness values
- **Random Deviation**: Randomizes the deviation for each sample. This results in the common noisy appearance seen in baked Thickness maps.
- **Submesh Filtering**: Filters the rays based on the submesh filtering settings
- **Sample Count**: Sets the amount of sub rays to cast for each pixel.

> Increasing the Sample Count increases both the quality of the output texture and the processing time.
{.is-info}

- **Blur Kernel**: If enabled by having a value greater than 0, sets the size of the Thickness blur kernel
- **Sampling Type**: Determines the sampling type used when generating ray directions.

#### Displacement

- **Full Range**: Outputs a full range Displacement map. This means that the lowest point in the Displacement map is set to 0 and the highest is set to 1 in the output image.

#### Normal Tangent Space

- **Binormal Per Fragment**: This setting depends on how your renderer/engine computes the tangent basis. Unreal Engine: On, Unity: Off.
- **Normalize Per Fragment**: This setting depends on how your renderer/engine computes the tangent basis. Unreal Engine: Off, Unity: Off.
- **Output Tangent Space**: Sets the output type of the automatically-computed tangent space. Can either be `OpenGL` or `DirectX`.


## Baking Process Overview

The following is how to bake mesh maps using the Mesh Baking Panel in InstaMAT Studio:

1. Select a `Source Mesh` and a `Target Mesh` by clicking the ![Folder Icon](/instamat_studio/canvas/folder_icon.png) icon. From the popup menu, choose `Pick Package Resource` to select a mesh from within the currently active package. Choose `Pick Local File` to select a mesh with your system's folder structure.
2. Choose the output `Resolution` for the baked images.
3. Choose a `Super Sampling` value if desired. This will multiply the output `Resolution` by the chosen factor, then sample the image down to the original result.
4. Enable each baker with its dedicated switch on the right. Bakers will move to their Active and Inactive positions on the panel.
5. Press the `Bake` button.

> ### Baking from a Single Mesh
> Baking does not require both a **Source Mesh** and a **Target Mesh**. To generate Mesh Bake Data for a single mesh, input it as the `Target Mesh`. This is useful when the need to transfer high-poly information onto a low-poly representation is not required, and instead the bakers are used specifically to extract information and generate maps to facilitate bespoke texturing effects for the specific mesh.
{.is-info}

## Baking by Mesh Name

InstaMAT's bakers can selectively target sets of meshes based on the suffixes of each individual submesh name. Baking by mesh name avoids baking incorrect source geometry and prevents baking artifacts. This removes the need to "explode" meshes when baking.

The following illustrates how to bake by mesh name in a typical "High to Low Poly Workflow" using InstaMAT's Mesh Baking Panel:

### 1. Prepare the Meshes

![Submesh hierarchy for source and target meshes](/instamat_studio/canvas/hierarchies.png)

The **Source Mesh** that contains the high-poly information will require every submesh in the scene to have an identifiable mesh name suffix also known as the `Source Mesh Suffix`. By default this suffix is "_high". For example, "Metal_Attachment_high" or "Cabinet_Door_high".

The **Target Mesh** that contains the low-poly information will require each submesh to have a matching low-poly counterpart from the **Source Mesh** and should be in the exact same position as the high-poly variant. These low-poly counterparts should have the same name as their high-poly counterparts with the exception of a `Target Mesh Suffix` at the end. By default this suffix is "_low". For example, "Metal_Attachment_low" or "Cabinet_Door_low".

These suffixes can be set under the `Advanced Settings` section in the Mesh Baking Panel.

### 2. Set Up the Bake

Meshes can be dragged into the <a href="">Package Management</a> Panel and imported into the project first. This will copy the mesh into the active package. Alternatively, meshes can be selected as local files and do not need to be imported into the project.

Input the `Source Mesh` and `Target Mesh` into their respective fields by clicking on the ![Folder Icon](/instamat_studio/canvas/folder_icon.png). From the popup menu, choose `Pick Package Resource` to select a mesh from within the currently active package or choose `Pick Local File` to select a mesh with your system's folder structure.

![Picking Source and Target meshes to bake](/instamat_studio/canvas/mesh_baking_pick_meshes.gif)

Be sure to change the `Targeting Mode` to `By Mesh Name`.

![Setting the 'Targeting Mode' to 'By Mesh Name'](/instamat_studio/canvas/mesh_baking_targetting_mode.gif)

Make sure that the `Target Mesh Suffix` and `Source Mesh Suffix` match the hierarchy of your respective meshes.

### 3. Bake

![Bake Button](/instamat_studio/canvas/bake_button.png)

The rest of the baking process is the same as the above <a href="#baking-process-overview">Baking Process Overview</a>. After your selected bakers are enabled and the rest of the baking settings are dialed in, click the `Bake` button to begin the bake. If `Store Result in Package` in the `Mesh Baking` section is enabled, the baked mesh maps will appear in the <a href="">Package Management</a> Panel. When baking from a <a href="">Layering</a> project, baked mesh maps for the asset will automatically populate the proper channels in the `Material Sections` area in the <a href="">Layering Project Editor</a>.