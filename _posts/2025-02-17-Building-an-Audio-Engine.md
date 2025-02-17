---
title: Building an Audio Engine
description: My Honours Project Journey
author: Jan
date: 2025-02-17
categories: [01. Audio Programming, Audio Engine Devlog]
tags: [game development, audio engine, honours, abertay, devlog, dsp, memory management]
---
🖥️ [View the GitHub Repository](https://github.com/JanHuss/newMaginengineAudio) | 🎮 [Check out my other projects](https://janhuss.github.io/categories/)

# Introduction

For my **honours project**, I set out to design and build an **audio engine for video games** 
with a focus on **memory allocation and efficiency**.

The project was inspired by [Rockstar’s RAGE Audio GDC talk](https://youtu.be/PqPaP_09Pwg?si=ztXVmpbTX-4Z7oDK), 
which first introduced me to the idea of **audio budgets** — an essential part of optimizing 
game audio. Throughout this journey, I aim to:

- **Understand the structure of an audio engine.**
- **Analyze how asset usage can stay within a given budget.**
- **Compare my implementation against industry-standard engines like FMOD and Wwise.**

This blog documents the **key milestones, research, and challenges** I faced while developing 
this system. The project is **still ongoing** and will be **updated over time**.

# Research & Project Proposal

Before development, I was required to submit a **project proposal**, detailing:

**What I am building** → An **audio engine optimized for CPU and memory efficiency**.
**Why this matters** → Audio optimization is a **key factor in game development**, and I wanted 
to **explore how to build an efficient system from the ground up**.
**How I would approach it** → Researching **audio engine architecture** and working with 
**existing libraries** to compare performance.

## Resources & Inspiration

To prepare, I explored multiple **books and talks** on game audio programming:

- **Game Audio Programmin**g (Guy Somberg – Vol. 1-4)
- **From Beep to Boom** (Simon Goodwin)
- **Game Engine Architecture** (Jason Gregory)

I also tested **different audio libraries**:

- **PortAudio** – Good for **loading data** but not ideal for real-time playback.
- **Miniaudio** – A lightweight **single-header** library supporting **multi-format playback**.

After gathering research, **I officially submitted my proposal**, marking the start of development.

# Feasibility Demo – Proving the Project’s Viability

The next major milestone was the **Feasibility Demo**, where I had to **prove that my project was 
achievable** by showcasing early progress.

## Required Deliverables:

- **A Gantt chart** outlining tasks until final submission.
- **Research question and project scope updates.**
- **A running application showing core functionality.**
- **A UML diagram and structural breakdown of the engine.**

### Gantt Chart

![Gantt Chart](/assets/img/UMLs/Gantt.png){: width="600" .w-5 .normal }<br>

### Structure Diagram

![Structure Diagram](/assets/img/UMLs/HonourStructureDiagramOld.png){: width="600" .w-5 .normal }<br>

### UML Diagram

![UML Diagram](/assets/img/UMLs/HonourUMLOld.png){: width="600" .w-5 .normal }<br>

# Technical Development & Key Changes

The initial development process involved **setting up a repository** and **experimenting with 
different audio playback systems**.

- Originally, I used **PortAudio for loading** and **Miniaudio for playback**, but I later 
**removed PortAudio entirely**.
- **Why?**
  1. Miniaudio could handle both **loading and playback**, simplifying the structure.
  2. It was easier to **understand one system deeply** rather than working with two.
  3. PortAudio’s **.lib file was causing major repository issues**, making cross-device work 
  frustrating.

After removing **PortAudio**, my **productivity and motivation improved**, allowing me to focus 
more on **developing the engine itself**.

# Final Thoughts & Future Plans

This project reinforced my **passion for audio programming** and **game engine development**.

Key takeaways:

- **Audio engine optimization** is **both an art and a science** — balancing performance, 
memory, and functionality.
- **There is still so much to explore** — I plan to **continue developing this engine beyond my 
honours year**.

**This is just the beginning of my journey into game audio engine development! More updates 
will follow as development continues.**
