# Technical Architecture

## Overview

TrackGame should separate simulation, gameplay, presentation, and data.

The goal is to prevent the project from becoming dependent on the visual layer.

```text
Game
│
├── Simulation
│   ├── Race
│   ├── Athlete
│   ├── AI
│   └── Physics/Movement
│
├── Gameplay
│   ├── Career
│   ├── Training
│   ├── Meets
│   └── Progression
│
├── Character
│   ├── Appearance
│   ├── Animation
│   ├── Clothing
│   └── Equipment
│
├── Presentation
│   ├── Camera
│   ├── UI
│   ├── Audio
│   └── Commentary
│
└── Data
    ├── Athletes
    ├── Events
    ├── Meets
    ├── Equipment
    └── Sponsors
```

## Simulation

The simulation should determine what happens.

The visual systems should represent what happens.

This allows the simulation to eventually support:

* Real-time races
* Simulated races
* AI-vs-AI races
* Career results
* Training calculations
* Replay systems

## Athlete

An athlete should have persistent data separate from their visual character.

Conceptually:

```text
Athlete
├── Identity
├── Attributes
├── Career
├── Statistics
├── Appearance
├── Equipment
└── Personality/AI data
```

## Data-Driven Design

Values that are likely to change during development should not be hardcoded throughout the project.

Examples:

* Event distances
* Athlete attributes
* Fatigue rates
* AI strategies
* Equipment
* Meet types
* Training effects

## Testing

Core simulation systems should be testable without requiring the full game presentation.

For example:

```text
Given:
Athlete A has a specific speed/endurance profile.

When:
Athlete A runs an 800m simulation.

Then:
The resulting time should fall within an expected range.
```

Exact formulas will be developed and validated during prototyping.

## Unreal Engine

Unreal Engine 5 will handle:

* Rendering
* Characters
* Animation
* Input
* World
* UI
* Audio
* Game framework

C++ will be preferred for core systems where appropriate.

Blueprints will be used where they provide faster iteration or are better suited to visual/gameplay logic.
