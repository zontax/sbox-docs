---
title: "Properties"
icon: "🔧"
created: 2025-08-20
updated: 2025-08-20
---

# Properties

There are a few basic properties that each Shader Graph has that affect the way the resulting Shader is drawn and how it can be used.

 ![](./images/11afc2ef-84ce-4e34-afb3-8602040941b4.png " =416x176")

# Blend Mode

Determines whether or not the Shader should support Opacity, and how it should be handled.

[19_21-23-MemorableRaven.mp4 1380x770](./images/60d7aae3-7578-4b87-854d-b68f54a3685c.png)

* Opaque - Always full opacity, no support for transparency.
* Masked - No transparency support, but will use dithering with anything in-between 0 and 1.
* Translucent - Full transparency support, allows you to see-through any opacities between 0 and 1.

# Shading Model

Determines whether or not the Shader should be affected by lighting.

[19_21-29-GreedyBlacklemur.mp4 1380x770](./images/448ec730-51a2-4a95-a59a-334c0b5cd8a1.png)

* Lit - Light will affect the material and can support Emissions, Normals, Roughness, Metalness, and Ambient Occlusion.
* Unlit - The material will output the raw colour to the screen regardless of the lighting in the Scene.

# Domain

Determines how/where the shader should be used.

[19_21-31-SingleMalamute.mp4 1380x770](./images/cbba0798-8ec6-4f5d-a8f1-15a3ffed4540.png)

* Surface - Used for any materials that will be used on 3D Objects placed within your scene. Can have a set Shading Model.
* Post Process - Used for post-processing materials that will be applied to the screen. Uses Screen Coordinates instead of Texture Coordinates.
