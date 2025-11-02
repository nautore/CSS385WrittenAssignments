## Performance Concern 1 Large Number of Draw Calls
In a 2D game such as mine, GPU performance may be hindered if there are several different sprites or visual elements constantly being drawn to the screen. This can increase the load on the GPU which can decrease overall frames per second or lead to stuttering. 
### Mitigation Strategy
One mitigation strategy is to use sprite atlases or spritesheets to reduce the number of image files that must be opened or switched between. Another strategy is only rendering sprites that are visible on the screen which is known as culling. This will reduce the total number of assets that need to be drawn to the screen during gameplay. 
## Performance Concern 2 Object Management
In a 2D game, instantiating too many objects or frequently creating/deleting temporary objects can cause performance hitches during gameplay. 
### Mitigation Strategy
One mitigation strategy is reusing objects to reduce the number of times objects are created or deleted. This can be achieved through object pooling where frequently accessed objects such as projectiles, particles, or enemies are preinitialized and grouped together. 
## Performance Concern 3 AI Pathfinding 
In a 2D game, enemy AI make calculations to determine which direction they should go to attack the player. If several enemies are frequently making pathfinding calculations or are all making these calculations at the same time, CPU performance can be heavily impacted. This can result in dropped frames.
### Mitigation Strategy
One mitigation strategy is to space out pathfinding calculations across multiple frames so that not all enemies are updating their pathfinding at the same time. Additionally, reducing the rate at which pathfinding calculations are made can mitigate this issue. Enemy AI does not necessarily need to update their pathfinding every game frame, so adding a delay before recalculating the pathfinding can improve CPU performance.
## Implementing these Strategies
In my game, I have already implemented some of these strategies, but I plan to include more as development progresses. For example, I already use spritesheets to store animations for the player and enemies. This is an easy way to reduce GPU load. Right now, enemy AI performs pathfinding calculations every frame. However, I plan to include a lot of enemies on the screen at the same time, so I will have to reduce the rate at which these updates occur or maybe space them out across multiple frames. I will also make sure to reuse objects when possible and reduce the number of temporary objects being instantiated or deleted.
