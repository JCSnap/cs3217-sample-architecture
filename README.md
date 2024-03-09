# cs3217-sample-architecture
## Game
- `Effectable` - When conformed, a function that takes in the game state and returns an `Effect` should be implemented. An `Effect` is a lazy executable that can modify states (either its own state or the game state).
- `Destroyable` - When destroyed, the effect function will be called, which returns an Effect, which is basically an action to perform by the game state. For instance, the effect could be to drop a coin (ask the game state to create a coin at the location of the object), or the effect could be to modify the environment etc. Game objects can choose whether or not they want to conform to `Destroyable`
- `Collectable` - similar in the sense that it will return an Effect, an action to perform by the game state. Eg. It can ask the game state to add one health to the player, or make the player invisible
- `Collidable` - similar in the sense that it will return an Effect. It can be general collision, or collision on a specific side (eg. top for objects being jumped on). Bouncable blocks can implement the collision on specific side function to make player bounce when collide with top, hidden blocks can implement the collision on specific side function to disable collision for bottom. Enemies can implement collision on specific side to make it take damage when it is being jumped on (or collided on top). The effect can modify its own state (eg. call the `takeDamage` function), or modify state in the game state
- `GameObjectBehaviour` - all game objects (enemies and blocks) conform to this protocol. The `action` function is called at every tick, which modifies the state of the object. Eg. For spikes, the action would be to toggle the spike position every tick to up and down. For other enemies, the action could be to shoot pellets, or call the `move` function. Likewise, movable platforms' action would be to call the `move` function
- `Player` - Like `Enemy` and `Block`, it conforms to `GameObjectBehaviour`. It also has additional properties like "health", "lives", or even "Power"
- `Power` - conforms to `Effectable`, which can modify game state when called. This allows extensions such as modifying the game environment, shooting pellets etc.

## Physics
- `PhysicsObject` - contains the properties required for physics objects regardless of shape (eg. center, mass, velocity....). Physics engine of specific shape will have to conform to this.

