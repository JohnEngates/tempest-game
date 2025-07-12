# Tempest Arcade Authenticity Roadmap

This roadmap outlines improvements to make the game more faithful to the original 1981 Atari Tempest arcade game.

## Phase 1: Core Mechanics (Quick Wins)

### 1.1 Superzapper Fix ✓ High Priority
- [ ] Change from 2 full zaps to 1 full + 1 partial zap per level
- [ ] Full zap: Kills all enemies (not spikes)
- [ ] Partial zap: Kills one enemy (prioritize threats like Fuseballs near rim)
- [ ] Update UI to show zapper state clearly

### 1.2 Movement System
- [ ] Convert from discrete segment jumps to continuous rotation
- [ ] Make segment a float value for smooth analog-style movement
- [ ] Add rotation speed control (faster when held)
- [ ] Consider gamepad support for spinner emulation

### 1.3 Scoring Authenticity
- [ ] Flippers: 150-300 points (random)
- [ ] Tankers: 100 points
- [ ] Fuseballs: 200-700 points (random)
- [ ] Spikers: 50 points per hit
- [ ] Bonus life every 20,000 points
- [ ] Implement high score table with localStorage

## Phase 2: Level Shapes and Progression

### 2.1 Web Shape System
- [ ] Implement 16 unique web shapes (not just circles):
  - Circle (16 segments)
  - Square (4 segments)
  - Plus/Cross
  - Bowtie/Figure-8
  - Flat line (open ends)
  - Triangle
  - Star
  - V-shape
  - Infinity symbol
  - Others...
- [ ] Cycle through shapes every 16 levels
- [ ] Color progression: Blue (1-16), Yellow (17-32), Red (33-48), Green (49-64), Invisible (65-80)

### 2.2 Level Selection
- [ ] Start screen with level selection (1, 3, 5, 7, 9, 11...)
- [ ] Save max reached level in localStorage

## Phase 3: Enemy Behaviors

### 3.1 Fix Existing Enemies
- [ ] **Flippers**: Add lane-flipping behavior to chase player
- [ ] **Fuseballs**: Move along edges (not center), invulnerable except when crossing lanes
- [ ] **Tankers**: Ensure they leave spikes properly

### 3.2 Add Missing Enemy Types
- [ ] **Spikers**: Spiral movement, always leave spikes, multi-hit destruction
- [ ] **Pulsars**: Zig-zag movement, periodically electrify their lane
- [ ] **(Bonus) Sparx**: Rim crawlers that chase the player

### 3.3 Wave System
- [ ] Spawn enemies in waves from bottom
- [ ] Level-specific enemy mixes (e.g., Pulsars from level 5+)
- [ ] Progressive difficulty with speed multipliers

## Phase 4: Audio System

### 4.1 Sound Effects
- [ ] Shooting sound (high beep)
- [ ] Enemy destruction (explosion)
- [ ] Superzapper (distinctive zap)
- [ ] Player hit (alarm sound)
- [ ] Level complete (ascending tones)
- [ ] Warp sequence sounds

### 4.2 Implementation
- [ ] Use Web Audio API for retro synthesis
- [ ] Optional: Load authentic arcade samples

## Phase 5: Visual Polish

### 5.1 Vector Graphics Style
- [ ] Remove filled shapes, use glowing strokes only
- [ ] Add bloom/glow effects
- [ ] Implement CRT scanline effect (optional toggle)
- [ ] Particle trails for projectiles

### 5.2 UI Improvements
- [ ] Attract mode demo
- [ ] Pause functionality (P key)
- [ ] Game over ranking display
- [ ] Credits screen

## Phase 6: Modern Enhancements

### 6.1 Controls
- [ ] Gamepad API support
- [ ] Touch controls for mobile
- [ ] Customizable key bindings

### 6.2 Accessibility
- [ ] Colorblind mode options
- [ ] Screen reader support for UI
- [ ] Adjustable game speed

### 6.3 Performance
- [ ] Optimize rendering for 60fps on all devices
- [ ] Dynamic canvas scaling
- [ ] Efficient collision detection

## Implementation Priority

1. **Essential for Authenticity** (Do First):
   - Superzapper fix
   - Continuous movement
   - Basic web shapes (at least 4-5)
   - Fix enemy behaviors
   - Basic audio

2. **Major Impact** (Do Second):
   - All 16 web shapes
   - Missing enemy types
   - Complete audio system
   - Vector visual style

3. **Polish** (Do Last):
   - Modern enhancements
   - Accessibility features
   - Advanced visual effects

## Resources
- MAME emulator for reference gameplay
- Original arcade manual for scoring/mechanics
- YouTube gameplay videos for enemy patterns
- Atari Age forums for technical details