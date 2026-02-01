# Retro Game #2 — Asteroids (Eli's Arcade)

## Goal
Add a playable Asteroids clone to the site. Same synthwave/neon aesthetic as the Breakout game. Vector-style graphics with glowing neon lines.

## File
`asteroids.html` in the root directory (same pattern as `game.html`).

## Design

### Visual Style
- Dark purple background (#0d0221) matching the site
- **Vector-style rendering** — all objects drawn as glowing neon outlines (no fills)
- Ship: neon cyan wireframe triangle with engine thrust glow
- Asteroids: irregular polygon outlines in neon purple/pink, subtle rotation
- Bullets: small bright amber dots with short trailing glow
- Explosions: wireframe fragments that scatter and fade (like the original)
- All lines have shadowBlur glow effects matching the synthwave palette
- Score/lives in Press Start 2P font, amber color
- CRT scanline overlay on the canvas (subtle, matching Breakout)

### Color Palette (match existing site)
- Background: #0d0221
- Ship/UI: cyan (#00f0ff)
- Asteroids: pink (#ff2975) and purple (#b537f2)
- Bullets: amber (#ffb700)
- Explosions: mix of all colors
- Text: amber (#ffb700)

### Gameplay
- Classic Asteroids rules:
  - Ship in center, rotates and thrusts (momentum/inertia physics)
  - Screen wrapping on all edges (objects reappear on opposite side)
  - Shoot to break asteroids: large → 2 medium → 2 small → destroyed
  - UFO/saucer appears occasionally (bonus points, shoots back)
- Controls:
  - Arrow keys: Left/Right rotate, Up thrust, Down or Shift for hyperspace (random teleport)
  - Space: shoot
  - WASD alternative: A/D rotate, W thrust, S hyperspace
  - Escape: pause
- Scoring:
  - Large asteroid: 20 pts
  - Medium asteroid: 50 pts
  - Small asteroid: 100 pts
  - UFO: 200 pts (large), 500 pts (small)
- 3 lives (displayed as small ship icons or 💾 emojis)
- Extra life every 10,000 points
- Difficulty increases each wave (more asteroids, faster UFOs)
- High score saved to localStorage

### Physics
- Ship has momentum — thrust adds velocity, no friction (space!)
- Slight drag factor (0.99x per frame) so ship eventually slows — keeps it playable
- Asteroids drift at constant speed with slight rotation
- Bullet speed is absolute (not additive with ship velocity)
- Collision detection: point-in-polygon or circle approximation

### Page Structure
- Same shared styling (link to style.css)
- Same nav: Home | Blog | Arcade (with sub-links to both games)
- Same footer
- Game canvas centered on page, 800x600 max
- Title: "ELI'S ARCADE — ASTEROIDS" in neon text above canvas
- Score, lives, and wave number displayed above canvas
- Below canvas: controls help text
- Responsive: scale canvas on mobile, touch controls (virtual joystick or tap zones)

### Audio (Web Audio API — no files)
- Oscillator beeps:
  - Thrust: low rumble/hum while held
  - Shoot: short high blip
  - Asteroid break: crunchy noise (short noise burst)
  - Ship death: descending warble
  - UFO: classic alternating two-tone (high/low oscillating)
  - Extra life: ascending arpeggio
- Mute button in corner (same as Breakout)

### Fun Details
- Engine flame effect when thrusting (flickering triangle behind ship)
- Ship blinks during respawn invulnerability (2 seconds)
- Asteroid fragments scatter as small line segments on destruction
- Subtle star field in background (tiny static dots)
- Screen flash on ship death
- Wave clear: brief "WAVE X" text with neon pulse

## Site Integration
- Update the Arcade section on index.html to show both games:
  - Breakout link → game.html
  - Asteroids link → asteroids.html  
  - Keep the teaser text engaging
- Update nav on ALL pages: "Arcade" should work as before (links to index.html#arcade or a game listing)
- Do NOT modify game.html (Breakout) — leave it exactly as is

## Testing Checklist
- [ ] Game loads with start screen ("PRESS SPACE TO START")
- [ ] Ship rotates, thrusts, and drifts with momentum
- [ ] Screen wrapping works for ship, asteroids, and bullets
- [ ] Asteroids break into smaller pieces correctly
- [ ] Collision detection works (ship + asteroids, bullets + asteroids)
- [ ] Score tracks correctly
- [ ] Lives decrease on death, game over at 0
- [ ] UFO appears and shoots
- [ ] Wave progression increases difficulty
- [ ] High score persists in localStorage
- [ ] Audio works and mute button toggles
- [ ] Responsive on smaller screens
- [ ] Nav links correct on all pages
