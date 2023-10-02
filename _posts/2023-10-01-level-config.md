---
title: Level Configuration 
date: 2023-10-01 10:00:00 -0500
categories: [Unreal Engine, General Topics]
img_path: /assets/img/2023-10-01-level-config.md
---

## Introduction

This post talks about how to configure an empty level in Unreal Engine.

## Landscape

Go to the Landscape mode configuration (```Shift + 2```) and then click on the ```Create``` button:

![Landscape config](landscape_config.png){: w="600" h="300" }

## Lighting

Add a ```Directional Light```:

![Directional Light](directional_light.png){: w="600" h="300" }

Select the Directional Light and mark it as ```Movable``` (for your scene to have 100% dynamic lighting).

Add the Sky Atmosphere:

![Sky](sky.png){: w="600" h="300" }

Add the Exponential Height Fog:

![Exponential Height Fog](exponential_height_fog.png){: w="600" h="300" }

Add the Sky Light:

![Sky Light](sky_light.png){: w="600" h="300" }

Select the Sky Light and mark it as ```Movable``` (for your scene to have 100% dynamic lighting):

![Sky Light Movable](sky_light_movable.png){: w="600" h="300" }

Also, while having the Sky Light selected, mark the option ```Light -> Real Time Capture``` because we are using Sky Atmosphere.

> To avoid having the red message "Lights needs to be rebuild", Go to the ```World Settings``` and mark the option ```Lightmass -> Advanced -> Force No Precomputed Lighting: true```. Then go to the menu ```Build -> Build All Levels```.
{: .prompt-info }

## Landscape Material

When you add a material to the landscape:

![Landscape Material](landscape_material.png){: w="600" h="300" }

you may get something like this:

![No Landscape Material](no_material_landscape.png){: w="600" h="300" }

And the reason is that the landscape paint layer has no layer info assigned yet:

![Landscape Paint](landscape_paint.png){: w="300" h="600" }

Select the second entry in the Layer and add it as a Weight-blended layer (normal):

![Landscape Paint Layer Info](layer_info_dirt.png){: w="300" h="600" }

and save it into the default folder:

![Landscape Paint Layer Save](landscape_paint_save.png){: w="300" h="600" }





