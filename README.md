# Pixel Paws

A portfolio showcase for **Pixel Paws**, a browser-based color strategy puzzle built around cats, cube figures, a conveyor system, limited ammunition and waiting slots.

> This public repository is intentionally a **showcase**, not the complete source distribution. The full implementation and development files are kept in a private repository.

## What the project demonstrates

- Product and game-system design
- HTML, CSS and JavaScript prototyping
- State persistence and profile data
- Level progression and difficulty systems
- Virtual currency, shop and unlockable cosmetics
- Achievements, statistics and daily rewards
- Tutorial, pause/recovery and settings flows
- Custom level creation and validation
- Accessibility-oriented options such as reduced motion and visual differentiation

## Core gameplay idea

The player works through figures made from colored cubes. Cats of matching colors interact with the figure while the player manages:

- the order of available cats;
- ammunition/capacity;
- a conveyor belt;
- five waiting spaces;
- limited hints and boosters;
- level-specific block behaviors.

The prototype evolved beyond the basic game loop into a larger system with progression, persistence, custom levels and internal diagnostics.

## Architecture overview

```text
Pixel Paws
├── UI / navigation
│   ├── splash + home
│   ├── level selection
│   ├── tutorial
│   ├── shop
│   ├── profile + statistics
│   ├── achievements
│   └── settings
├── game engine
│   ├── cube state
│   ├── cat queue / waiting area
│   ├── conveyor processing
│   ├── shots / hits
│   ├── special block behavior
│   └── win / loss evaluation
├── progression
│   ├── coins
│   ├── rewards
│   ├── records
│   └── unlocks
├── persistence
│   ├── profile state
│   ├── save validation
│   └── import / export
└── development tools
    ├── level editor
    ├── structural validation
    └── isolated level testing
```

More detail: [docs/architecture.md](docs/architecture.md)

## Implementation highlights

The full prototype includes separate flows for home, levels, tutorial, daily rewards, shop, profile/statistics, achievements and settings. It also includes a custom-level editor and diagnostics screen.

The development editor supports creating and resizing boards, assigning colors and special block properties, defining formations, validating level structure, testing the level in isolation, and importing/exporting JSON.

## Validation and project status

A detailed internal requirements matrix was maintained during development. In the latest documented review, the prototype had a large implemented surface while still explicitly marking partial and pending areas instead of claiming full certification.

Examples of remaining validation work include:

- real-device QA;
- broader accessibility testing;
- arbitrary combinations of special blocks;
- deeper hint-safety analysis;
- packaging/publication-specific requirements.

## Public vs. private source

This repository intentionally contains documentation and portfolio evidence only. It does **not** publish the complete game, editor or original implementation logic.

The complete source is maintained privately and can be reviewed selectively for recruitment or technical evaluation when appropriate.

## Project ownership

Design, implementation direction and portfolio documentation by **Estefanía Iturrieta**.

All rights reserved unless explicitly stated otherwise.
