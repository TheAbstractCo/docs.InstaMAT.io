---
title: InstaMAT Project Integration
description: InstaMAT's project types are designed to integrate together seamlessly. In this article we go through a couple of examples on how to integrate various projects together.
published: true
date: 2023-02-27T14:55:39.768Z
tags: instamat studio
editor: markdown
dateCreated: 2023-02-27T13:58:03.026Z
---

# InstaMAT Project Integration

InstaMAT's project types are designed to integrate seamlessly together. `Layering` projects can be used within `Element Graphs` to extend their procedural functionality. Inversly, materials that are created with an Element Graph can be used directly as a layer in Layering. Materials that were generated from a photo using `Materialize Image` can be added directly to a `Material Layering` project to add more visual complexity. Integrating projects in this manner frees up and expands the many angles from which to approach a project, giving the artist more opportunities to work the way they think.

## Layering to Element Project Integration

The [Canvas](/Products/InstaMAT_Studio/Canvas) makes `Layering` project integration as easy as a drag and drop. To bring a Layering project into an `Element Graph`, drag it from the [Package Management](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Package_Management) panel directly into the Canvas. The layering project will become a node and provide all of the necessary graph input and outputs.

To begin visualizing the `Layering` project on a mesh, select the new node in the Canvas, navigate to the [Graph Object Editor](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Graph_Object_Editor) and pick one using the `Mesh` input and the [Resource Picker](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Resource_Picker) panel. Additionally, a mesh can be dragged into the Canvas as well. This mesh will also become a node and can be connected to the Layering project's `Mesh` input.

If the `Layering` project relies on any baked mesh maps and smart prefab materials, these can be generated using a `Mesh Bake` node.

To preview the outputs of a layering project on the mesh, first view the mesh in the [Viewport](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Viewport) by either clicking on the mesh node's output pin the Canvas, or by <kbd>Right-Clicking</kbd> the mesh node and choosing `View Mesh`. Then <kbd>Right-Click</kbd> on the `Layering` project node and choose `Preview as 3D Material`.

> Integrating `Layering` projects into `Elements` enhances them with all of the Canvas's procedural functionality and flexibility. You can apply masks, effects, and mesh modifier nodes while also exposing additional graph inputs to easily adjust settings using sliders. {.is-info}

## Element to Layering Project Integration

`Elements` created from an `Element Graph` can be used in many different facets of `Layering`. A PBR material can be used as an `Element Layer` or `Element Brush`. In fact, any channel from a PBR material created in InstaMAT Studio can be utilized in a `Multi-Channel Layer`. The Roughness channel can be taken from a "Dirty Iron" material while the BaseColor channel can be taken from an "Aged Wood". Element/Layering integration is as flexible as it is powerful.

There are many ways to bring in an `Element` into a `Layering` project:

- Drag a material from either the [Graph Library](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Quick_Search) or the [Package Management](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Package_Management) panel onto a mesh in the viewport. This will apply the material to the specific mesh or sub-mesh and mask off others.
- Drag a material into the layer stack. This will fill the entire project with a newly-created `Element Layer`.
- Click the <i class="fa-regular fa-layer-plus"></i> (Add New Layer) button below the layer stack and hoose `Element Layer`. Pick the element from the [Resource Picker](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Resource_Picker) panel.
- Click the <i class="fa-regular fa-layer-plus"></i> (Add New Layer) button below the layer stack and choose `Multi-Channel Layer`. Open the <i class="fa-regular fa-layer-group"></i> (Layer Channels) tab. Next to any channel, choose the <i class="fa-regular fa-flux-capacitor"></i> (Graph Resource) icon to choose an Element and utilize a matching output (for example the BaseColor output of the chosen material used as the BaseColor channel for the Multi-Channel Layer).

> This is only the beginning. Masks, Brushes, Stencils, Decals, Filters, Generators, and Effects can all be created using the `Element Graph`. {.is-info}

## Materialize Image Project Integration

Materials generated from a photo using the `Materilize Image` project type can be treated just like any other material in InstaMAT Studio. Once created, a Materialized photo can be imported into a `Layering` project by either dragging and dropping it or by clicking the <i class="fa-regular fa-layer-plus"></i> (Add New Layer) button and selecting `Element Layer`.

These materials can be blended together in an `Element Graph` by dragging them into the [Canvas](/Products/InstaMAT_Studio/Canvas) where it will become a node or used in a `Material Layering` project as a layer. Additionally, properties of the `Materialize Image` process can be exposed for use later on. This can be done by <kbd>Right-Clicking</kbd> a property in the [Graph Object Editor](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Graph_Object_Editor) when creating the material and choosing `Expose as Input Parameter`. The exposed parameter will be available for tweaking once the node or layer is selected in its new respective project.