# Garden Snake

Garden Snake is a polished remake of the classic Snake game with a forest-inspired visual style, animated Three.js background, particle effects, and a synthesized eat sound. The project is built with plain HTML, SCSS, and vanilla JavaScript modules, so it runs without a bundler.

## Tech Stack

- HTML, SCSS, and Vanilla JavaScript (ES modules)
- Three.js r128 for the animated background scene
- Web Audio API for the synthesized eat sound
- Google Fonts: Lora and DM Mono
- Font Awesome icons

## Features

- Day/night theme switching with smooth transitions
- Three difficulty levels: Easy, Medium, and Hard
- Per-level snake colors and score tracking
- Animated Three.js background with drifting spores and vine segments
- Particle effects for eating and game over
- Pulsing food and a glowing snake head
- Fading body segments that taper toward the tail
- Persistent high scores per level using localStorage
- Wall collision in Hard mode, edge teleport in Easy/Medium
- Keyboard, touch, and on-screen arrow controls
- Pause, resume, restart, and main menu flow
- Responsive layout designed for screens down to 480px

## Project Structure

```text
.
├── index.html
├── README.md
├── src/
│   ├── main.js
│   ├── controls/
│   │   ├── keyboard.js
│   │   ├── mobile.js
│   │   ├── snakeBoard.js
│   │   └── teleport.js
│   ├── game/
│   │   ├── food/
│   │   │   ├── create.js
│   │   │   └── draw.js
│   │   └── snake/
│   │       ├── draw.js
│   │       ├── eat.js
│   │       ├── isEat.js
│   │       └── move.js
│   ├── settings/
│   │   ├── index.js
│   │   ├── settingsUI.js
│   │   ├── levels/
│   │   │   ├── active.js
│   │   │   ├── checkWallCollision.js
│   │   │   ├── color.js
│   │   │   ├── data.js
│   │   │   ├── records.js
│   │   │   ├── recordScore.js
│   │   │   ├── storage.js
│   │   │   ├── unlocked.js
│   │   │   └── updateRecord.js
│   │   ├── sound/
│   │   │   ├── synth.js
│   │   │   └── toggle.js
│   │   └── theme/
│   │       └── mode.js
│   ├── state/
│   │   └── state.js
│   ├── three/
│   │   ├── background.js
│   │   └── icons3d.js
│   ├── ui/
│   │   ├── buttons.js
│   │   ├── eventsUI.js
│   │   ├── gameOver.js
│   │   ├── modals.js
│   │   ├── particles.js
│   │   ├── pause.js
│   │   └── restartGame.js
│   └── utils/
│       └── constants.js
├── styles/
│   ├── main.scss
│   ├── main.css
│   ├── base/
│   │   ├── _mixins.scss
│   │   └── _variables.scss
│   ├── images/
│   └── media/
│       ├── media.scss
│       └── media.css
└──
```

## Quick Start

1. Compile the stylesheets:

   ```bash
   npx sass styles/main.scss:styles/main.css styles/media/media.scss:styles/media/media.css
   ```

   Add `--watch` if you want automatic recompilation while editing styles.

2. Serve the project locally:

   ```bash
   npx serve .
   ```

3. Open the local URL in your browser.

## How to Play

- Use the arrow keys or the on-screen arrows to move the snake.
- Eat the apple to grow and increase your score.
- Avoid colliding with your own tail.
- In Hard mode, walls also end the game; Easy and Medium modes wrap around the board.
- Beat the per-level record to trigger the gold "New record!" message.

## Theme and Audio

- The top-bar icon toggles between dark and light mode.
- The volume button mutes the eat sound and saves that preference in localStorage.
- The eat sound is generated at runtime with the Web Audio API, so no audio file is required.

## Three.js Background

The background is loaded from a CDN as a global Three.js instance. The scene is rendered from [src/three/background.js](src/three/background.js) and stays behind the gameplay interface, so it never interferes with controls.

## Live Demo

https://snake-game-rouge-eta.vercel.app/
