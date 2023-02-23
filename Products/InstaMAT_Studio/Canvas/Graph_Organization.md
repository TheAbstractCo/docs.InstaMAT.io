---
title: Graph Organization
description: InstaMAT Studio features several ways to keep graphs organized and readable.
published: true
date: 2023-02-23T13:38:54.140Z
tags: instamat studio
editor: markdown
dateCreated: 2023-02-23T13:08:05.737Z
---

# Graph Organization

The Canvas in InstaMAT Studio contains several features and utilities that help maintain the organization and readability of a graph. This article overviews a few  methods: Reroute nodes, Temporary Reroute Points and Comments.


## Reroute Nodes
![reroute2.gif](/instamat_studio/canvas/reroute2.gif =400x){.align-right} A Reroute node can be used to clean up connection points so that they flow in a more organized manner. Reroute nodes are permanent until deleted and are based on the type of information being carried through the connection. The quickest way to create a Reroute node is by <kbd>Right Clicking</kbd> on a connection to bring up Quick Search, then begin typing `reroute`.

Because Quick Search is context sensitive, the correct Reroute node will be selected. Pressing <kbd>Enter</kbd> will insert the Reroute node into the connection line where it was right clicked.

Another option is to drag a connection off of a node's input or output and letting go to invoke `Quick Search`. Beginning to type `reroute` and pressing <kbd>Enter</kbd> will insert the Reroute node at the end of the connection.

<br style="clear: right;"/>

![reroute3.gif](/instamat_studio/canvas/reroute3.gif =400x){.align-right} Reroute nodes allow for multiple connections to be spawned from its output. This allows different parts of the graph to share the same source.

<br style="clear: right;"/>

## Temporary Reroute Points
![reroute1.gif](/instamat_studio/canvas/reroute1.gif =400x){.align-right} Temporary Reroute Points can be added by <kbd>Double Clicking</kbd> on any connection in the canvas. Once created, the point can be repositioned and the connection will adjust accordingly. Additionally the keyboard shortcut <kbd>Alt/Option + Left Click</kbd> on a connection will insert a temporary reroute point where clicked.

<br style="clear: right;"/>

> If a connection line with a temporary reroute point is altered, for example the connection's origin or destination is adjusted, the temporary reroute point will automatically be removed.{.is-info}


### Merging Temporary Reroute Points

Temporary Reroute Points can be merged together to form a Reroute node. Drag and drop one temporary reroute point onto another coming from the same source to quickly convert it.

![reroute5.gif](/instamat_studio/canvas/reroute5.gif =800x) {.align-center}

## Cleaning Up Unused Reroute Nodes

To quickly delete any unused Reroute nodes *(nodes that don't have both a connected input and output connection)*, go to `Canvas` > `Clean Up Graph` in the Main Menu. The unused Reroute nodes and their connections will be removed from the graph.

![reroute4.gif](/instamat_studio/canvas/reroute4.gif =800x){.align-center}

## Comments