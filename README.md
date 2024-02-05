# AI Game Playing in Ghost with Alpha-Beta Pruning

This project implements a solver for the game of Ghost using alpha-beta pruning. Ghost is a two-player word game where players take turns adding letters to a growing string, aiming to avoid completing a valid English word. The twist in our implementation is the addition of a scoring system that prioritizes winning quickly or delaying loss as long as possible.

## Overview

The game is played with the following rules:

- Players alternately append English letters to a growing string.
- The string must potentially form a word at each turn, but completing a word results in a loss for the current player.
- Our variation assigns a score based on the length of the word formed, with quicker wins or longer delays in losing being more favorable.

## Implementation

This project contains several key components:

- `MinimaxAgent`: Implements the Minimax algorithm to choose the optimal move from any game state.
- `AlphaBetaAgent`: Enhances the MinimaxAgent with alpha-beta pruning to reduce the number of nodes evaluated, making the agent more efficient.
- `RandomAgent`: Simulates an opponent that chooses moves randomly rather than strategically.
- `OptimizedAgainstRandomAgent`: Optimizes gameplay against an opponent that is playing randomly, aiming to maximize the expected value of the game's outcome.

### Features

- Utilizes alpha-beta pruning to efficiently evaluate game states.
- Includes a comprehensive game state class that manages the game's logic and progression.
- Offers an intuitive strategy against randomly playing opponents, balancing risk and potential gain.

## Usage

To run a simulation of the game, create a `GhostDictionary` from a list of valid English words, then instantiate and run a game with desired agents and starting conditions:

```python
from pset3 import *

dictionary = GhostDictionary("dictionary.txt")
prefix = "ou"
play_game(dictionary, prefix, 0, MinimaxAgent, MinimaxAgent)
