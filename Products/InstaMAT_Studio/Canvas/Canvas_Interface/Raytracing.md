---
title: Raytracing
description: The Raytracing Panel contains the AMD Radeon™ ProRender raytracing engine. This allows users to quickly generate photo-real images with just a few clicks using both CPUs and GPUs.
published: true
date: 2023-01-23T20:51:19.897Z
tags: instamat studio
editor: markdown
dateCreated: 2023-01-23T20:42:52.095Z
---

# Raytracing

![Raytracing_Panel](/instamat_studio/canvas/raytracing_panel.png)

The **Raytracing** Panel contains the AMD Radeon™ ProRender raytracing engine. This allows users to quickly generate photo-real images with just a few clicks using both CPUs and GPUs. The automatic PBR material conversion allows for seamless usability between the real-time <a href="../Viewport.html">Viewport</a> and the AMD Radeon™ ProRender scene. The powerful post-processing stack enables final-shot compositing and product shots to be generated directly inside InstaMAT Studio.

## Interface Overview

The user interface for the Raytracing Panel is divided into three parts. The Settings on the left, the Toolbar at the top, and the Raytracing Viewport on the right.

### Settings

<img src="/instamat_studio/canvas/raytracing_settings.png" alt="Raytracing Settings" width="400"/>

The left panel contains all of the render settings for the AMD Radeon™ ProRender engine.

> The settings panel can be hidden by clicking the arrow between the settings panel and the Raytracing Viewport.
{.is-info}

#### Controls

<img src="/instamat_studio/canvas/raytracing_controls.png" alt="Raytracing Controls" width="400"/>

These buttons control the state of the raytracing engine.

- ![Play/Pause](/instamat_studio/canvas/play_icon.png) **Play/Pause**: Starts or pauses the render
- ![Stop](/instamat_studio/canvas/stop_icon.png) **Stop**: Stops the render

> The rendered image size and current sample iteration are displayed along the bottom in the Raytracing Panel's status bar.
{.is-info}

#### Settings

These are the main settings for the Raytracing Panel.

- **Render Engine**: Sets the active raytracing render engine
- **Raysampler Type**: Determines the ray sampling type
	- **Sobol**: casts rays in a uniform fashion
	- **Adaptive**: prioritizes ray casting in noisy areas
	- **Random**: cast samples randomly
- **Screen**: Sets the `Width` and `Height` of the rendered image
- **Ray Recursion**: Sets the maximum recursion depth for rays
- **Ray Depth**: Sets the maximum depth for refraction, glossy, etc.
- **Radiance Clamp**: Sets the radiance clamp to avoid fire flies
- **Maximum Sample Count**: Sets the maximum amount of samples for the rendered image. Rendering stops if the amount of samples have been generated.
- **Preview Sample Step**: Displays a render preview every "x" number of samples. When set to `Off` by sliding to or entering '0', only the final image is displayed in the Raytracing Viewport.
- **Render IBL**: Renders the (Image Based Lighting) background image
- **Preview**: Renders the image at half resolution for the first 10 samples
- **Image Filtering**: Applies filtering when scaling the image to fit the Raytracing Viewport

> To scale the rendered image to fit the Raytracing Viewport, click the ![Scale Image](/instamat_studio/canvas/scale_image_icon.png) (Scale Image) button in the Raytracing Panel's toolbar.
{.is-info}

- **Viewport Interaction**: Allows interacting with the scene through the Raytracing Viewport. The same navigation hotkeys can be used from InstaMAT Studio's real-time <a href="../Viewport.html">Viewport</a>.
- **Auto Pause**: Pauses rendering after one second of user input inactivity
- **Available Devices**: Lists the compatible devices available for use. Click the switch next to the device to use it for raytracing.

#### Camera Settings

These settings adjust the raytracing camera.

- **Active Camera**: Selects the active camera used for raytracing
- **Lens Shift**: Shifts the camera for fine adjustments
- **Tilt Correction**: Tilts the camera for fine adjustments
- **Focal Tilt**: Sets the focal tilt of the camera
- **Aperture Blade Count**: Sets the blade count for the camera's aperture. This changes bokeh shapes and affects the camera blur.
- **Exposure**: Sets the exposure of the camera
- **F-Stop**: Sets the camera's F-Stop. Decrease to provide a more shallow depth of field.
- **Focus Distance**: Sets the distance of the camera's focus point. Objects at this distance will be in focus.
- **Angular Motion In Degrees**: Applies motion blur with the set angle in degrees
- **Angular Motion Axis**: Sets the axis for the Angular Motion blur
- **Linear Motion Axis**: Sets the Linear Motion Axis using an XYZ vector

