# Pixel Paws — Architecture Notes

## Scope

Pixel Paws began as a browser puzzle prototype and evolved into a larger single-player game system with persistent progression and a separate development editor.

The public repository documents architecture and behavior without exposing the complete implementation.

## Main subsystems

### 1. Navigation and screens

The application manages multiple interface states instead of behaving like a single static page. The prototype includes:

- splash / loading;
- home;
- level selection;
- tutorial;
- daily rewards;
- shop;
- profile and statistics;
- achievements;
- settings;
- game screen;
- diagnostics;
- editor-related flows.

### 2. Game state

The game loop tracks:

- active level;
- cube/block state;
- available cats;
- waiting cats;
- conveyor slots;
- remaining ammunition;
- hints and boosters;
- elapsed time;
- level result.

State transitions are explicit so that the interface can redraw from the current model instead of relying only on visual DOM state.

### 3. Cube and hit logic

The engine evaluates which blocks are attackable, applies impacts, handles destruction and triggers special behavior where applicable.

Special block concepts explored in the editor include:

- reinforced blocks;
- protected blocks;
- chain reactions;
- wildcards;
- color-changing blocks;
- obstacles;
- layered blocks.

### 4. Queue and conveyor model

Cats move through a queue/conveyor model with a separate waiting area. This is one of the central strategy constraints: selecting the correct color is not enough; order and capacity also matter.

### 5. Persistence

The prototype keeps profile/progression state between sessions. The project also explored:

- validation of stored data;
- migration between save versions;
- backup behavior;
- import/export of profile or level data.

### 6. Progression systems

The broader prototype includes:

- coins;
- shop purchases;
- inventory/unlocks;
- level completion;
- records;
- achievements;
- statistics;
- daily rewards.

### 7. Development editor

A dedicated editor was built separately from the normal player flow. It supports:

- board sizing;
- cell editing;
- color selection;
- difficulty metadata;
- conveyor/capacity parameters;
- special block configuration;
- formations;
- structural validation;
- isolated playtesting;
- JSON import/export.

Keeping the editor separate from player progress avoids contaminating normal save data while testing experimental levels.

## Engineering choices

### Self-contained browser prototype

A major development branch was intentionally kept as a self-contained HTML/CSS/JavaScript application. This made the prototype portable and easy to test without a backend or build pipeline.

### Defensive state handling

The project gradually added validation and recovery logic around persistent data and custom-level input instead of trusting every stored or imported value.

### Progressive validation

Requirements were tracked as implemented, partial, pending or not applicable. This was deliberate: a feature being present in code does not automatically mean it has been validated across browsers, devices and accessibility configurations.

## Current limitations

The project should still be treated as a prototype rather than a production release. Important remaining work includes cross-device QA, performance profiling, broader accessibility validation, publication packaging and deeper testing of arbitrary custom-level combinations.
