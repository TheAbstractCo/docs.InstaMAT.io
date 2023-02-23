---
title: Graph Organization
description: InstaMAT Studio features several ways to keep graphs organized and readable.
published: true
date: 2023-02-23T13:12:49.425Z
tags: instamat studio
editor: markdown
dateCreated: 2023-02-23T13:08:05.737Z
---

# Graph Organization

The Canvas in InstaMAT Studio contains several features and utilities that help maintain the organization and readability of a graph. This article overviews to two main methods: Reroute Nodes and Comments.


## Reroute Node
![reroute2.gif](/instamat_studio/canvas/reroute2.gif =500x){.align-right}A Reroute node is permanent until deleted and is based on the type of information being carried through the connection. The quickest way to create a Reroute node is by **right clicking** on a connection to bring up Quick Search, then begin typing *"reroute"*.

Because Quick Search is context sensitive, the correct Reroute node will be selected. Pressing **Enter** will insert the Reroute node into the connection line where it was right clicked.

Another option is to drag a connection off of a node's input or output and letting go to invoke Quick Search this way. Beginning to type *"reroute"* and pressing enter will insert the Reroute node at the end of the connection.

![Adding a Reroute node using Quick Search](/Images/Reroute2.gif)

Reroute nodes allow for multiple connections to be spawned from its output. This allows different parts of the graph to share the same source.

![Branching a connection off of a Reroute node](/Images/Reroute3.gif)

## Temporary Reroute Point
Temporary reroute points can be added by **Double Clicking** on any connection in the canvas. Once created, the point can be repositioned and the connection will adjust accordingly. Additionally the keyboard shortcut **Alt/Option + Left Click** on a connection will insert a temporary reroute point where clicked.

![Adding a temporary reroute point](/Images/Reroute1.gif)

>If a connection line with a temporary reroute point is altered, for example the connection's origin or destination is adjusted, the temporary reroute point will automatically be removed.


## Merging Temporary Reroute Points

Temporary reroute points can be merged together to form a Reroute node. Drag and drop one temporary reroute point onto another coming from the same source to quickly convert it.

![Merging temporary reroute points](/Images/Reroute5.gif)

## Cleaning Up Unused Reroute Nodes

To quickly delete any unused Reroute nodes *(nodes that don't have both a connected input and output connection)*, go to **Canvas > Clean Up Graph**. The unused Reroute nodes and their connections will be removed from the graph.

![Removing unused Reroute nodes with the Clean Up Graph menu item](/Images/Reroute4.gif)