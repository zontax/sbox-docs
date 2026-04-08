---
title: "Instance Overrides"
icon: "💱"
created: 2025-08-01
updated: 2025-08-01
---

# Instance Overrides

Prefab instance overrides allow you to customize individual instances of a prefab without affecting the original prefab or other instances. This lets you create variations of the same prefab while maintaining the connection to the original template.

When you modify a property, add a component, or change the hierarchy of a prefab instance, these changes are stored as overrides. The instance remembers what's different from the original prefab while still receiving updates when the prefab itself changes.

# Visual Indicators

In the scene hierarchy, prefab instances with overrides are clearly marked to show their modified state.

 ![](./images/ec8022c1-c396-4aaf-8ca2-6eba31fbf1e1.png " =353x365")

Overridden properties and components are highlighted in the inspector, making it easy to see what's been customized on each instance.

 ![](./images/3f7b3afe-3db2-461b-8705-ed538200fa1e.png " =431x928")

# Types of Overrides

## Property Overrides

Change any property value on GameObjects or Components within the prefab instance. Position, rotation, scale, component properties, and GameObject settings can all be overridden.

 ![](./images/12fecea3-5c44-4d61-a8d2-27471b7de65d.png " =420x217")

## Component Additions

Add new components to GameObjects within the prefab instance. These components only exist on this specific instance.

 ![](./images/a19ff92c-bd82-48b9-9c7f-13c18961fb5d.png " =422x232")

## GameObject Additions

Add new child GameObjects to the prefab instance hierarchy. These children are unique to this instance.

 ![](./images/c319b278-24c8-4128-871c-3736269185ee.png " =343x26")

# Managing Overrides

The inspector and scene hierarchy provides controls to manage overrides on individual properties and objects:

 ![](./images/b77f68a2-8565-41f6-9bb1-094a453ef36f.png " =646x448")


 ![](./images/163e2024-dff8-40b8-b582-4f4dcaa48b6b.png " =613x230")

## Reverting Overrides

Right-click on any overridden property or object and select `Revert Override` to restore the original prefab value. You can also revert all overrides on a GameObject or the entire prefab instance.

## Applying Overrides

To make your instance changes permanent, right-click and select `Apply to Prefab`. This updates the original prefab with your changes, affecting all other instances.

# Nested Prefabs

When working with prefabs that contain other prefabs (nested prefabs), overrides work hierarchically. Changes to nested prefab instances are stored on the outermost prefab instance.

 ![](./images/ed67ca94-9c3c-47ac-9876-0397b991495c.png " =335x78")

This ensures that all override data is centralized and properly managed even in complex prefab hierarchies.
