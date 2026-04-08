---
title: "Skeletal Animation"
icon: "🦴"
created: 2025-11-17
updated: 2025-11-26
---

# Skeletal Animation

You can animate skinned characters directly in the editor using Movie Maker. This tutorial covers:

* Enabling the skeletal animation tools
* Importing animation sequences from a model
* Generating bone animation track data using AnimGraph
* Recording bone animations from gameplay
* Upgrading legacy procedural bone object animations
* Using IK to manipulate poses

# Getting Started

Movie Maker's skeletal animation tools are enabled if you have at least one *SkinnedModelRenderer* in your movie with a *Bones* sub-track. When enabled for a renderer, you'll see its skeleton.

You'll also need to be in the [Motion Editor](/systems/movie-maker/motion-editing.md) to do the modifications described in this tutorial.


[sbox-dev_cnj2vQLxyW.mp4 1096x908](./images/6277da6f-5e41-4701-82bf-f7da4430d51d.png)

# Base Animations

Animating skinned objects from scratch can be time consuming, so you'll usually want to start with an imported or generated base-level animation that you can tweak later.

## Importing Animation Sequences

For simple sequences you can just load an animation from your model.


1. Make sure you're in *Motion Editor* mode
2. In the timeline, select a time range that you want to import an animation for
3. Right-click on a selected region of track that belongs to the object you want to animate
4. Select *Import Anim Sequence*, and pick a clip
5. Drag the imported sequence around or trim the start / end times
6. Click the green *Apply* button to save the modification


[sbox-dev_Ym9B95sPum.mp4 1148x1020](./images/1ff673bd-a93c-468e-b641-b5f1f165d23c.png)


:::tip
Root motion will be included by default, you can disable it by locking the *LocalPosition* / *LocalRotation* tracks of the object you're animating.

:::

## Generating Using AnimGraph

You can save a lot of time by letting AnimGraph generate an animation for you. You'll just need *LocalPosition* and *LocalRotation* tracks describing how your character moves. These can be created in any way you like: keyframes, recording, or motion editing.

### Rotate With Motion

If you've only got a *LocalPosition* track, you can generate a *LocalRotation* track that always looks in the direction of movement. Just select the time range you want to generate rotations for in the motion editor, then right-click and select *Rotate with Motion* in the context menu, and apply if you're happy with it.


[sbox-dev_tHY2E5IKIB.mp4 1298x1064](./images/9447385c-38dd-4be8-82cb-2194598e3fe0.png)

Before moving on to the next step, feel free to tweak the generated *LocalRotation* track if you want your character to side-step or walk backwards at any point.

### Motion to AnimGraph Parameters

When you have *LocalPosition* and *LocalRotation* tracks for your *SkinnedModelRenderer*, you can generate AnimGraph parameter tracks based on that motion. Select the time range you want to generate the track data for, and select *Motion to AnimGraph Parameters* in the context menu.


[sbox-dev_kYGVfoQJLL.mp4 1298x1182](./images/a47dd92b-ac81-4bee-9467-0e911b8e2de3.png)

You can find the generated tracks nested under *Parameters* in the track list, and again they can be tweaked using keyframes or motion editing before moving to the next step.

### AnimGraph Parameters to Bones

If you want to have more fine-grained control over how your character moves, you'll need to bake its animation into bone tracks. As always, select the time range you want to bake, then select *AnimGraph Parameters to Bones* in the context menu. Now you're ready to move on to the [Manipulating Poses](#h-manipulating-poses) section.


[sbox-dev_jFi5J0teCg.mp4 1296x1184](./images/ac905bd6-630d-4660-86f1-752716715448.png)

## Recording Gameplay

Another way to generate initial bone track data is to record it in play mode. You'll just need to create tracks for the bones you want to record before you start. We've included a sub-track preset for the built-in player controller as an example.


[sbox-dev_Z1xCckpKEh.mp4 1936x1120](./images/4d03cac3-e077-41ce-910b-98b886dac308.png)

## Upgrading Legacy Bone Object Animations

Before we had dedicated bone track support, the best you could do was to enable *Create Bone Objects* on a *SkinnedModelRenderer* and add all the created objects to your movie. If you have an existing animation using that method, you can upgrade it to the new-style bone tracks with this context menu option. After doing the upgrade, you can manually delete the old tracks and disable *Create Bone Objects*.


[sbox-dev_B2C30JqFce.mp4 1298x558](./images/68a4c27f-a440-4e44-b37a-72d05a4100bb.png)

# Manipulating Poses

We have some basic tools to help you tweak how your characters are posed during your movie. This is fairly minimal currently, but should be enough to do things like layer upper body motion on top of a walk animation generated using the above methods.


:::tip
You should know the basics of [Motion Editing](/systems/movie-maker/motion-editing.md) before getting started here.

:::

## Moving Bones

First, select a time region in your movie that you want to animate a pose change for. Next, click and drag from a joint. We'll simulate an IK chain going from the dragged bone to the root to try to find a sensible pose. While dragging, you can press *Esc* to cancel. Press the green *Apply* button when you're happy to commit the change to your animation.


[sbox-dev_G5aoRHmoPS.mp4 1298x1058](./images/202557fd-518e-454a-8efc-bdc7fd546d47.png)

## Rotating Bones

When dragging a bone, you can hold the E key to start rotating it in place.


[sbox-dev_yGgPlUGxLg.mp4 1298x1056](./images/a8a3922c-d509-4643-82ce-fad56934e865.png)

## Locking Bones

Bones can be locked or unlocked in the context menu, or by holding *Shift* and clicking on them. This can be especially useful for things like finger posing by locking the hand.


[sbox-dev_5zV36pDo5G.mp4 1298x1056](./images/04e5b0f7-f5db-473b-99a7-59772524f674.png)


:::warning
Currently this will only animate correctly if you lock an ancestor of whichever bone you're manipulating. You can lock descendant bones like in the example below, but the lock is only considered for the current playhead time while posing.

:::


[sbox-dev_08lOzdxNjN.mp4 1300x1054](./images/7f1d612a-cf1e-477e-8630-ca7f0e44c25f.png)