#### Tone Mapping

These settings apply to the photographic tone mapping filter that emulates the work of a camera.

- **Type**: Sets the tone mapping type. Various tone mapping types allow for different image grading results. Depending on the type, different settings are enabled for finer control over image values and exposure.
	- **Auto-linear**: Photographic tone mapper that uses default camera characteristic values and the average luminance of a picture
	- **Reinhard**: Performs Reinhard02 tone mapping
	- **Photometric**: Photographic tone mapper that creates a photorealistic color grade
- **Gamma**: Provides a gamma correction value
- **Exposure**: Sets the film exposure time
- **Sensitivity**: Sets the Luminance of the scene (in candela per m^2)
- **F-Stop**: Sets the aperture f-number
- **Vignette**: Provides a camera vignette around the rendered image
- **Saturation**: Sets the Saturation used for sensitivity computation
- **Lighten**: Brightens up highlights. Higher settings bring highlights closer to white.
- **Darken**: Darkens shadowed areas. Higher settings bring shadowed areas closer to black.
- **Focal Length**: Sets the camera focal length
- **ISO**: Sets the film ISO value
- **Use ISO**: If enabled, uses the provided ISO value. Otherwise, uses the `Saturation` to compute sensitivity.

#### Post Processing Stack

The Post-processing stack includes various filters and effects to complete entire product shots without needing to export the render into an image editing program. To enable a feature, click the toggle to the right.

- **Anti-aliasing (MLAA)**: Adds anti-aliasing to the final image
- **Sobel Filter**: Creates a Black/White line effect
- **Posterize**: Creates a poster effect. Specify levels of color depth with the provided `Levels` input when enabled.
- **Bloom**: Adds bloom to bright areas in the image. Adjust using provided `Radius` `Decay` `Threshold` and `Weight` settings when enabled.
- **Motion Blur**: Adds a directional blur using the provided `Radius`and `Axis Direction` settings when enabled
- **Denoise**: Denoises the image using different algorithms
	- **Type**: Sets the algorithm used to denoise the image. Can be set to `Median` or `AI`.
	- **Median**: Sets the median value in pixels
  
> It is recommended to keep the `Median` setting to a value of '1'.
{.is-info}

### Toolbar

<img src="/instamat_studio/canvas/raytracing_toolbar.png" alt="Raytracing Toolbar" />

The Raytracing Panel contains its own dedicated toolbar to provide shortcuts to further functionality.

- ![Icon](/instamat_studio/canvas/save_current_icon.png) **Save Current**: Saves the currently active channel to disk
- ![Icon](/instamat_studio/canvas/save_all_channels_icon.png) **Save all channels**: Saves all channels to disk
- ![Icon](/instamat_studio/canvas/scale_image_icon.png) **Scale Image**: Automatically scales the rendered image in the Raytracing Viewport so that it fits the viewing area
- ![Icon](/instamat_studio/canvas/image_filtering_icon.png) **Image Filtering**: Applies image filtering when scaling the image to fit the Raytracing Viewport
- ![Icon](/instamat_studio/canvas/viewport_interaction_icon.png) **Viewport Interaction**: Allows the user to interact with the Raytracing Viewport to adjust the scene
- ![Icon](/instamat_studio/canvas/paint_checkerboard_icon.png) **Paint Checkerboard**: Shows a checkerboard background in areas of the image that have transparency
- ![Icon](/instamat_studio/canvas/r_icon.png) **R**: Solos the Red channel
- ![Icon](/instamat_studio/canvas/g_icon.png) **G**: Solos the Green channel
- ![Icon](/instamat_studio/canvas/b_icon.png) **B**: Solos the Blue channel
- ![Icon](/instamat_studio/canvas/a_icon.png) **A**: Solos the Alpha channel
- **Viewport AOV**: (Arbitrary Output Variable) Displays the many render passes available from the raytracing engine. The following passes are available:
	- Color
	- Ambient Occlusion
	- DiffuseAlbedo
	- Geometric Normal
	- Shading Normal
	- Opacity
	- Depth
	- Object ID
	- Emission
	- Direct Illumination
	- Indirect Illumination

## Raytracing Settings Presets

Raytracing settings can be saved and loaded as a preset. To Save or Load a settings preset, go to the main menu and choose `Save Settings` or `Open Settings...` from the **File** menu.

> For more information on AMD Radeon™ ProRender, please refer to the official documentation: <a href="https://radeon-pro.github.io/RadeonProRenderDocs">https://radeon-pro.github.io/RadeonProRenderDocs</a>.
{.is-info}