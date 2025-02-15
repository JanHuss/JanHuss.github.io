---
title: Rendering a Heightmap & Implementing Bloom Effects
description: A deep dive into shaders, lighting, and rendering techniques.
author: Jan
date: 2023-12-06
categories: [2. Programming, Graphics]
tags: [coursework, abertay, graphics, directx3d11, shaders, c++, renderdoc, nsight]
---

🖥️ [View the GitHub Repository](https://github.com/JanHuss/GraphicsProgrammingCoursework) | 🎮 [Check out my other projects](https://janhuss.github.io/categories/)

# Introduction

This might have been one of the **hardest things I’ve had to accomplish**, but it was also an 
incredibly **fun and rewarding challenge**.

For this coursework, I designed a **scene rendering system** featuring:
- **A heightmap-based terrain generator** using vertex manipulation.
- **A 3D drone model with dynamic lighting & shadow mapping.**
- **A bloom post-processing effect** with threshold-based brightness adjustments.

Everything was built using **shaders and custom rendering techniques** to create a visually 
compelling environment.

# Heightmap Terrain & Lighting System

The core of this project involved rendering a **plane that could be manipulated using a heightmap 
texture**. The heightmap, provided by the university, was used to:

- **Calculate vertex positions** based on pixel color values.
- **Generate mountainous terrain dynamically** within the scene.

Additionally, a **3D drone model** was rendered with its textures applied. Both the **heightmap 
and model** were affected by:

- **Two light sources** that dynamically illuminate the scene.
- **Two shadow maps**, passed into the **geometry shaders**, ensuring accurate shadow casting.

Within the **geometry shaders**, normals were calculated based on light positions, allowing for:

- **Realistic reflections** on illuminated surfaces.
- **Accurate shadow generation** where light does not reach.

# Shadow Mapping & Depth Pass

Before rendering the main scene, a **depth pass function** was executed. This:

- **Calculated shadows and depth values.**
- **Used light positions and directions** to determine where shadows should be cast.

Once depth values were established, the **scene pass function** was called, integrating **lighting, 
shadows, and reflections** to produce the final rendering.

# Bloom Post-Processing Effect

To enhance the scene’s visuals, I implemented a **bloom effect**, which adds a soft glow to 
bright areas. The process involved:

1. **Thresholding** – Determining how bright a pixel must be before bloom takes effect.
2. **Blurring** – Applying a **horizontal blur pass** followed by a **vertical blur pass**, 
creating a **Gaussian-like glow**.
3. **Final Pass** – Combining the blurred textures into the final rendered image, blending the 
bloom effect naturally into the scene.
This created a **cinematic lighting effect**, adding realism and depth to the rendering.

# Dear ImGui for Real-Time Debugging

To streamline development, I integrated **Dear ImGui**, which allowed for:

- **Adjusting heightmap values in real time.**
- **Modifying model positions, light positions, and colors dynamically.**
- **Toggling the bloom effect and fine-tuning its threshold and brightness.**

This significantly improved the workflow, making it easier to **test and tweak rendering 
settings efficiently**.

# Showcase Video

The video below **demonstrates the capabilities of the application**, showcasing how the 
heightmap terrain, lighting, and bloom effects function in real time.

{% include embed/youtube.html id='-fSZVPdDhi4' %}

# Final Thoughts

This project was an **intense but rewarding technical challenge**, giving me **hands-on experience 
with shaders, lighting systems, and post-processing effects**.


