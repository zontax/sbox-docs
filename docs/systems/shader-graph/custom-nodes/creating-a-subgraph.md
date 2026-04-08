---
title: "Creating a Subgraph"
icon: "📦"
created: 2025-08-20
updated: 2025-09-01
---

# Creating a Subgraph

Subgraphs are a collection of Shader Graph nodes that can be easily reused as a single node across other Shaders and even other Subgraphs. This is an easy way of develop custom Shader Graph Functions of your own.

# Creating a Subgraph

You can create an empty Shader Graph Function by creating a new Asset and selecting Shader -> Shader Graph Function

 ![Creating an empty Subgraph](./images/1715b065-63a8-45fe-a963-f85187fe74f1.png " =370x157")

You can also create a Shader Graph Function from pre-existing nodes in a graph by selecting them all, right clicking, and selecting "Create Custom Node"

 ![Right clicking on pre-existing nodes to create a Subgraph from them](./images/4cb4f826-a09e-4555-b47c-510df08c1ca6.png " =554x362")

# Subgraph Properties

When no nodes are selected, you can edit the properties of the Subgraph itself, including it's Name, Description, Icon, and whether or not it should appear in the Node Library (If not, the node will not appear in the right click menu or the Palette)


 ![The Subgraph Properties](./images/66ec3fc8-c612-46eb-ab5e-b5ecc970f070.png "left-50 =385x194") ![The Custom Node appears when added to the Node Library](./images/bd607060-9aed-403b-9f37-d48dbedc5a1d.png "left-50 =257x212")





# Creating Outputs

Every Subgraph has a "Result" node, which is similar to the "Material" output node from regular Shader Graphs. However in a Subgraph you can define as many outputs as you want via the Properties panel, and can even choose which outputs to display in the Preview tab.


[Creating an Output called "Output", and previewing it as the Albedo of the Preview tab 1380x770](./images/932e2679-8a82-4ebb-9fc0-ca36aa9e54f3.png)

 ![The Output as seen on the Custom Node](./images/40e2c2a6-bd02-473b-b38a-6d8fcdcfb06a.png " =319x129")

# Creating Inputs

To create an input that is exposed on the resulting Subgraph Node, you can create a "Subgraph Input" node,

 !["Tint" is a Color input, and "Intensity" is a Float input](./images/4f3af89b-e3fa-497c-bf32-e08cf3d7d47c.png " =727x275")

 ![The properties for the "Tint" Subgraph Input](./images/2213789c-b737-4dbd-ab92-0cb17ec8c9b0.png " =418x285")

 ![The Inputs as seen on the Custom Node (with their default values)](./images/1162ec90-3f50-49eb-97a7-bd32d2a9a317.png " =423x169")

Setting "Is Required" to true will not pre-populate a default value, and will instead require you to connect another node for the Graph to compile.

Order is used to ensure the correct order of the inputs on the left side of the resulting node.

# Using Textures

Any Texture nodes that are used in a Subgraph MUST be named in order to compile, as they cannot (currently) be baked with the shader. This is because any Material made using this shader needs to define any Textures used, and whoever is using your shader might not have the referenced Texture.

When using a Subgraph Node, the default Texture can be changed via the Properties tab, alongside the unrequired Inputs.

 ![The default Texture property exposed in the Properties tab when the Custom Node is selected](./images/3a542fa2-ba17-422d-b018-124c9b05edfb.png " =696x168")
