---
title: Package Management
description: The Package Management Panel contains all of the resources within the active package file. This includes projects, images, meshes, point clouds, baked mesh data, and baking settings.
published: true
date: 2023-01-23T16:10:28.956Z
tags: instamat studio, canvas
editor: markdown
dateCreated: 2023-01-23T16:10:28.956Z
---

# Package Management

<img src="Images/Package_Management.png" width="300"/>

The **Package Management** Panel contains all of the resources within the active package file. This includes projects, images, meshes, point clouds, baked mesh data, and baking settings. At the bottom of the panel is the **Package Meta Data** section containing the meta data for the active package.

## Interface Overview

### Package Navigator

<img src="Images/PM_Top.png" width="300"/>

At the top of the Package Management Panel is the name of the package. The package can be renamed by clicking the ![Pencil Icon](Images/Pencil_Icon.png) icon.

Below the package name is a dedicated search field used to filter through the package's contents including its resources by name.

The ![Open Resource](Images/Open_Resource_Icon.png) (Open Resource) icon allows the user to quickly add a resource to the package. More can be read about importing resources <a href="#importing-resources">below</a>.

Projects are listed alphabetically in the main body of the Package Management Panel. All other resources such as images, meshes, and baking settings are organized under an **'Assets'** category.

### Asset Tooltips
![Asset tooltip](Images/Asset_Tooltip.png)

Hovering over an asset will bring up a tooltip containing various information and meta data for the project or resource. The tooltip includes the asset's:

- Name
- Category
- Description
- Author
- Version
- Package Name
- Package Path
- Package Size
- Large Preview Icon

> #### Large Preview Icons
>The **Large Preview Icon** is generated by InstaMAT and will adapt based on the asset or project's outputs. For example: PBR Materials are rendered on a material sphere, and projects that export geometry will show the output mesh with any textures applied.
>
>To regenerate the project's preview:
>
>1. **Right click** the asset to bring up the contextual menu
>2. Choose **'Regenerate Preview'**

### Meta Data

<img src="Images/PM_Bottom.png" width="400"/>

When a project or resource is selected, the bottom of the Package Management Panel displays its meta data.

Below this is the **Package Meta Data** section. Here, the following can be set:

- Package Author
- Package Application
- Package URL
- Hide Resources

If the **'Hide Resources'** toggle is enabled, packages will not show their resources when part of the <a href="Graph_Library.html">Graph Library</a>.

## Importing Resources

Resources can be imported into a package in two ways:

- Assets such as images, meshes, or point clouds can be dragged directly into the Package Management Panel and will automatically be categorized by their type.
- Clicking the ![Open Resource Icon](Images/Open_Resource_Icon.png) (Open Resource) icon at the top of the Package Management Panel brings up a panel to quickly import a file.