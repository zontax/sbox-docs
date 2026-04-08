---
title: "Tonemapping"
icon: "☀️"
created: 2025-06-10
updated: 2025-10-02
---

# Tonemapping

# What is it

In s&box, tonemapping is a built-in post-processing effect that remaps HDR colors for display, which by default can appear dark until tuned. You can run other post-processing effects before or after tonemapping to use a full HDR buffer, or to use the resulting LDR buffer respectively.

s&box supports multiple different tonemappers, each with different ways of mapping HDR content to LDR, which affect the appearance of your scene. You can pick whichever you prefer.

## How to use it

On your camera GameObject, add a Tonemapping component.

## Properties

The s&box tonemapping component supports the following properties:

* **Mode**: the tonemapping operator algorithm (e.g., Reinhard, ACES).
* **Auto Exposure**
  * **Auto Exposure Enabled**: toggles automatic exposure adaptation.
  * **Minimum Exposure**: lower bound for exposure when auto exposure is active.
  * **Maximum Exposure**: upper bound for exposure when auto exposure is active.
  * **Rate**: speed at which exposure adapts to scene brightness changes.

## Modes

The s&box tonemapping component has the following modes available:

### Hable Filmic ![Hable Filmic on Construct with default exposure settings](./images/574c7c06-8f01-4ff4-82f2-dabf7e530ca5.png "right-50 =471x265")

Source 2's default tonemapper. Preserves detail in dark areas well, but loses punchiness in brighter areas.




### ACES ![ACES on Construct with default exposure settings](./images/0ed841b7-f46d-445f-9777-29e167ae8ce5.png "right-50 =471x265")

Filmic, very punchy, and has very high levels of contrast.





### Reinhard-Jodie ![Reinhard-Jodie on Construct with default exposure settings](./images/813f91b9-b8a4-4115-90b4-b782385ee906.png "right-50 =471x265")

Low contrast, but good for most environments.





### Linear ![Linear on Construct with default exposure settings](./images/7457a0c2-b296-4852-8b8f-285c17a3d7e6.png "right-50 =471x265")

Unbiased and only applies exposure.





### AgX ![AgX on Construct with default exposure settings](./images/5b88593a-8e64-4566-a82b-31d033803f70.png "right-50 =471x265")

The same tonemapper used by Blender. Similar saturation and detail to ACES, but lifts darker areas slightly more. Great for outdoor areas.
