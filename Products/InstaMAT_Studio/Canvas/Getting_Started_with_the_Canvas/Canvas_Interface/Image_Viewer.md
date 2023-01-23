---
title: Image Viewer
description: The Image Viewer is InstaMAT Studio's interface for viewing 2D image information.
published: true
date: 2023-01-23T15:58:05.036Z
tags: instamat studio, canvas
editor: markdown
dateCreated: 2023-01-23T15:47:21.820Z
---

# Image Viewer

<img src="/instamat_studio/canvas/image_viewer_hero.png" alt="Image Viewer" width="600" />

The **Image Viewer** is InstaMAT Studio's interface for viewing 2D image information. The Image Viewer can be found in all of InstaMAT's project types. When creating materials in the <a href="">Canvas</a>, the Image Viewer provides a closer look while building out each material map such as the Height, Roughness, and Base Color information. In <a href="">Layering</a>, the Image Viewer provides a look at an asset's texture maps applied to the mesh's UV layout. In a <a href="">Materialize Image</a> project, the Image Viewer displays essential information for the construction and extraction of each material channel from the image.

The Image Viewer has many useful built-in features such as rulers, tiling preview options, and individual channel soloing. The following article overviews the UI and some useful workflows.

## Interface Overview

<img src="/instamat_studio/canvas/image_viewer_numbered.png" alt="Image Viewer Numbered" width="600"/>

The Image Viewer is divided up into three parts: The Image View, the Toolbar, and the Image Viewer Status Bar.

### <img src="/instamat_studio/canvas/1.png" alt="1" width="22"/> Image View

The following is how to navigate in the Viewport:

- **Pan**: **Left Click** and drag
- **Zoom**: **Right Click** and drag up and down or use the **Scroll Wheel**
- **Focus**: Press the **F** key. This fits the image into the Image Viewer's viewing area.

> If neither of these options are working, check if the ![Scale_Image_Auto_Icon](/instamat_studio/canvas/scale_image_auto_icon.png) `Scale Image Automatically` icon in the Image Viewer's toolbar is disabled.
{.is-info}

### <img src="/instamat_studio/canvas/2.png" alt="2" width="22"/> Toolbar

The Image Viewer contains a dedicated toolbar with the following actions:

- ![Save Image_Icon](/instamat_studio/canvas/save_project.png) **Save Image**: Saves the current image to disk
- ![Copy_Image_To_Clipboard_Icon](/instamat_studio/canvas/copy_image_to_clipboard_icon.png) **Copy Image to Clipboard**: Copies the current image to the Clipboard
- ![Focus_Scene_Icon](/instamat_studio/canvas/focus_scene_icon.png) **Focus**: Fits the image into the Image Viewer's viewing area
- ![Scale_Image_Auto_Icon](/instamat_studio/canvas/scale_image_auto_icon.png) **Scale Image Automatically**: Automatically scales the image loaded into the Image Viewer so that it fits the viewing area
- ![Tiling_Preview_Mode_Icon](/instamat_studio/canvas/tiling_preview_mode_icon.png) **Tiling Preview Mode**: Previews how the loaded image tiles either in a grid or cross layout
- ![Highlight_Tile_Border_Icon](/instamat_studio/canvas/highlight_tile_border_icon.png) **Highlight Central Tile Border**: Highlights the border of the central tile when using one of the Tiling Preview modes
- ![Paint_Checker_Icon](/instamat_studio/canvas/paint_checker_icon.png) **Paint Checkerboard**: Shows a checkerboard background in areas of the image that have transparency in the Alpha channel
- ![Pixel_Grid_Icon](/instamat_studio/canvas/pixel_grid_icon.png) **Show Pixel Grid**: Displays a pixel grid when zoomed in to a level where pixels can be distinguished
- ![Filtering_Icon](/instamat_studio/canvas/filtering_icon.png) **Image Filtering**: Enables bilinear filtering when magnifying the image
- ![Tonemapping_Icon](/instamat_studio/canvas/tonemapping_icon.png) **Tonemapping**: Applies tonemapping to the image

