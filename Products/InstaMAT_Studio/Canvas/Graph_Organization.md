---
title: Graph Organization
description: InstaMAT Studio features several ways to keep graphs organized and readable.
published: true
date: 2023-02-23T19:04:18.848Z
tags: instamat studio
editor: markdown
dateCreated: 2023-02-23T13:08:05.737Z
---

# Graph Organization

The Canvas in InstaMAT Studio contains several features and utilities that help maintain the organization and readability of a graph. This article overviews a few  methods: Reroute nodes, Temporary Reroute Points and Comments.


## Reroute Nodes
![reroute2.gif](/instamat_studio/canvas/reroute2.gif =300x){.align-right} A Reroute node can be used to clean up connection points so that they flow in a more organized manner. Reroute nodes are permanent until deleted and are based on the type of information being carried through the connection. The quickest way to create a Reroute node is by <kbd>Right Clicking</kbd> on a connection to bring up Quick Search, then begin typing `reroute`.

Because Quick Search is context sensitive, the correct Reroute node will be selected. Pressing <kbd>Enter</kbd> will insert the Reroute node into the connection line where it was right clicked.

Another option is to drag a connection off of a node's input or output and letting go to invoke `Quick Search`. Beginning to type `reroute` and pressing <kbd>Enter</kbd> will insert the Reroute node at the end of the connection.

<br style="clear: right;"/>

![reroute3.gif](/instamat_studio/canvas/reroute3.gif =300x){.align-right} Reroute nodes allow for multiple connections to be spawned from its output. This allows different parts of the graph to share the same source.

<br style="clear: right;"/>

## Temporary Reroute Points
![reroute1.gif](/instamat_studio/canvas/reroute1.gif =300x){.align-right} Temporary Reroute Points can be added by <kbd>Double Clicking</kbd> on any connection in the canvas. Once created, the point can be repositioned and the connection will adjust accordingly. Additionally the keyboard shortcut <kbd>Alt/Option + Left Click</kbd> on a connection will insert a temporary reroute point where clicked.

<br style="clear: right;"/>

> If a connection line with a temporary reroute point is altered, for example the connection's origin or destination is adjusted, the temporary reroute point will automatically be removed.{.is-info}


### Merging Temporary Reroute Points

![reroute5.gif](/instamat_studio/canvas/reroute5.gif =400x){.align-right} Temporary Reroute Points can be merged together to form a Reroute node. Drag and drop one temporary reroute point onto another coming from the same source to quickly convert it.

<br style="clear: right;"/>

## Cleaning Up Unused Reroute Nodes

![reroute4.gif](/instamat_studio/canvas/reroute4.gif =400x){.align-right} To quickly delete any unused Reroute nodes *(nodes that don't have both a connected input and output connection)*, go to `Canvas` > `Clean Up Graph` in the Main Menu. The unused Reroute nodes and their connections will be removed from the graph.

<br style="clear: right;"/>

## Comments

Comments can be used to visually group a collection of nodes in a graph. Comments have an assortment of customizable properties such as a Name, Description, and Background Color. In addition to keeping a graph tidy in the Canvas view, comments are also visible on the [Minimap](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Minimap).

![comments_in_the_canvas.png](/instamat_studio/canvas/comments_in_the_canvas.png =800x){.align-center}

To create a comment:

1. Select a group of nodes
2. <kbd>Right Click</kbd> on one of the selected nodes to bring up the contextual menu
3. Choose `Comment`

> Additionally, comments can be made by pressing the keyboard shortcut <kbd>Shift + C</kbd>. {.is-info}

The comment will wrap around the selection. Moving the comment wil result in moving the nodes it contains. Comments can be deleted by selecting them and pressing the <kbd>Delete</kbd> or <kbd>Backspace</kbd> keys. If only the comment is selected, the contained nodes will not be deleted.

> It is possible to lock comments from being moved or selected by toggling the <i class="fa-regular fa-square-a-lock"></i> button in the [Canvas Toolbar](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Canvas_Toolbar).

### Comment Shortcut Hotkeys

Comments can have an assigned hotkey that focus the Canavs view when invoked. This makes it easy to jump around to various portions of the graph as it gets more complex. To assign a shortcut hotkey to a comment, select the comment and open the [Graph Object Editor](/Products/InstaMAT_Studio/Canvas/Canvas_Interface/Graph_Object_Editor). A number 0 - 9 can then be assigned to the comment. To use the hotkey, press <kbd>Option/Alt + (shortcut hotkey)</kbd>.