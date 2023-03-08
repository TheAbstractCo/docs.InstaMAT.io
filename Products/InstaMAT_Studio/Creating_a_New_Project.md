---
title: Creating a New Project
description: New projects can be created inside an InstaMAT Package with the New Project screen.
published: true
date: 2023-03-08T16:23:19.824Z
tags: instamat studio
editor: markdown
dateCreated: 2023-03-06T17:17:25.714Z
---

New projects can be created inside an InstaMAT `Package` with the `New Project` screen. Hover over each project to get a preview and extended description. Click a project to create it.

![new_project_screen.gif](/instamat_studio/general/new_project_screen.gif){.align-center}

The New Project screen can be found in a few locations:

- From the `Welcome Screen`, click `Create a new InstaMAT project`
- Go to `File` > `New Project` in the main menu
- Click the <i class="fa-regular fa-octagon-plus"></i> (New Project) button in the main toolbar

## Project Types

The following project types can be created in InstaMAT Studio:

- **Layering:** Create stunning textuers for your assets with a delightfully intutive and creative workflow using a familiar layer-based approach.
- **Material Layering:** Experience a new way to create fully procedural 3D materials. Simply drag and drop your existing materials onto the material layer stack and experience a transformative workflow for creating procedural materials.
- **Materialize Image:** Convert any image into a complete PBR material with output channels for BaseColor, Normal, Roughness, Metalness, AmbientOcclusion, and Height.
- **Element Graph:** The ultimate swiss-army knife for any 3D asset production pipeline. Design stunning and fully procedural materials with InstaMAT's vast library of noise functions, pattern generators and utility nodes. From procedural mesh processing nodes to string handling and arithmetic operations - it's there, waiting for your spark of creativity.
- **nPass Element Graph:** Build advanced processing nodes that perform multiple passes when executed, with the ability to carry data from one pass to the next.
- **Atom Graph:** Create custom image processing nodes that can be instanced in any ElementGraph.
- **Function Graph:** Develop small functions that can be easily reused in your Atom Graphs.

## Package Hirearchy

`Projects` are created and stored inside InstaMAT `Packages`. In addition to multiple projects, packages contain related resources that are to be bundeled with each project such as images, fonts, baked mesh maps, baking settings, meshes, and point clouds. Multiple projects can share the same resources in a package.

Package contents are viewed through the [Package Management](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Package_Management) panel.