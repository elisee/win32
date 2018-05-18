---
Description: 'This event notifies the installer that it has to verify that the selected path is writable. If the path is cannot be written, then the event blocks further ControlEvents associated with the control.'
ms.assetid: '4672e2e4-a789-4050-81b9-92ec491745ac'
title: CheckExistingTargetPath ControlEvent
---

# CheckExistingTargetPath ControlEvent

This event notifies the installer that it has to verify that the selected path is writable. If the path is cannot be written, then the event blocks further ControlEvents associated with the control.

This event can be published by a [PushButton Control](pushbutton-control.md)or a [SelectionTree control](selectiontree-control.md). This event should be authored into the [ControlEvent table](controlevent-table.md).

This ControlEvent requires the user interface to be run at the [*full UI*](f-gly.md#-msi-full-ui-gly) level. This event will not work with a [*reduced UI*](r-gly.md#-msi-reduced-ui-gly) or [*basic UI*](b-gly.md#-msi-basic-ui-gly). For information, see [User Interface Levels](user-interface-levels.md).

## Published By

This ControlEvent is published by the installer.

## Argument

The name of the property containing the path. If the property is indirected, then the property name is enclosed in square brackets.

## Action on Subscribers

This ControlEvent does not perform an action on subscribers.

## Typical Use

A [PushButton](pushbutton-control.md) control on a browse dialog is tied to this event in the [ControlEvent](controlevent-table.md) table to check the selected path before returning to the selection dialog.

 

 


