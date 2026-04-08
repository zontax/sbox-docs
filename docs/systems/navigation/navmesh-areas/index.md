---
title: "NavMesh Areas"
icon: "⏹️"
created: 2024-12-03
updated: 2025-10-29
---

# NavMesh Areas

NavNesh Areas can affect NavNesh generation and agent behavior/pathing.\n ![](./images/d5eda4fd-ed43-41f9-9ee4-358b059ac062.png " =423x191")The NavMeshArea component is used to define the location, shape and type of an area.

 ![](./images/c2f35aa4-e22d-4341-95a4-0fdbb648ee54.png " =423x157")

You can also specify the Area for a link component.

 ![](./images/67a7f9a0-55f2-4842-90ce-202a2c2f5d14.png " =428x539")The NavMeshAreaDefinition resource is used to define properties of the Area.

# Limitations

* Currently there is a limit of 24 NavMeshAreaDefinition, but you can assign them to as many Area Components as you like
* **Static** areas are basically free.
* **Moving** areas are a bit more expensive, but you should be able to have at least a couple of dozens of them.
