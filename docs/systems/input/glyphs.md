---
title: "Glyphs"
icon: "🎨"
created: 2024-03-28
updated: 2025-07-10
---

# Glyphs

Input glyphs are an easy way to show users which buttons to press for actions, they automatically adjust for whatever device you're using and return appropriate textures.


```csharp
Texture JumpButton = Input.GetGlyph( "jump" );
```


:::info
 Glyphs can change from users rebinding keys, or switching input devices - so it's worth it just grabbing them every frame.

:::


You can also choose between the default and outlined versions of glyphs, like so:

```csharp
Texture JumpButton = Input.GetGlyph( "jump", true );
```

 ![PlayStation glyphs using the outline style](./images/c122f5bf-f2c4-4f97-a844-24e80dd03ef0.png " =2560x1277")

To use these quickly and easily in razor, you can use the resulting texture directly in an <Image> panel:

```markup
<Image Texture="@Input.GetGlyph( "jump", InputGlyphSize.Medium, true )" />
```


**Examples**

 ![Hints using keyboard and mouse](./images/ea10e59f-7514-4d10-9825-cf9b6d415ef6.png " =480x270")

 ![Hints using an Xbox controller](./images/435d3a0b-30ec-4a28-ac53-2c981147383e.png " =480x242")
