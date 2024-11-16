# [Animation Blueprint System in Unreal Engine 5]



Bora Tibet Ozdemir

2221180

## Research

Animation systems are an essential part of game development, allowing characters to move fluidly and respond dynamically to player input. Unreal Engine 5's Animation Blueprint system offers a robust framework to manage animations, blend them seamlessly, and achieve complex character movement with precision. For this project, I used the Animation Blueprint system to create and integrate a character's idle, walk, and run animations, while also introducing a slot system for montage playback and independent skeletal part movement.

Resources Consulted
Video Tutorial

How To Make An Animation Blueprint In Unreal Engine 5 | How To Animate A Character - UE5 Tutorial (2022)
YouTube Video (Accessed 15/11/2024).
This comprehensive tutorial provided a step-by-step guide to setting up an Animation Blueprint. It covered creating and configuring a BlendSpace, working with skeletal meshes, and connecting animations to gameplay events. The practical demonstrations offered clarity and insights into real-world implementation.
Epic Games Documentation

Animation Blueprints in Unreal Engine | Unreal Engine 5.5 Documentation | Epic Developer Community
Epic Games Documentation (Accessed 15/11/2024).
This official documentation outlined the technical capabilities of Animation Blueprints in Unreal Engine 5. It detailed concepts such as state machines, BlendSpaces, and montage systems, providing a strong theoretical foundation for managing character animations.




# Example Documentation


Animation Blueprints (ABPs) in Unreal Engine 5 enable developers to control animations programmatically, offering flexibility to handle complex scenarios like blending multiple animations, synchronizing movement with gameplay, and layering dynamic animation effects. Some of the core concepts I explored during this project include:

BlendSpaces:
BlendSpaces allow the seamless transition between animations based on input parameters, such as speed. This is ideal for creating lifelike movement where characters transition smoothly from idle to walking and then to running.

Montages and Slot Nodes:
Montages provide a mechanism to play animations independently of the main animation graph, making them ideal for actions like attacking or interacting with objects. Slot nodes allow developers to define areas of the skeletal mesh to play specific animations without interfering with other parts.

Skeletal Mesh Control:
Unreal Engine's Animation Blueprint system supports isolating and controlling parts of a character's skeletal mesh, enabling independent movement of upper and lower body parts. This feature is particularly useful for scenarios like running while aiming or attacking.



## Implementation

Creative and Technical Approaches
To implement the character animations, I followed a structured workflow using Unreal Engine 5’s Animation Blueprint system:

1. Character Import and Animation Setup
I started by importing a skeletal mesh and its associated animations (idle, walk, and run). The skeletal mesh was fully rigged, enabling direct integration with Unreal Engine’s animation tools.

2. Creating the BlendSpace 1D
A BlendSpace 1D was used to manage the transitions between the idle, walk, and run animations. The steps were:

Parameter Assignment:
Configured a speed parameter to drive the BlendSpace. This parameter was updated in real-time based on the character’s movement speed.
Animation Mapping:
Mapped the idle animation at speed 0, the walk animation at mid-speed, and the run animation at maximum speed.
Smooth Transitions:
Adjusted interpolation settings to ensure smooth transitions between animations as the speed parameter changed.
3. Setting Up the Animation Blueprint
The Animation Blueprint served as the central hub for managing animations. Key actions included:

State Machine Creation:
Built a state machine within the Animation Blueprint to define states like “Idle/Walk/Run.” Each state was connected to the BlendSpace to handle animation blending dynamically.
Event Graph Programming:
Used the Animation Blueprint’s event graph to retrieve character movement data (e.g., velocity) and feed it into the BlendSpace’s speed parameter.
4. Adding a Default Slot for Montages
To enable montage playback, I added a default slot node to the Animation Blueprint.

Slot Node Placement:
Positioned the default slot in the animation graph, ensuring it could overlay animations from montages without interfering with the BlendSpace or state machine logic.
Montage Integration:
Created and linked animation montages (e.g., attack or interaction animations) to specific gameplay events, allowing them to play independently of other animations.
5. Independent Movement of Skeletal Mesh Parts
For greater control, I configured the lower and upper body parts to move independently:

Bone Filtering:
Used bone filtering in the Animation Blueprint to isolate movement to specific skeletal parts. For instance, the lower body followed BlendSpace-driven animations (idle, walk, run), while the upper body could perform separate actions like aiming or attacking.
Layered Blending:
Applied layered blending to merge upper-body animations (e.g., attacking) with lower-body movement seamlessly.












## Outcome
The final implementation achieved fluid character animations with dynamic movement and independent skeletal part control.

Visual Quality
Seamless Blending:
The BlendSpace transitions were smooth, creating lifelike movement as the character changed speed.
Layered Animation Effects:
The slot node and bone filtering enabled complex animations, such as running while performing attacks, without disrupting the natural motion of other body parts.
Gameplay Responsiveness
Real-Time Updates:
The speed parameter linked to the BlendSpace updated in real time based on player input, ensuring animations reflected character actions instantly.
Independent Animation Playback:
Montages played independently, allowing for responsive and context-specific animations like combat moves or item interactions.



## Critical Reflection
Strengths
Flexibility:
The Animation Blueprint system’s modularity allowed me to handle complex animation scenarios, such as combining BlendSpaces with montage playback and skeletal mesh control.
Responsiveness:
The seamless transitions and independent skeletal part movement enhanced the character’s responsiveness, improving player immersion.
Limitations
Limited Procedural Animation:
While the BlendSpace and montages worked well, the implementation lacked procedural animations, such as inverse kinematics for foot placement on uneven terrain.
Montage Overlap Handling:
Managing overlapping montages required additional logic, which was not fully optimized in this iteration.

Future Improvements
To further enhance the animation system, I plan to:

Implement Procedural Animation Techniques:
Add features like inverse kinematics to adapt animations dynamically to the environment (e.g., foot alignment on slopes).

Enhance Montage Logic:
Introduce layered montage playback systems to handle overlapping actions seamlessly, such as attacking while dodging.

BlendSpace 2D Integration:
Upgrade to a BlendSpace 2D to handle additional parameters like direction, enabling diagonal movement animations.

## Bibliography

How To Make An Animation Blueprint In Unreal Engine 5 | How To Animate A Character - UE5 Tutorial (2022) At: https://www.youtube.com/watch?v=TE-SsP3pigs (Accessed  16/11/2024).
-
Animation Blueprints in Unreal Engine | Unreal Engine 5.5 Documentation | Epic Developer Community (s.d.) At: https://dev.epicgames.com/documentation/en-us/unreal-engine/animation-blueprints-in-unreal-engine (Accessed  16/11/2024).
-


ChatGPT (s.d.) At: https://chatgpt.com (Accessed  10/10/2024).


## Declared Assets

Modular Asian Medieval City in Environments - UE Marketplace (s.d.) At: https://www.unrealengine.com/marketplace/en-US/product/modular-asian-medieval-city (Accessed 10/10/2024).
Mixamo (s.d.) At: https://www.mixamo.com/#/ (Accessed  10/10/2024).




The following assets were created or modified with the use of GPT 4o:
- Development Journal.html
