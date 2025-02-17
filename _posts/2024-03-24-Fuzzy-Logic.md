---
title: Exploring Fuzzy Logic for AI Decision-Making
description: Testing fuzzy logic for real-time AI behavior.
author: Jan
date: 2024-03-24
categories: [University Work]
tags: [coursework, abertay, ai, fuzzy, logic, c#]
---

🖥️ [View the GitHub Repository](https://github.com/JanHuss/FuzzyLogic) |🎮 [Check out my other projects](https://janhuss.github.io/categories/)

# Video Demonstrations

The following videos showcase the **presentation of this project** and a **demonstration of how 
fuzzy logic performs under different rule sets**.

## Presentation Video

{% include embed/youtube.html id='AIt1J4jxDxw' %}

## Fuzzy Logic AI Test Results

{% include embed/youtube.html id='O1OvdUCsCbo' %}

# Introduction

For this project, I implemented **fuzzy logic AI** in a **Unity-based simulation**, where a 
**green car avoids obstacles (red cars) and collects items (purple coins)**.

Fuzzy logic is often underutilized in game development but has been seen in **RTS games** for 
opposition reaction systems. The goal of this coursework was to **evaluate how “accurate” fuzzy 
logic can be in real-time AI decision-making**.

# Why Fuzzy Logic?

Fuzzy logic operates on a **scale between 0 (false) and 1 (true)** rather than strict binary 
decisions. This allows **for more nuanced AI behavior** by assessing inputs as degrees of truth 
rather than fixed values.

I was particularly interested in:
- **How “fuzzy” decisions impact AI movement.**
- **How adding more rules affects AI accuracy.**
- **How well fuzzy logic can handle dynamic decision-making in games.**

# Implementation & AI Behavior

The **fuzzy logic system** was integrated into a **green car game object**, controlling its 
movement based on the positions of **red cars (obstacles) and purple coins (collectibles)**.

## Inputs Used in the System:
1. **redCarDirection** – Determines if the green car is **left, right, or centered** relative 
to an obstacle.
2. **redCarApproach** – Measures how **far or close** the car is to an obstacle.
3. **itemDirection** – Determines if the green car is **left, right, or centered** relative to a 
collectible.
4. **itemApproach** – Measures how **far or close** the car is to a collectible.

These inputs were processed using the **Fuzzy Logic Library provided in the CMP304 Unity Lab**.

# Defining AI Rules & Testing Scenarios

To test how fuzzy logic affects decision-making, I created **multiple rule sets**:

## Phase One – Arbitrary Values (Baseline)

- Initial logic rules applied without optimization.
- AI behavior was unpredictable and inconsistent.

## Phase Two – Improved Input Values
- Adjusted input peaks to **better distinguish object distances**.
- AI exhibited more **controlled movement** but still had inconsistencies.

## Phase Three – Improved Output Values

- Optimized defuzzification for **smoother AI transitions**.
- AI **improved in avoiding obstacles** and **targeting collectibles more efficiently**.

### Testing Different Rule Sets:

- **14 Rules**: Limited decision-making capability.
- **120 Rules**: More refined decision-making, but with diminishing returns.


**Key Takeaway:** More rules **did not always lead to better performance** in this application.

# Results & Observations

- **Fuzzy logic was precise but not always effective.**
- AI performed better when **objects were farther away**, giving it more time to react.
- **More rules didn’t necessarily improve decision-making** — in some cases, it overcomplicated 
the process.
- The best configuration was **Phase Two**, where input peaks were adjusted to reduce unnecessary collisions.

## What Can We Learn from This?

- **Adjusting input peaks directly affects reaction speed.**
- **Too many rules can reduce efficiency instead of improving accuracy.**
- **Fuzzy logic works well for AI movement but isn’t always the best choice for fast-paced 
reaction-based decisions.**

# Final Thoughts

This project provided **valuable insights into AI decision-making** and how **fuzzy logic can be 
used in game development**. While it has **strengths in nuanced behavior**, it also requires 
**careful tuning to avoid overcomplicating AI logic**.

**This was an exciting experiment, and I look forward to further exploring AI-driven 
decision-making in games!**
