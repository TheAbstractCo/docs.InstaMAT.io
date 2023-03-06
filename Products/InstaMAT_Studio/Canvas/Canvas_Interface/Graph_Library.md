---
title: Graph Library
description: The Graph Library panel provides access to the vast node library built into InstaMAT Studio.
published: true
date: 2023-03-06T08:20:22.764Z
tags: instamat studio
editor: markdown
dateCreated: 2023-01-20T18:58:18.667Z
---

![Graph Library Panel](/instamat_studio/canvas/graph_library.png =300x){.align-center}

The **Graph Library** panel provides access to the vast node library built into InstaMAT Studio. Each set of nodes and resources is broken down into categories and can be searched with the dedicated search field at the top of the panel.

To use a resource from the Graph Library, drag it from the library panel into your project.

>In addition to the Graph Library, a faster way to use a node from InstaMAT's library is by using **Quick Search** — A context sensitive search box with extensive functionality built right into the Canvas. To learn more, read our article on Quick Search [here](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Quick_Search).
{.is-info}

## Interface Overview

### Category Browser

![gl_top_small.png](/instamat_studio/canvas/gl_top.png =300x){.align-right} The top area of the Graph Library is the **Category Browser** and contains all of the categories and resources available in the library. Use the dedicated search field at the top to filter through the available resources.

<br style="clear: right;" />

### Content Browser

![gl_bottom_small.png](/instamat_studio/canvas/gl_bottom.png =300x){.align-right} Once a category has been selected, the bottom half of the panel known as the **Category Browser** will display each resource based on the selected view method.

The Category Browser contains a dedicated toolbar with the following actions:

- <i class="fa-regular fa-folder"></i> **Search in the Selected Category**: When enabled, using the dedicated search field at the top of the panel will only search in the selected category
- <i class="fa-regular fa-lightbulb-on"></i> **Context Sensitivity**: When enabled, only categories relevant to the currently active project will be shown in the top half of the panel
- <i class="fa-regular fa-folder-tree"></i> **Show Objects from Subcategories**: When enabled, resources from subcategories of the selected category will be shown
- <i class="fa-regular fa-text"></i> **Show Names**: Toggles the resource name
- <i class="fa-regular fa-text-size"></i> **Show Categories**: Toggles the resource category
- <i class="fa-regular fa-user"></i> **Show Only User Library Content**: When enabled, only resources from the **User Library** will be displayed in the Graph Library panel. Learn more about the User Library [below](#user-library).
- <i class="fa-regular fa-table"></i> **Use a Table View**: Displays resources in a table view format
- <i class="fa-regular fa-chess-board"></i> **Display Small Icons**: Displays resources with small icons and, if enabled, positions the resource name and category to the right of each icon
- <i class="fa-regular fa-table-cells"></i> **Display Medium Icons**: Displays resources with medium icons and, if enabled, positions the resource name and category underneath each icon
- <i class="fa-regular fa-table-cells-large"></i> **Display Large Icons**: Displays resources with large icons and, if enabled, positions the resource name and category underneath each icon
- <i class="fa-regular fa-square-info"></i> **Show Library Status Bar**: Toggles the Library Status Bar located at the bottom of the Graph Library panel




## Favorites
InstaMAT Studio allows the user to add library items to their **Favorites**. These favorites can be located in the dedicated <i class="fa-regular fa-heart"></i> `Favorites` category in the **Category Browser** of the Graph Library panel and the [Resource Picker](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Resource_Picker) panel.

To add or remove an item as a Favorite:

1. Right click the resource to bring up the contextual menu
2. Choose `Add/Remove to Favorites`


## User Library
The User Library is a custom machine-dependent library integrated into InstaMAT Studio. Projects added to the User Library are accessible throughout the InstaMAT Studio interface and can be located in the Graph Library panel, in [Quick Search](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Quick_Search), and also with the [Resource Picker](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Resource_Picker) panel.

To add a project to the User Library:

1. Locate the "InstaMAT" folder located in the local machine's `~/Documents` directory by default.
2. Add projects to the "Library" subfolder.

InstaMAT Studio will automatically detect that the User Library has been altered and update the UI accordingly.