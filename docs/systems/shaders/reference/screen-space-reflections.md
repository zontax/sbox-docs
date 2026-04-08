---
title: "Screen-Space Reflections"
icon: "🪞"
created: 2025-07-28
updated: 2025-07-28
---

# Screen-Space Reflections

SSR is done in three steps

* Intersection
  * Uses the [G-Buffer] and [Screen Space Tracing] right after we do the Depth Pre-Pass, uses the result from last frame reprojected with [Motion]
  * ![](./images/8313278f-3460-487a-afdc-1b0432f29ee1.png " =1133x605")
* Denoising
  * Accumulates the result and makes it pretty taking off the rough edges
  * ![](./images/09a84696-af0a-4fad-bf94-c12b3af40db9.png " =1133x605")
* Compositing
  * Sets the texture to be composited with [Dynamic Reflections]
  * ![](./images/df608457-5edc-4d34-8750-0858ca51cb91.png " =1094x538")
