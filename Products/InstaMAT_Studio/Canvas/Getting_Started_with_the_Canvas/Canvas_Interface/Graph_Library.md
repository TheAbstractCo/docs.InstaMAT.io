---
title: Graph Library
description: The Graph Library panel provides access to the vast node library built into InstaMAT Studio.
published: true
date: 2023-01-20T19:03:52.381Z
tags: instamat studio
editor: markdown
dateCreated: 2023-01-20T18:58:18.667Z
---

# Graph Library

<img src="/instamat_studio/canvas/graph_library.png" width="300"/>

The **Graph Library** panel provides access to the vast node library built into InstaMAT Studio. Each set of nodes and resources is broken down into categories and can be searched with the dedicated search field at the top of the panel.

To use a resource from the Graph Library, drag it from the library panel into your project.

>In addition to the Graph Library, a faster way to use a node from InstaMAT's library is by using **Quick Search** — A context sensitive search box with extensive functionality built right into the Canvas. To learn more, read our article on Quick Search <a href="">here</a>.

## Interface Overview

### Category Browser
<img src="/instamat_studio/canvas/gl_top.png" width="300"/>

The top area of the Graph Library is the **Category Browser** and contains all of the categories and resources available in the library. Use the dedicated search field at the top to filter through the available resources.

### Content Browser

<img src="/instamat_studio/canvas/gl_bottom.png" width="300"/>

Once a category has been selected, the bottom half of the panel known as the **Category Browser** will display each resource based on the selected view method. The Category Browser contains a dedicated toolbar with the following actions:

- ![icon](/instamat_studio/canvas/search_in_selected_category_icon.png) **Search in the Selected Category**: When enabled, using the dedicated search field at the top of the panel will only search in the selected category
- ![icon](/instamat_studio/canvas/context_sensitivity_icon.png) **Context Sensitivity**: When enabled, only categories relevant to the currently active project will be shown in the top half of the panel
- ![icon](/instamat_studio/canvas/show_objects_from_subcategories_icon.png) **Show Objects from Subcategories**: When enabled, resources from subcategories of the selected category will be shown
- ![icon](/instamat_studio/canvas/show_names_icon.png) **Show Names**: Toggles the resource name
- ![icon](/instamat_studio/canvas/show_categories_icon.png) **Show Categories**: Toggles the resource category
- ![icon](/instamat_studio/canvas/show_only_user_library_content_icon.png) **Show Only User Library Content**: When enabled, only resources from the **User Library** will be displayed in the Graph Library panel. Learn more about the User Library below.
- ![icon](/instamat_studio/canvas/use_a_table_view_icon.png) **Use a Table View**: Displays resources in a table view format
- ![icon](/instamat_studio/canvas/display_small_icons_icon.png) **Display Small Icons**: Displays resources with small icons and, if enabled, positions the resource name and category to the right of each icon
- ![icon](/instamat_studio/canvas/display_medium_icons_icon.png) **Display Medium Icons**: Displays resources with medium icons and, if enabled, positions the resource name and category underneath each icon
- ![icon](/instamat_studio/canvas/display_large_icons_icon.png) **Display Large Icons**: Displays resources with large icons and, if enabled, positions the resource name and category underneath each icon
- ![icon](/instamat_studio/canvas/show_library_status_bar_icon.png)  **Show Library Status Bar**: Toggles the Library Status Bar located at the bottom of the Graph Library panel


## Favorites
InstaMAT Studio allows the user to add library items to their **Favorites**. These favorites can be located in the dedicated ![Icon](/instamat_studio/canvas/favorites_icon.png) `Favorites` category in the **Category Browser** of the Graph Library panel and the <a href="">Resource Picker</a> panel.

To add or remove an item as a Favorite:

1. Right click the resource to bring up the contextual menu
2. Choose `Add/Remove to Favorites`


## User Library
The User Library is a custom machine-dependent library integrated into InstaMAT Studio. Projects added to the User Library are accessible throughout the InstaMAT Studio interface and can be located in the Graph Library panel, in <a href="Quick_Search.html">Quick Search</a>, and also with the <a href="">Resource Picker</a> panel.

To add a project to the User Library:

1. Locate the "InstaMAT" folder located in the local machine's `~/Documents` directory by default.
2. Add projects to the "Library" subfolder.

InstaMAT Studio will automatically detect that the User Library has been altered and update the UI accordingly.