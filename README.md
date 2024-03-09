# cs3217-sample-architecture
- Destroyable - effectWhenDestroyed will return an Effect, which is basically an action to perform by the game state. For instance, the effect could be to drop a coin (ask the game state to create a coin at the location of the object), or the effect could be to modify the environment etc.
- Collectable - similar in the sense that it will return an Effect, an action to perform by the game state. Eg. It can ask the game state to add one health to the player, or make the player invisible
- Jumpable - similar in the sense that it will return an Effect. Eg. it can modify its own state (eg. call the `takeDamage` function), or modify state in the game state
