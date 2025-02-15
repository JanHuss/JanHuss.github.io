---
title: Building a Final Fantasy-Inspired Turn-Based Combat System
description: An initial dive into gameplay mechanics using Unreal Engine
author: Jan
date: 2023-12-11
categories: [2. Programming, Gameplay Mechanics]
tags: [coursework, abertay, c++, unreal engine, blueprints, conversion]
---

🖥️ [View the GitHub Repository](https://github.com/JanHuss/GameplayMechanics) | 🎮 [Check out my other projects](https://janhuss.github.io/categories/)

# Video Demonstration

The video below provides a **narrated walkthrough** of the combat system, explaining the 
**action timer mechanics, turn-based combat flow, and attack execution** in real time.

{% include embed/youtube.html id='DMTATTaozkw' %}

# Introduction

For my coursework, I chose to develop a **turn-based combat system** inspired by **Final Fantasy’s 
Active Time Battle (ATB) system**. As a longtime fan of **turn-based RPGs**, I wanted to 
experiment with an **action timer mechanic** and analyze its effectiveness in gameplay.

The system was originally built in **Unreal Engine blueprints** using a [tutorial by Ryan Laley](https://www.youtube.com/playlist?list=PL4G2bSPE_8une98EVjO89lJTkxJDVz217), 
then fully converted into **C++** to enhance modularity and efficiency. This project was an 
opportunity to **gain deeper insights into turn-based mechanics** and explore the **challenges of 
implementing a structured combat loop.**

# Gameplay Overview

The system features a **three-player party vs. three-enemy battle setup**, where each 
character has:

- **An action timer** that fills up based on their **speed stat**.
- **A command menu** for **attacking, using items (planned), or running (planned).**
- **A targeting system** where players choose an enemy before executing an action.

Once a character’s **action timer fills**, they take their turn. Enemies also attack when 
their own timers are ready, meaning battles are **not strictly turn-based but instead dynamic**.

## How the Combat System Works:

1. **Speed-Based Turn Order** – All characters are sorted into an **initiative queue** based on 
their speed stat.
2. **Action Timers** – Each character’s action timer fills up over time.
3. **Executing Commands** – When ready, the player selects an attack and chooses a target.
4. **Stat-Based Combat Calculations** – Attack damage is determined by a formula that factors 
in **strength, endurance, and a randomized modifier**.
5. **Animations & Feedback** – Attacks trigger **animations, damage calculations, and hit 
reactions**.
6. **Round Progression** – Turns cycle through the queue until all characters have acted, 
then the next round begins.

This system introduces **strategic depth**, as **enemies can attack at any time**, forcing 
players to react quickly and plan their moves efficiently.

# Technical Development

The project was built using **Unreal Engine 5**, incorporating a mix of **C++ classes and 
blueprints**.

## Key C++ Components:

- **BattleGameMode** – Manages combat flow, turn order, and player/enemy data.
- **BaseUnit (Player & Enemy)** – Defines **character stats, health, and combat logic**.
- **CombatManager** – The **core battle system**, handling **speed calculations, action timers, 
attack execution, and damage calculations**.
- **HUD & UI Widgets** – Displays **action timers, player health, and target selection menus**.

## Challenges & Solutions:
- **Blueprint-to-C++ Conversion** – Initially developed in **blueprints**, then rewritten in 
**C++** to improve scalability and performance.
- **Stat Calculation Complexity** – Balancing **strength, endurance, and speed mechanics** 
required multiple iterations to create a **fair combat system**.
- **UI Interactions** – Implementing a **clean, intuitive menu system** for turn selection.

# Final Thoughts

This project was an **incredible learning experience** that deepened my understanding of:
- **Turn-based combat mechanics** and how to structure **gameplay loops**.
- **C++ programming in Unreal Engine** and blueprint-to-code conversion.
- **Balancing character stats and enemy AI logic.**

While I originally planned to include **items, buffs, and debuffs**, time constraints required 
me to **prioritize the core combat system**. However, I plan to **expand on this system in the 
future**, refining its mechanics and adding more strategic depth.

**This was a challenging but rewarding project, and I’m excited to push my Unreal Engine 
development skills even further!**
