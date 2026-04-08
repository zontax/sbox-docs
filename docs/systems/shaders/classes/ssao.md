---
title: "SSAO"
icon: "🕳️"
created: 2024-12-05
updated: 2024-12-10
---

# SSAO

If your custom shader implements custom lighting you can sample the screen space ambient occlusion value for your lighting calculations.

```cpp
float ScreenSpaceAmbientOcclusion::Sample( float4 ScreenPosition )
```

 ![](./images/32bf9e46-c7b3-4888-b22c-82addbb1182c.png) ![](./images/633aa24a-fee6-4c58-9b09-94f7ee88b476.png "right-50")

## Custom Ambient Occlusion

You can implement your own ambient occlusion solution simply by providing the screen space ambient occlusion texture globally from your own component:

```csharp
commands.SetGlobal( "ScreenSpaceAmbientOcclusionTexture", AOTextureCurrent.ColorIndex );
```
