---
title: InstaMAT for Unreal Engine
description: This page will help you to get up to speed with InstaMAT for Unreal Engine in minutes.
published: true
date: 2023-03-03T09:37:03.711Z
tags: integrations, instamat for unrealengine
editor: markdown
dateCreated: 2023-03-02T17:31:20.600Z
---

## What is InstaMAT for Unreal Engine?

InstaMAT for Unreal Engine enables you to create and tweak procedural assets, such as textures and meshes within Unreal Engine.

<a name="prerequesites"></a>
## Prerequesites

InstaMAT for Unreal Engine always supports the latest Unreal Engine version on both Windows and macOS on the market. Support for the latest Unreal Engine version is typically added shortly after the official release. The plugin is maintained to be fully compatible with the newest version only.

<a name="installing-instamat-for-unreal-engine"></a>
## Installing InstaMAT for Unreal Engine

To get started, copy the `InstaMAT` folder to your project’s Plugins folder.

> If you cannot find the Plugins folder in the root of your Unreal Engine project, simply create it using either Windows Explorer or macOS Finder.{.is-info}

Finally, <kbd>right-click</kbd> your project file `projectname.uproject`, and depending on your operating system, select either Generate Xcode project (macOS) or Generate Visual Studio project files (Windows).

The next time you open the Unreal Engine project, the InstaMAT plugin will be compiled.

<a name="machine-authorization"></a>
## Machine Authorization

A workstation needs to be authorized before InstaMAT for Unreal Engine can be used. If you haven’t authorized InstaMAT on your workstation before, you will be asked to do so when starting the Unreal Engine project. Enter your license information and press Authorize to request a license for your workstation. Your workstation is now authorized for use with InstaMAT. 

> Make sure to deauthorize your workstation before uninstalling InstaMAT.{.is-warning}

<a name="machine-deauthorization"></a>
## Machine Deauthorization

To deauthorize your workstation before uninstalling InstaMAT for Unreal Engine, open the InstaMAT Settings Window and go to the `Deauthorize` panel. Enter your credentials in the panel, and click `Deauthorize Workstation`button.

<a name="setting-up-instamat-for-unreal-engine"></a>
## Setting up InstaMAT for Unreal Engine

Before InstaMAT for Unreal Engine can be used, the plugin needs to be configured. Go to the plugin settings inside the `Path Settings` panel specify the `InstaMAT Studio Installation` directory and your User path. InstaMAT for Unreal Engine requires both directories to load the InstaMAT library. The default user directory can be found on Windows usually at `C:\Users\<username>\Documents\InstaMAT` and on macOS at <some other directory>.

![instamat_settings_environment.png](/instamat_integrations/instamat_for_ue/instamat_settings_environment.png){.align-center}
  
<a name="using-instamat-for-unreal-engine"></a>
## Using InstaMAT for Unreal Engine

InstaMAT is fully integrated into Unreal Engine, and all asset generation features are available. This includes texture generation, mesh generation. Furthermore allows InstaMAT for Unreal Engine to use other Unreal Engine assets, such as textures and meshes, as inputs for your InstaMAT library.
  
<a name="importing-a-material"></a>
## Importing a Material

Materials can be imported through the InstaMAT Library or by importing an `.imp` file into the Unreal Engines `Content Browser`. If the `.imp` file contains multiple InstaMAT Graphs a graph object for each included InstaMAT Graph will be generated. The graph objects can be used to create instances of the same type. Instances are generated either through the context menu of the graph by right clicking on the asset and selecting `Create Instance` or through the detail settings inside the `Create New Instance` panel. 

![Create Instance From Context Menu](/instamat_integrations/instamat_for_ue/instamat_create_instance.png =500x){.align-center}

The context menu will spawn a naming dialog for the new instance the detail panel requires to provide a valid name inside the text field.

![Creating Instance From Detail Panel](/instamat_integrations/instamat_for_ue/instamat_create_instance_detail.png =800x){.align-center}
  
InstaMAT will generate an instance of the InstaMAT Graph with a connected material, and all assets, like textures, with the specified name. 

<a name="instance-settings"></a>
## Instance Settings

The generated textures or assets are tweakable through the detail settings of the instance. The detail settings contain material unspecific settings like resolution, execution format and seed settings, as well as, InstaMAT Graph specific settings. Changes will result in an execution of InstaMAT and the regeneration of the assets with the updated settings. For textures with high resolutions and a high bit depth the execution can get slow. InstaMAT instances provides a preview mode that allows fast iteration by reducing the resolution and bit depth.

<a name="instamat-materials"></a>
## InstaMAT Materials

All instances generate an accompanying material. The materials are highly configurable and have alread all textures connected to the right slots. If the materials are not required for the project, they can be ignored and the textures can be used directly.

<a name="exporting-assets"></a>
## Exporting Assets

Assets can be directly exported from within the instance. Textures can be exported in the desired file formats. InstaMAT for Unreal Engine allows exporting textures to the following file types: 
  * PNG (8 bit, 16 bit) 
  * TGA (8 bit, 16 bit)
  * TIFF (8 bit, 16 bit)
  * EXR (16 bit, 32 bit).
