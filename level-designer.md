# Level Designer

- All placable items (enemies and blocks) will inherit from BoardObject
- The board will have a name, and a width and height in terms of the number of grids, and all the board objects
- The grid will have reference to the object that occupies it. This is to enable O(1) lookup when choosing what to render in the window
- For objects that conform to `Movable`, there should be an interface to sets the trajectory of movement; for objects that conform to `Breakable`, there should be an interface to set the health; for objects that conforms to `Droppable`, there should be an interface to set the Collectible to drop
