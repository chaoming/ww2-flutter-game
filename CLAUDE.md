# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A Flutter-based WW2 turn-based strategy game featuring hexagonal map gameplay with diverse terrain and military units.

## Game Architecture

### Core Systems
- **Hex Grid Map** - Hexagonal tile system with 6-directional movement, terrain types (Plains, Forest, Hills, Mountains, City, River, Road, Beach, Sea), fog of war, and supply lines
- **Turn System** - Movement Phase → Combat Phase → Production Phase → End Turn
- **Combat System** - Simultaneous damage resolution with terrain modifiers, unit type advantages, and zone of control
- **Production/Economy** - Cities generate Production Points, factories/airfields produce units, infantry captures territories

### Unit Types
| Unit | Move | Range | Role |
|------|------|-------|------|
| Infantry | 3 | 1 | Captures cities, traverses all terrain |
| Tank | 5 | 1 | High attack, restricted terrain |
| Artillery | 2 | 2-4 | Indirect fire, no counter-attack |
| Fighter | 8 | 1 | Air superiority, intercepts bombers |
| Bomber | 6 | 1 | Strategic bombing |

### Key Mechanics
- HP system (10 HP per unit) with veterancy progression
- Terrain provides movement costs and defense bonuses
- Zone of control affects enemy movement
- Air units must return to airfields

## Flutter Path

Flutter is installed at: `/Users/chaomingli/Projects/flutter/bin/flutter`

## Build Commands

```bash
# Get dependencies
flutter pub get

# Run on device/emulator
flutter run

# Run tests
flutter test

# Run single test file
flutter test test/path/to/test_file.dart

# Build release APK
flutter build apk --release

# Build iOS
flutter build ios --release

# Analyze code
flutter analyze

# Format code
dart format .
```

## Project Structure (Planned)

```
lib/
├── main.dart
├── models/          # Game data models (Unit, Hex, Terrain, Player)
├── game/            # Game logic (combat, movement, AI)
├── widgets/         # UI components (hex grid, unit info, menus)
├── screens/         # Full screens (game, menu, settings)
├── services/        # Save/load, audio, network
└── utils/           # Hex math, constants, helpers
```

## Claude Code Configuration

### Skills (Auto-invoked)
- **flutter-test** - Run and analyze Flutter tests
- **hex-math** - Reference for hex grid algorithms (coordinates, neighbors, pathfinding)
- **game-balance** - Validate unit stats against requirements
- **issue-workflow** - Manage GitHub issues (start, complete, blockers)

### Subagents
- **code-reviewer** - Review Dart/Flutter code after implementing features
- **game-designer** - Validate game mechanics against GAME_REQUIREMENTS.md
- **ui-reviewer** - Review widgets for structure, accessibility, responsiveness

### Slash Commands
- `/issue <number>` - Load GitHub issue and plan implementation
- `/done [issue-number]` - Commit changes and optionally close issue
- `/balance` - Quick reference for unit stats and combat values

### Hooks
- Auto-format Dart files after Edit/Write operations

## Git Workflow

- Claude commits changes but does NOT push
- User handles `git push` manually

## Key References

- [GAME_REQUIREMENTS.md](GAME_REQUIREMENTS.md) - Detailed game design document with unit stats, terrain effects, and combat formulas
- [GitHub Project](https://github.com/users/chaoming/projects/3) - Roadmap and issue tracking
