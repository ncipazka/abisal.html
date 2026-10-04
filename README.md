# Abisal

A deep-sea survival shooter built with vanilla JavaScript and HTML5 Canvas. The whole game lives in a single HTML file with no dependencies and no build step.

You pilot a submarine on the ocean floor. Torpedoes fire automatically at the nearest enemy, so your job is to move, dodge, and choose upgrades that turn a fragile sub into a floating arsenal. Survive as long as you can and take down a boss every fifth wave.

## Play

Open `abisal.html` in any modern browser. That is all.

To serve it locally instead:

```bash
python3 -m http.server 8000
# then open http://localhost:8000/abisal.html
```

## Controls

| Action | Keyboard | Touch |
| --- | --- | --- |
| Move | `W` `A` `S` `D` or arrow keys | Drag anywhere on the screen |
| Dash (brief invulnerability) | `Space` | DASH button |
| Pause | `P` or `Esc` | none |
| Pick an upgrade | Click a card or press `1`, `2`, `3` | Tap a card |

Aiming and firing are automatic.

## Gameplay

- **Waves** last 30 seconds each, and enemy count, health, and speed scale up over time.
- **XP** drops as plankton when enemies die. Collect it to level up, then pick 1 of 3 random upgrades.
- **Bosses** appear every 5th wave. They fire rotating rings of projectiles and summon minions. Defeating one restores some HP and drops a large pile of XP.
- **Score** is based on kills and survival time. Your best score is saved in the browser's local storage.

### Enemies

| Enemy | Behavior |
| --- | --- |
| Minnow | Basic chaser |
| Eel | Fast and fragile |
| Crab | Slow, tanky, hits hard |
| Jelly | Keeps its distance and shoots at you |
| Trench Lord (boss) | Radial projectile bursts and minion summons |

### Upgrades

Sharp Torpedoes, Rapid Fire, Salvo (extra projectiles), Piercing Torpedoes, Turbo Propeller, Orbit Drones, Shockwave, Plankton Magnet, Steel Hull, Auto Repair, and Light Dash. Each one stacks up to a level cap.

## Project structure

```
abisal.html   # HTML, CSS, and JavaScript in one file
README.md
```

The main places to tweak the game inside `abisal.html`:

- `UP` – the list of upgrades, their descriptions, level caps, and effects
- `ED` – base stats for each enemy type
- `update()` – the main game loop logic (movement, spawning, collisions)
- `draw()` – rendering of the world and HUD

## Tech

- Vanilla JavaScript (ES6+)
- HTML5 Canvas 2D
- Google Fonts (Chakra Petch), with a system font fallback

## Ideas for the future

- Sound effects and music
- More weapons and enemy types
- Additional bosses
- Gamepad support

## License

Add a license of your choice (for example MIT) before publishing.
