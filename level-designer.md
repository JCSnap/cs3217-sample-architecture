# Level Designer

- All placable items (enemies and blocks) will inherit from BoardObject
- The board will have a name, and a width and height in terms of the number of grids, and all the board objects
- The grid will have reference to the object that occupies it. This is to enable O(1) lookup when choosing what to render in the window
