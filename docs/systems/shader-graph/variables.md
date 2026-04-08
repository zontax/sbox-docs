---
title: "Variables"
icon: "💾"
created: 2025-08-20
updated: 2025-08-20
---

# Variables

Variables are useful for making your Graph easier to follow and understand, while also giving the option to expose certain values to the Material Editor and Code.

# Constants

Any Constant nodes created within a Shader will be compiled as constant values in shader code. These values cannot be changed

 ![](./images/be738c2b-c426-4900-97ef-0fdee4112ba0.png " =348x129")

# Variables

Any Constant nodes that are given a name are automatically exposed in the Material Editor. these values can be customized when creating a Material from the Shader.

 ![Giving a Float constant the name "Intensity"](./images/ea83033b-f2da-45ed-b1ed-0d79e8537bd7.png " =1381x770")

 ![How the Variable appears in the Material Editor](./images/d90498d1-ce0b-4d05-a0be-b7318e374895.png " =468x70")

If a Constant has "Is Attribute" set to true, then the value will not be exposed in the Material Editor and will instead be accessible via `RenderAttributes` in code.