> By default, the Image Viewer automatically toggles Tonemapping based on the colorspace of the loaded image. To disable this, use the `Automatic Tonemapping` toggle in <a href="">Preferences</a> under the **'Interface'** tab in the **Image Viewer** section.
{.is-info}

- ![R_Icon](/instamat_studio/canvas/r_icon.png) **R**: Solos the Red channel
- ![G_Icon](/instamat_studio/canvas/g_icon.png) **G**: Solos the Green channel
- ![B_Icon](/instamat_studio/canvas/b_icon.png) **B**: Solos the Blue channel
- ![A_Icon](/instamat_studio/canvas/a_icon.png) **A**: Solos the Alpha channel
- ![Rulers_Icon](/instamat_studio/canvas/rulers_icon.png) **Show Rulers**: Toggles the Image Viewer rulers

### <img src="/instamat_studio/canvas/3.png" alt="3" width="22"/> Image Viewer Status Bar

<img src="/instamat_studio/canvas/image_viewer_status_bar.png" alt="Image Viewer Status Bar" width="600"/>

The **Image Viewer Status Bar** displays information on the image's size, current viewing scale, format, and channels.

## Loading Images into the Image Viewer

There are a few ways to load an image into the Image Viewer:

- <kbd>Double Click</kbd> an image in the <a href="Package_Management.html">Package Management</a> Panel
- <kbd>Right Click</kbd> a Node in the <a href="../../Canvas_Overview.html">Canvas</a> or Graph Output in the <a href="Graph_Object_Editor.html">Graph Object Editor</a> to bring up the contextual menu and choose `View Image`
- <kbd>Single Left Click</kbd> on an image input or output connector pin on a Node in the <a href="../../Canvas_Overview.html">Canvas</a>

## Tabs

<img src="Images/Image_Viewer_Tabs.gif" alt="Image Viewer switching through tabs" width="600"/>

Images can be loaded into multiple tabs. Tabs are displayed across the top of the Image Viewer.

To load an image into a new tab:

1. **Right Click** a Node or Graph Output to bring up the contextual menu
2. Choose **'View Image in New Tab'**

Tabs can be reorderd by dragging and dropping them into their new position. To close a tab, hover over it and click the (**X**) located in the right portion of the tab.

> ### A/B Testing
>
> Using tabs is a great way to perform A/B testing in the Canvas. Duplicate an effect with alternative settings for its attributes and open the output in a new tab. Switch between the two tabs to compare the results.
>
> ![GIF of A/B Testing with Tabs]()

## Previewing Image Tiling

<img src="Images/Image_Viewer_AB.gif" alt="Image Viewer A/B Testing with Tabs" width="600"/>

The Image Viewer provides built-in features to preview how an image tiles. To preview the tiling of an image, click the ![Icon](Images/Tiling_Preview_Mode_Icon.png) (Tiling Preview Mode) icon in the Image Viewer's toolbar. The tiling can be displayed in a grid or a cross layout. To identify the seams of the image, click the ![Icon](Images/Highlight_Tile_Border_Icon.png) (Highlight Central Tile Border) icon.

To disable the tiling preview, click the Tiling Preview Mode icon again and choose the ![Icon](Images/Tiling_Preview_Mode_Icon.png) (No Tiling) option.

## Channel Soloing

<img src="Images/Image_Viewer_Channels.gif" alt="GIF soloing each channel of a packed image output" width="600"/>

Many pipelines support "Channel Packing" or the packing of multiple pieces of information into one image output to optimize resources and performance. InstaMAT Studio's library contains nodes to extract and pack values into the Red, Green, and Blue channels of an image such as <a href="">Channel Compose</a> or <a href="">Channel Split</a>.

For example, a material's Roughness, Metalness, and Ambient Occlusion channels could be packed into one output like the following:

| Image Channel | Material Map Information |
| --- | --- |
| Red | Roughness |
| Green | Metalness |
| Blue  | Ambient Occlusion |

The Image Viewer makes it easy to solo each individual color channel of the active image by utilizing the **'R'**, **'G'**, **'B'**, and **'A'** buttons in the Image Viewer's toolbar.

> Another way to pack outputs into particular color channels of a single image output is with InstaMAT Studio's Image and Data Output Export Dialog. To learn more, please read our dedicated article <a href="">here</a>.