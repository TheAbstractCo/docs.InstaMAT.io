---
title: Canvas Navigation
description: The Canvas View is navigated by panning and zooming.
published: true
date: 2023-02-23T11:23:39.098Z
tags: instamat studio, canvas
editor: markdown
dateCreated: 2023-01-23T21:04:46.005Z
---

# Canvas Navigation

The Canvas View is navigated by panning and zooming.

## Panning

![Panning](/instamat_studio/canvas/pan_canvas.gif =400x){.align-right} To Pan, <kbd>Left Click</kbd> and drag on an empty space. If an object in the Canvas such as a node or comment is in the way of your cursor, hold the <kbd>Space Bar</kbd> to ignore any Canvas objects. 

Additionally, pressing the <kbd>Arrow Keys</kbd> will incrementally pan the Canvas view in the key's direction.

<br style="clear: right;"/>

## Zooming

![Zooming](/instamat_studio/canvas/zoom_canvas.gif =400x){.align-right} To Zoom, <kbd>Right Click</kbd> and drag up or down.

<br style="clear: right;"/>

## Mouse Wheel

InstaMAT Studio adapts to the native mouse wheel behavior of the platform it is running on. The mouse wheel by itself will either zoom or perform a vertical scroll. Holding the <kbd>Shift</kbd> key while using the mouse wheel will swap behaviors.

To change the default mouse wheel behavior, choose the behavior in the `Canvas` tab in the [Preferences](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Preferences) panel.

![Mouse Wheel Behavior in Preferences Window](/instamat_studio/canvas/mouse_wheel_behavior.png =600x){.align-center}

<!-- Image to be updated once translation keys are removed from current build. -->

## Selecting Objects

![Selecting oobjects](/instamat_studio/canvas/select_canvas.gif =400x){.align-right} To select an object in the Canvas view, <kbd>Left Click</kbd> the object.

To select multiple objects, hold <kbd>Shift</kbd> and drag a rectangular selection of the objects to select.

<br style="clear: right;"/>

## Moving Objects

![Moving Objects](/instamat_studio/canvas/move_canvas.gif =400x){.align-right} To move an object from one place in the graph to another, select the object or objects then <kbd>Left Click</kbd> and drag to the new position.

<br style="clear: right;"/>

> If you'd like to pan the Canvas view while dragging an object, drag the object to a border of the Canvas view to pan in that direction. This also works when dragging connections from a node's input or output.
{.is-info}

## Deleting Objects

![delete_canvas.gif](/instamat_studio/canvas/delete_canvas.gif =400x){.align-right}To delete an object from the Canvas view, select it, then press the <kbd>Delete</kbd> or <kbd>Backspace</kbd> key. 

Additionally objects can be deleted by <kbd>Right Clicking</kbd> them to bring up the context menu, then choosing `Delete`.

<br style="clear: right;"/>

> **Connections:** Connections can be selected and deleted separately from the nodes that they are attached to. To delete a connection or set of connections, select them and use the <kbd>Delete</kbd> or <kbd>Backspace</kbd> key.{.is-info}



## Duplicating Objects

![duplicate_canvas.gif](/instamat_studio/canvas/duplicate_canvas.gif =400x){.align-right}To duplicate an object in the Canvas view, select it, then <kbd>Option/Alt</kbd> + <kbd>Click and Drag</kbd> the duplicate into position.

Additionally, nodes can be copied and pasted with the standard <kbd>Cmd/Ctrl</kbd> + <kbd>C</kbd> and <kbd>Cmd/Ctrl</kbd> + <kbd>V</kbd> keyboard shortcuts.

<br style="clear: right;"/>

## Focusing

Focusing in InstaMAT Studio is a universal term meaning to frame up the contents or a selection so that it fits within the bounds of the view. To focus in the Canvas, use the <kbd>F</kbd> key. To focus on a portion of the graph, select the objects to focus on first, then hit <kbd>F</kbd>.

![focus_canvas.gif](/instamat_studio/canvas/focus_canvas.gif){.align-center}

> Another way to frame up a portion of the graph so that it fits the view is to drag a rectangular selection in the [Minimap](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Minimap).
{.is-info}