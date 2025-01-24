# Sokoban Warehouse Game (Assembly Implementation)

## Overview
The Sokoban Warehouse Game is implemented in Assembly language for an 8x8 LED matrix-based environment. The game features player-controlled movement to push a box onto a designated target while avoiding obstacles such as walls. The implementation includes multiplayer support and an improved random number generator. 

* I have included the official documentation in a pdf format in this repo.

## License
The project repsitory is not public according to the Academic Conduct of UofT, for access to the private repo email me at hj.shah@mail.utoronto.ca

## Features

### 1. Multiplayer Mode
- **Turn-based Gameplay:**
  - The game supports multiple players, each taking turns to solve the puzzle.
  - The stack pointer is used to store each player's score.
  - Once all players complete their turns, the program displays the leaderboard.
- **Restart Mechanism:**
  - Players can restart their levels without affecting others.
  - The game continues for the remaining players after a restart.

### 2. Improved Random Number Generator
- **Linear Congruential Generation (LCG):**
  - The seed value is initialized using the lower 32 bits of the elapsed time since epoch.
  - The number is multiplied by 13 and incremented by 167, then taken modulus 33967.
  - The result ensures a long sequence period and avoids repetition.
  - The final position is determined using remainder division by 6 to avoid placing objects on walls.

### 3. Game Mechanics
- **Grid Setup:**
  - The game environment is displayed on an 8x8 LED matrix.
  - Walls are placed around the edges to create boundaries.
  - The player, box, and target are initialized at random positions, ensuring solvability.
- **User Interaction:**
  - Movement via D-pad controls (up, down, left, right).
  - Collision detection prevents movement through walls.
  - Box placement logic ensures the target is reached correctly.
- **Winning Condition:**
  - The game is won when the box is placed exactly on the target.
  - The system displays congratulatory messages and updates scores.

## Controls
- **D-pad Inputs:**
  - `UP (0)`: Move the player up.
  - `DOWN (1)`: Move the player down.
  - `LEFT (2)`: Move the player left.
  - `RIGHT (3)`: Move the player right.

## Installation
1. Import the code into RISC-V 
2. Set the appropriate settings for the LED and D-Pad modules
3. Run the executable

## Usage
1. The game prompts the user to enter the number of players.
2. Players take turns to complete the objective of moving the box to the target.
3. The program keeps track of scores and prints the leaderboard at the end.

## Implementation Details
- **Assembly Features Used:**
  - Stack-based player management.
  - LED matrix manipulation using calculated offsets.
  - Efficient polling of D-pad inputs.
  - Randomized initial placement of game elements.


## Contributors
- Hardik Shah

