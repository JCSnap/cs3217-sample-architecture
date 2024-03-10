# High Level Architecture

- Most are self explanatory (similar to the problem sets)
- `LevelManager` is the bridge between the level designer and the game, by converting the objects to game objects
- `Renderer` deals with what to render on the screen. If we do implement multiplayer with 2 different screens. The responsibility of what to render to each player falls under here. Thus it needs to be flexible enough to accomodate for that.
