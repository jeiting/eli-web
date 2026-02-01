# Retro Game — Breakout (Eli's Arcade)

## Goal
Add a playable Breakout/Arkanoid clone to the site. Full synthwave aesthetic, neon everything.

## File
`game.html` in the root directory.

## Design

### Visual Style
- Dark purple background (#0d0221) matching the site
- Neon cyan paddle with glow effect
- Neon pink ball with trailing glow
- Brick grid in alternating neon colors: cyan, pink, amber, purple
- Each row a different color — classic Breakout style
- Canvas-based rendering with glow effects (shadowBlur)
- Score display in Press Start 2P font, amber color
- Lives display (3 lives, shown as small circles or "💾" emojis)
- "GAME OVER" and "YOU WIN" screens with neon text

### Gameplay
- Standard Breakout rules: paddle at bottom, ball bounces, break all bricks
- Mouse AND keyboard controls (arrow keys or A/D)
- Ball speeds up slightly as bricks are destroyed
- 5 rows of 10 bricks
- 3 lives
- Score: 10 points per brick, bonus for clearing rows
- Start screen: "PRESS SPACE TO START" with blinking text
- Pause with Escape key

### Page Structure
- Same shared styling (link to style.css)
- Same nav: Home | Blog | Arcade (current)
- Same footer
- Game canvas centered on page, max 800x600
- Title: "ELI'S ARCADE" in big neon text above the canvas
- Score and lives displayed above the canvas
- Below canvas: brief instructions ("← → or Mouse to move | Space to launch | Esc to pause")
- Responsive: on mobile, canvas scales down, touch controls (tap left/right halves to move paddle)

### Audio (optional but cool)
- Simple Web Audio API beeps for:
  - Ball hitting paddle (low tone)
  - Ball hitting brick (higher tone, varies by row)
  - Ball lost (descending tone)
  - Game over (sad descending)
  - Win (ascending fanfare)
- Keep it simple — just oscillator beeps, no audio files needed
- Mute button in corner

### Fun Details
- Particle effects when bricks break (small neon sparks)
- Ball leaves a short trailing afterglow
- Paddle has subtle glow pulse
- CRT scanline overlay on the canvas (subtle)
- High score saved to localStorage

## Site Integration
- Add "Arcade" to nav links on ALL pages (index.html, blog.html, post template, hello-world post)
- Add an "Arcade" section to the homepage between Blog and Footer:
  - Small preview/teaser: "🕹️ Think you can beat my high score?"
  - Link to game.html
- Update style.css if needed for game-specific styles (or keep game CSS inline in game.html)

## Testing Checklist
- [ ] Game loads and shows start screen
- [ ] Space starts the game
- [ ] Paddle moves with mouse and keyboard
- [ ] Ball bounces off walls, paddle, and bricks
- [ ] Bricks break and score increases
- [ ] Ball resets when missed (life lost)
- [ ] Game over after 3 lives
- [ ] Win condition when all bricks cleared
- [ ] High score persists in localStorage
- [ ] Responsive on smaller screens
- [ ] Nav links work on all pages
