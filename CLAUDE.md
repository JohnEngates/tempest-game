# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a browser-based implementation of the classic arcade game Tempest using HTML5 Canvas and vanilla JavaScript.

## Running the Game

Open `index.html` in a web browser. No build process or dependencies required.

## Architecture

### Core Game Loop
- `tempest.js` contains all game logic in a single file
- Main game loop uses `requestAnimationFrame` for smooth 60fps rendering
- Game states: PLAYING, LEVEL_COMPLETE, WARPING, GAME_OVER

### Key Classes

**Game** - Main controller that manages:
- Game state and progression
- Enemy spawning with wave system
- Collision detection between projectiles, enemies, spikes, and player
- Level transitions and warping sequences

**Tube** - The geometric playfield:
- 16 segments forming a circular tunnel
- `getPosition(segment, depth)` returns coordinates in CENTER of segments
- Player sits BETWEEN segments on the rim, enemies travel UP segment centers

**Player** - The claw-shaped ship:
- Positioned between segment dividing lines, protects one segment
- Smooth movement interpolation with wrap-around handling
- Shoots projectiles down the center of protected segment

**Enemy Types**:
- Flippers: Spider-like, can change segments only at center
- Tankers: Split into 2 Flippers when destroyed
- Fuseballs: Jump between lanes, only vulnerable while jumping

**Spike** - Hazard trails left by enemies as they advance

### Critical Mechanics

1. **Positioning System**:
   - Segments are numbered 0-15
   - Player position is BETWEEN segments (e.g., between 0 and 1)
   - Enemies/projectiles travel in CENTER of segments
   - This is crucial for collision detection

2. **Wrap-Around Handling**:
   - Special logic for movement between segments 15 and 0
   - Angle calculations must handle the 0/360° boundary
   - See `updatePosition()` in Player class for implementation

3. **Visual Feedback**:
   - Active segment highlighted with yellow glow
   - Player flashes when invulnerable after hit
   - Screen flash on damage

## Common Issues and Solutions

**Visual glitches at wrap-around point**: Check angle calculations in Player's `updatePosition()` and `render()` methods. Ensure proper modulo arithmetic and 2π additions.

**Collision detection misses**: Remember player covers a segment, enemies are in segment centers. Player segment check should be exact match.

**Movement stuttering**: Verify `moveProgress` interpolation and `deltaTime` calculations.

## Game Controls
- Arrow Keys: Move left/right between segments
- Space: Shoot (hold for continuous fire, max 8 shots)
- Z: Superzapper (2 per level)
- R: Restart when game over