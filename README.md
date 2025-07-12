# Tempest

A browser-based implementation of the classic 1981 arcade game Tempest, built with HTML5 Canvas and vanilla JavaScript.

## 🎮 Play Now

Open `index.html` in any modern web browser to play. No installation or build process required!

## 🕹️ Controls

- **Arrow Keys** - Move left/right between segments
- **Space** - Shoot (hold for continuous fire, max 8 shots)
- **Z** - Superzapper (2 per level)
- **R** - Restart when game over

## 🎯 Gameplay

Navigate your claw-shaped ship around the rim of a geometric tube, defending against enemies crawling up from the depths:

### Enemies
- **Flippers** (Purple) - Spider-like creatures that change lanes at the tube's center
- **Tankers** (Cyan) - Split into two Flippers when destroyed
- **Fuseballs** (White) - Jump between lanes, only vulnerable while jumping

### Features
- Progressive difficulty with more enemies each level
- Spike hazards left by advancing enemies
- Superzapper clears all enemies on screen
- Smooth movement with wrap-around at segment boundaries
- Classic vector-style graphics with modern effects

## 🛠️ Technical Details

- Pure vanilla JavaScript - no frameworks or dependencies
- HTML5 Canvas for rendering
- 60fps game loop using `requestAnimationFrame`
- Modular class-based architecture
- Responsive vector graphics that scale with canvas size

## 📁 Project Structure

```
tempest/
├── index.html      # Game HTML with UI elements
├── tempest.js      # Complete game logic and rendering
├── README.md       # This file
└── CLAUDE.md       # Developer documentation
```

## 🚀 Development

The game runs directly from the filesystem - just edit and refresh! Key classes:

- `Game` - Main game controller and state management
- `Tube` - The geometric playfield
- `Player` - Ship movement and shooting
- `Enemy` - Base enemy behaviors
- `Spike` - Hazard trails
- `Projectile` - Player bullets

See `CLAUDE.md` for detailed architecture notes and common issues.

## 📜 License

This is a fan recreation for educational purposes. Tempest is a trademark of Atari, Inc.