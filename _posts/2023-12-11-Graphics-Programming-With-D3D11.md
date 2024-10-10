---
title: Graphics Programming with Directx3D11 using shaders
description: A proper jump into graphics programming
author: Jan
date: 2023-12-06
categories: [2. PROGRAMMING, GRAPHICS]
tags: [coursework, abertay, graphics, directx3d11, shaders, c++, renderdoc, nsight]
---

This might have been one of the hardest things I had to accomplish, but it was so much fun!

For this coursework I designed a scene rendering a plane that can be vertex manipulated utilising a heightmap texture, provided by the university, and shaders that calculates the vertices based on the pixel colour to generate mountains. 
A drone model with its texture is also rendered to the scene. Both heightmap and model have two lights and two shadow maps being passed into the geometry shaders. The function to render geometry is named scene pass. Within the geometry shaders, normals are calculated based on the light positions to generate reflections wherever the light hits a surface. Wherever the light does not hit a surface, shadows will be generated which have been calculated within the depthpass function. 
Before the scene pass function, a depth pass function is called which calculates the shadows and their depth. It has a similar functionality to the scene pass, however shadow map calculations are based on the light positions and directions within the rendered world rather than the world positions.
The scene also has the functionality of turning on a bloom post production effect. The threshold function determines how bright a pixel has to be until bloom takes effect. Once the threshold and brightness values are determined, a horizontal blur effect will be applied followed by a vertical blur creating a bleed-like or gaussian effect on the rendered frame.
The bloom effect function is taking both horizontal and vertical images and blending them into one texture. Lastly, the texture is passed into a final pass function which renders the world with this blurred effect.

To help with the development of this application, Dear ImGui was utilised to help with changing values for the heightmap, model positions, light positions, light directions, light colours, toggling the post production effect on and setting the bloom threshold and brightness values.

You can find the video presentation on the project below:<br>

{% include embed/youtube.html id='-fSZVPdDhi4' %}
