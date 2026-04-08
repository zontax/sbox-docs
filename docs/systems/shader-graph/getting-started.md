---
title: "Getting Started"
icon: "🌱"
created: 2025-08-20
updated: 2025-08-20
---

# Getting Started

Shader Graph is a visual scripting language that compiles to shader code. This is great for those who have never touched shader languages as well as those who have deep shader knowledge and want to quickly and easily prototype a shader idea they have.

# Shader Graph Editor

You can open the Editor by creating a new Shader Graph asset and double clicking on it. Upon opening it, you will be met with 4 main sections:

 ![](./images/6c8b213e-8b7e-46a2-9de1-7660a936054a.png " =1387x811")


1. Preview - Where you can see your Shaders output update in real time. You can change the preview model/lighting to whatever you'd like.
2. Properties - An inspector window that allows you to edit the properties of the Shader or any selected nodes.
3. Graph - Where your nodes live. All graphs end with a "Material" node, which is where all your output values should eventually connect to.
4. Output - Will display any errors or warnings that may be present within your Shader Graph. You can also view the Console, Undo History, or Node Palette via the other tabs.

Each tab can be dragged around and re-positioned however you'd like, so feel free to customize it to your liking.

# Creating a Node

You can create any nodes that are available to you by simply right clicking anywhere in the Graph or by clicking and dragging nodes into the Graph from the Palette.

 ![](./images/2550c704-ee35-4fd6-b340-6d61dba5a06f.png "left-50 =171x380") ![](./images/314448b1-be5e-4bd4-a68e-22c8ec6b6746.png "left-50 =86x385")







# Input/Output Types

Each node has a certain amount of inputs and outputs, each with their own types which are color-coordinated to determine if the value is a vector and how many components it has.

 ![](./images/4316b255-eb91-4f59-8569-778fbbc68198.png " =240x144")

* Float (Green) - A single floating-point value
* Float2 (Purple) - A two-component vector (UV Coordinates, Screen Position)
* Float3 (Blue) - A three-component vector (Positions, Normals, RGB)
* Float4/Color (Yellow) - A four-component vector (RGBA, Positions with W)

Some nodes may output a different type given the input types, depending on how the node chooses to handle such a thing. 

 ![](./images/834afed9-ce98-4c58-aa94-6fed9b11d7e0.png "left-50 =257x159") ![](./images/028c962d-096e-4a65-b3c1-0a1330f3d858.png "left-50 =342x172")




Notice how the Multiply node returns a green Float value by default (given it's two Float inputs), but when a Color is input, the output becomes a yellow Float4/Color.

# Creating a Material

Once you have saved your Shader Graph, you'll see there is a compiled Shader file next to it, which can now be used as any other Shader when making a Material. You can also right click on it directly and select "Create Material" to instantly create a Material from it.

 ![](./images/b528b9c9-7888-4fb7-b879-3e04d052edce.png " =364x418")
