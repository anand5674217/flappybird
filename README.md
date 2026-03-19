# Flappy Bird Game

A Python-based implementation of the classic Flappy Bird game using Pygame, featuring animated sprites, collision detection, score tracking, and sound effects.

## Overview

This project recreates the popular Flappy Bird game where players control a bird character, navigating it through incoming pipes by flapping to stay airborne. The game includes smooth animations, collision detection, a scoring system with high score tracking, and authentic game sounds.

## Features

- 🐦 **Animated Bird Character**: Multi-frame animation with flying position variations
- 🌿 **Dynamic Obstacles**: Randomly positioned pipes with varying heights
- 🎨 **Visual Polish**: Scrolling background and floor for depth
- 🔊 **Sound Effects**: Wing flap, collision, and scoring sounds
- 📊 **Score System**: Real-time score display with high score tracking
- 🎮 **Smooth Physics**: Gravity-based bird movement with responsive controls
- 🔄 **Game States**: Main game and game-over states with restart capability

## Project Structure

```
flappybird/
├── FlappyBird.ipynb          # Main game implementation (Jupyter Notebook)
├── assets/                   # Game sprites and images
│   ├── background-day.png    # Game background
│   ├── background-night.png  # Alternative background
│   ├── base.png              # Floor/ground image
│   ├── bluebird-*.png        # Blue bird animation frames
│   ├── redbird-*.png         # Red bird animation frames
│   ├── yellowbird-*.png      # Yellow bird animation frames
│   ├── pipe-green.png        # Green pipe obstacles
│   ├── pipe-red.png          # Red pipe obstacles
│   ├── message.png           # Game over screen
│   └── gameover.png          # Additional game over assets
├── sound/                    # Audio effects
│   ├── sfx_wing.wav          # Flap sound
│   ├── sfx_hit.wav           # Collision/death sound
│   ├── sfx_point.wav         # Score sound
│   ├── sfx_die.wav           # Death effect
│   └── sfx_swooshing.wav     # Swoosh sound
├── 04B_19.ttf                # Game font
└── README.md                 # This file
```

## Requirements

- Python 3.6+
- Pygame library

## Installation

1. **Install Python** (if not already installed)
   - Download from [python.org](https://www.python.org)

2. **Clone the Repository**
   ```bash
   git clone https://github.com/anand5674217/flappybird.git
   cd flappybird
   ```

3. **Install Dependencies**
   ```bash
   pip install pygame
   ```

## How to Run

1. Open the Jupyter Notebook:
   ```bash
   jupyter notebook FlappyBird.ipynb
   ```

2. Run all cells in order:
   - Cell 1: Uncomment `pip install pygame` if pygame is not installed
   - Cell 2: Import required libraries
   - Cell 3: Execute the main game (will launch the game window)
   - Cell 4: Optional cleanup

Alternatively, if you convert the notebook to a Python script:
```bash
python FlappyBird.py
```

## How to Play

- **Start Game**: Press SPACE to begin
- **Flap/Jump**: Press SPACE to make the bird flap and move upward
- **Navigate**: Guide the bird through the pipes (gaps between upper and lower pipes)
- **Avoid**: Don't hit pipes, the floor, or go above the screen
- **Score**: Points increase as you successfully pass through each pipe
- **Game Over**: Collision triggers game over screen showing your score and high score
- **Restart**: Press SPACE on the game over screen to play again

## Game Mechanics

### Physics
- **Gravity**: Constant downward acceleration (0.25 pixels per frame²)
- **Flap**: Instantaneous upward velocity change of -12 pixels per frame
- **Bird Rotation**: Bird rotates based on movement direction (positive = downward rotation, negative = upward)

### Scoring
- Score increases continuously at 0.01 points per frame while playing
- A sound effect plays every 100 frames as confirmation
- High score is tracked and displayed at game over

### Collision Detection
- Bird collision with pipes triggers game over
- Bird collision with floor/ceiling triggers game over
- Safe zones exist only within the pipe gaps

### Pipe Generation
- Pipes spawn every 1,200 milliseconds
- Pipe heights are randomly selected from three preset levels
- Top pipe is always 300 pixels above the bottom pipe
- Pipes move leftward at 5 pixels per frame

## Game Elements

### Visual Assets
- **Bird**: Three-frame animation cycle for flapping effect
- **Pipes**: Symmetric obstacles with gaps for maneuvering
- **Background**: Scrolling parallax effect with floor tile
- **UI**: Score display during gameplay; score + high score on game over

### Audio
- **Wing Flap**: Plays when bird flaps
- **Hit Sound**: Plays on collision
- **Point Sound**: Plays periodically during gameplay
- **Death Sound**: Plays on game over

## Controls

| Key | Action |
|-----|--------|
| SPACE | Flap (when playing) / Start game / Restart after game over |
| ESC/Close Window | Quit game |

## Technical Details

### Screen Resolution
- **Display**: 576 × 1024 pixels
- **Scaled Assets**: All assets are scaled 2x for visibility
- **Frame Rate**: 120 FPS

### Key Functions
- `drawfloor()`: Renders scrolling floor tiles
- `create_pipe()`: Generates random pipe positions
- `move_pipes()`: Moves pipes leftward
- `draw_pipes()`: Renders pipes with correct orientation
- `check_collision()`: Detects collisions with obstacles
- `rotate_bird()`: Rotates bird based on current velocity
- `bird_animation()`: Cycles through bird frames
- `score_display()`: Renders score information

## Customization Options

You can modify the following parameters in Cell 3:

- `gravity`: Change falling speed (higher = faster fall)
- `pipe_height`: Modify available pipe positions
- `SPAWNPIPE` timer: Change pipe spawn frequency
- `bird_frames` images: Use different bird sprites
- `pipe_surface` image: Change pipe appearance
- `game_font` size: Adjust score display size
- Screen resolution in `py.display.set_mode()`

## Future Enhancements

Possible improvements to the game:
- Multiple bird character options
- Difficulty levels with variable gravity and pipe speed
- Leaderboard system
- Power-ups or obstacles
- Day/night mode toggle
- Mobile/touch controls
- Main menu screen

## License

This project is a personal implementation of the classic Flappy Bird game concept. 

## Credits

- Game concept: Dong Nguyen (Flappy Bird)
- Implementation: Anand
- Assets: Flappy Bird asset pack
- Sound effects: Standard game audio library

## Troubleshooting

**Game doesn't start**: Ensure all asset files (images and sounds) are in the correct directories
**No sound**: Check that `.wav` files are in the `sound/` folder; verify pygame mixer is initialized properly
**Choppy animation**: Increase clock tick value or verify your system can handle 120 FPS
**Notebook won't run**: Install Jupyter with `pip install jupyter` and ensure pygame is installed

---

**Note**: This is implemented in a Jupyter Notebook format, making it ideal for interactive development and learning. For production use, consider converting to a standalone Python script.
