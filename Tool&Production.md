# Development Commentary
# Project Outline (Suggested Word Count 500)
Last Drop is a 3D side-scrolling puzzle platformer that revolves around a unique mechanic where the player controls a character with a bubble attached to their head. This bubble reacts to different surfaces in the environment, changing states based on the surface the player interacts with. The game is set across four distinct seasonal levels—Spring, Summer, Autumn, and Winter—each introducing its own set of mechanics and challenges. Players must solve puzzles by manipulating the bubble and using the environmental effects, all while navigating through intricate level designs. The game also focuses on performance optimization using material-based state changes rather than relying heavily on particle effects.


###Identify any anticipated challenges or potential issues that may arise during development.
## Core Gameplay

The core mechanic in Last Drop revolves around a bubble that is attached to the player's character. The bubble's behavior changes when it interacts with various surfaces, and the player must manipulate the environment to use these interactions to solve puzzles and progress through the game. The bubble can enter different states, which are determined by the environmental surface it comes in contact with. These states include Oil, Fire, and the states tied to each of the four seasons: Spring, Summer, Autumn, and Winter.

## Visual Design & Material Usage
To optimize performance and ensure smooth gameplay, Last Drop uses materials instead of relying heavily on Niagara particle effects to indicate changes in the bubble’s state. Different surface interactions will change the bubble’s material properties, which are visually represented with dynamic textures and effects. This allows for smoother performance while still delivering immersive visual feedback to the player.

# Research 

## Methodology
Investigate relevant documentation, tutorials, or instructional videos that provide technical insights into your tasks. Summarise the content and its relevance to your project.
Explain how this technical knowledge supports your project work and guides your decision-making process.
## Game Sources

Portal 2 introduces new mechanics, such as gels and light bridges, to evolve the portal system as the game progresses. In a similar vein, Last Drop introduces seasonal changes, each with its own set of surface types that affect the bubble's behavior. For example, in the Winter level, the bubble might slide across icy surfaces, while in Autumn, Sap creates platforms for the player to jump on. These mechanics keep the gameplay fresh, much like how Portal 2 introduces new puzzle elements to challenge players. (Mechanics, Depth, and Portal 2, s.d.)

Both games share the design philosophy of limiting player freedom to drive creativity. In Portal 2, the portal surfaces are restricted to specific walls, forcing players to think critically about where and when to use their portals. In Last Drop, the bubble’s state is determined by the surface it interacts with, which influences the player’s actions and decisions in each puzzle.

Through Portal 2, we learned the importance of building on a core mechanic and using environmental interaction to create deep, engaging puzzle-solving experiences. This approach heavily influenced the design of Last Drop’s evolving surface state mechanics.
## Academic Sources
The academic sources I consulted were largely centered around game mechanics and player experience. Miguel Sicart’s “Defining Game Mechanics” (Sicart, 2008) provided insights into the relationship between game mechanics and player actions, which was vital in understanding how the player’s interaction with the bubble state system could shape their puzzle-solving experience. Sicart's definition of "core mechanics" helped me identify the primary gameplay elements of The Last Drop, such as the bubble's state changes and the surface types. This perspective informed the design of the bubble system, where each state represents a unique mechanic that requires the player to adapt and think strategically to solve puzzles.

Additionally, Unreal Engine’s documentation was heavily referenced in understanding the technical side of the save system, particularly when dealing with object serialization and managing persistent game data. This knowledge was crucial in designing the game’s save/load functionality, ensuring a robust and flexible save system for player progression.
## Documentation Sources
In The Last Drop, a side-scrolling puzzle game built in Unreal Engine 5, I developed a save system to store and load the player’s transform (position and rotation) and camera rotation, inspired by Tom Looman’s “Unreal Engine C++ Save System (SaveGame)”(Looman, 2021). This system ensures players resume from their last saved position, enhancing puzzle continuity.

Following Looman’s methodology, I created a SaveGameData class derived from USaveGame in C++ to manage save data. I defined a struct, FPlayerData, to hold the player’s FTransform (position, rotation, scale) and camera rotation as an FRotator, mirroring Looman’s approach of structuring data for serialization. In SaveGameData, I added a FPlayerData property marked with UPROPERTY(SaveGame) for Unreal’s binary serialization. I also created an interface, ISaveSystem, with functions like SaveGameData(), LoadGameData(), GetGameData(), and SavePlayer(), providing a blueprint for save/load operations.

I implemented this interface in a custom Game Instance, centralizing save logic as Looman suggests for persistent game-wide access. In the Game Instance, SavePlayer() captures the player’s transform and camera rotation (via GetPlayerSave() in BP_BodyChar), stores them in FPlayerData, and saves to “Slot1” using UGameplayStatics::SaveGameToSlot. LoadGameData() checks if “Slot1” exists with DoesSaveGameExist(); if not, it initializes a new SaveGameData instance, and if it does, it loads the data with LoadGameFromSlot, applying it via UsePlayerSave() in BP_BodyChar. In BP_BodyChar, GetPlayerSave() retrieves the current transform and control rotation, while UsePlayerSave(), called on BeginPlay, sets the character’s transform and rotation from the loaded data.

For triggering saves, I created a Checkpoint Actor with a Trigger Box. On player overlap, it calls SavePlayer() through the Game Instance, storing the current transform and rotation to “Slot1”. This checkpoint system ensures progress is saved at key points, inspired by Looman’s practical examples of event-driven saves.

Looman’s influence shaped my implementation significantly. His tutorial’s use of USaveGame and UPROPERTY(SaveGame) directly informed my SaveGameData class and FPlayerData struct, adapting his C++ concepts to my mixed C++/Blueprint workflow. His emphasis on clean, reusable save logic guided my interface design and Game Instance setup, ensuring modularity. The idea of saving critical data like position—seen in Looman’s player position example—led me to prioritize the transform and camera rotation, vital for The Last Drop’s puzzle navigation. His versioning advice also influenced me to structure SaveGameData for future additions (e.g., player stats), though not yet implemented. Looman’s clear, structured approach gave me the confidence to blend C++ and Blueprints effectively, creating a robust save system tailored to my game’s needs.
### Actor Components
In Unreal Engine, Actor Components are modular pieces of functionality that can be attached to any Actor to extend its behavior without requiring inheritance. This system promotes clean, reusable code by allowing developers to compose behaviors in a flexible, object-oriented way. Unlike traditional class-based design, where all behaviors are defined directly in the Actor or its subclasses, components allow you to separate concerns—for example, handling movement, input, or surface detection—in self-contained modules. (Components in Unreal Engine | Unreal Engine 5.5 Documentation | Epic Developer Community, s.d.)


In our project Last Drop, we created a custom Actor Component called SurfaceStateComponent. This component is responsible for detecting the physical surface beneath the player’s bubble and changing the bubble's state accordingly. Because it is a standalone component, we were able to cleanly separate this behavior from the core character class. This modular approach allowed for reuse across different levels and ensured the logic could be updated or extended independently—for instance, to include new states like Sap, Ice, or Fire, without affecting unrelated systems.

The use of Actor Components aligns with Unreal Engine’s design philosophy of building flexible, reusable game logic. This was particularly valuable in our project as it allowed for clean integration of complex mechanics like dynamic state transitions, surface-based interaction, and visual feedback through material changes.
### Materials C++

Documentation on material assignment through C++ was sparse, especially for scenarios involving runtime asset management. A useful source that informed our approach was a community forum post discussing how to apply materials to static meshes in C++ (How to Create material using C++ and apply it to static mesh? - Development / Rendering, 2019). 

This provided a working example of using Unreal’s asset referencing and material application workflow in code. It guided us in implementing our own logic to dynamically switch materials based on physical surface types and bubble states, without relying on heavier visual systems like Niagara for every case.

### Sphere Trace
A key component in implementing the surface interaction system was the use of sphere traces to detect the physical material beneath the player’s bubble. Sphere traces offer a way to perform collision checks within a defined radius, providing smoother and more reliable surface detection than line traces, especially on uneven terrain or when the player is in motion.

To implement this in C++, it was essential to ensure that the trace not only returned collision information but also included data on the physical material of the surface hit. This enabled the system to determine whether the surface was classified as Oil, Fire, Ice, Sap, or any other custom-defined type, and to update the bubble’s state accordingly.

While Unreal Engine provides built-in support for tracing in Blueprints, applying this in C++—particularly with correct parameters and physical material support—required more in-depth understanding. The official Unreal Engine documentation on Sphere Trace by Channel was instrumental in shaping this system (Sphere Trace By Channel | Unreal Engine 5.5 Documentation | Epic Developer Community, s.d.). 

It detailed the necessary parameters, including the use of FCollisionQueryParams and setting bReturnPhysicalMaterial = true, which was a crucial fix in resolving an earlier bug where physical materials were not being detected during the trace.

The documentation clarified how to structure the trace and interpret the resulting FHitResult, providing the foundation for a reliable and performant surface detection system tied directly to game mechanics.
# Implementation (Suggested Word Count 1,100)

## Process
A custom actor component, the SurfaceStateComponent, was attached to the bubble. This component uses a sphere trace to detect the surface beneath the bubble and changes the bubble’s state accordingly. Materials were used instead of Niagara particle effects to optimize performance, ensuring dynamic visual updates without sacrificing frame rates, particularly in levels with numerous surface interactions.

Each surface state affects the bubble's properties differently:

- Oil State: The bubble becomes slippery and harder to control.

- Fire State: The bubble bursts upon contact with fire surfaces.

- Water State: The bubble floats on water surfaces, aiding navigation.

- Ice State: The bubble becomes slick and brittle, sliding on surfaces and breaking on hot objects.

- Sap State: The bubble drops sap liquid that forms a platform, allowing the player to launch themselves or navigate obstacles.

By dynamically swapping materials for each state, we ensured that each state had a visually distinct effect, like semi-transparent wet textures for water and frosted appearances for ice. Environmental Niagara effects (like fire, splashes, and crackles) were used sparingly to prevent performance overhead.

Save Game System
To maintain gameplay continuity, a save system was created using Unreal's SaveGame system. A SaveGameData class, derived from USaveGame, serialized the player’s position and bubble state for saving and loading. The Game Instance handled saving and loading operations, storing data in a save slot such as "Slot1." This system ensures that the player resumes with the correct bubble state when the game is loaded, crucial for solving puzzles.

Key elements of the save system included:

- Player Data Struct: A struct to store player transform (position, rotation) and camera rotation.

- SaveGameData Class: A class derived from USaveGame to manage the player’s data.

- Save System Interface: An interface for functions like SaveGameData(), LoadGameData(), and SavePlayer().

- Game Instance Implementation: A custom Game Instance managing save and load logic.

- Checkpoint System: A checkpoint actor with a trigger box to save player data upon overlap.

## New Approaches

The most critical approach was the use of dynamic material changes for different surface states. This allowed the bubble to react uniquely to surfaces like water, ice, and fire without relying on particle effects, thus improving performance. Materials were parameterized to adjust in real-time based on the detected surface.

Using C++ enums to manage bubble states made the system modular and extendable, ensuring that future gameplay mechanics could be added easily. This system was both flexible and scalable, allowing for quick integration of new surface states.

I also incorporated AI tools like ChatGPT for generating complex C++ code, especially in areas like state transitions and collision detection. This AI-assisted approach helped fill gaps in documentation and expedited development, especially when handling intricate mechanics like the Sap state, where the bubble drops sap to create platforms.
## Testing
Testing focused on ensuring the bubble’s state transitions and interactions worked as expected:

State Interactions: Each surface state was tested to ensure it triggered the correct behavior—oil made the bubble slippery, fire caused it to burst, etc.

Edge Cases: Testing included verifying that the bubble didn’t break unintended rules (e.g., no transition from Fire to Oil) and ensuring reliable sap platform creation.

Save/Load System: We tested the save/load system to confirm that the player’s position and bubble state were correctly restored. Multiple tests ensured the bubble’s state persisted upon reloading.
## Technical Difficulties
C++ Documentation: A major challenge was the lack of clear documentation for implementing dynamic material swapping and surface interactions in C++. Much of the necessary logic had to be created from scratch with the help of AI tools like ChatGPT. These tools proved essential in generating code for state transitions, collision detection, and other complex mechanics.

Sap Mechanics: The Sap state, where the bubble drops sap to create a platform, posed difficulties in ensuring the sap persisted and behaved correctly after state changes. Implementing reliable physics interactions for sap and ensuring the platform was solid and usable were particularly challenging. It took several iterations to refine the mechanic, making it consistent and intuitive.

State Transitions: Managing state transitions between Oil, Fire, Water, Ice, Sap, and seasonal surfaces required attention to detail. Conflicting state transitions, such as preventing Fire from transitioning into Oil, needed careful logic development. The system was continuously refined to accommodate edge cases and ensure smooth gameplay.

Performance Optimization: Although dynamic materials helped reduce the performance costs of particle effects, maintaining smooth performance across large levels with multiple surface interactions remained a challenge. Material parameters and instances were optimized to mitigate these issues, but performance still needed to be tested on various hardware to ensure smooth gameplay.
#
# Outcomes (Suggested Word Count 300)

## Source Code/Project Files

## Build Link

## Video Demonstration

# Reflection (Suggested Word Count 500)

## Research Effectiveness
The research conducted during The Last Drop was vital in addressing both technical and gameplay challenges. Key sources that influenced my work were Tom Looman’s “Unreal Engine C++ Save System (SaveGame)” (2021) and the Unreal Engine documentation, especially materials on saving systems, actor components, and sphere traces. Looman’s guide provided the foundation for my save system, allowing for a reliable implementation of saving and loading game data in C++. Unreal Engine’s documentation was essential for understanding surface detection mechanics and optimizing performance by switching from particle effects to dynamic materials.

However, a gap existed in C++-focused documentation, especially for complex systems combining dynamic surface states with saving/loading features. While tutorials focused on Blueprint solutions, there were fewer detailed C++ examples, slowing development and forcing reliance on external tools like AI for assistance. More C++-specific documentation would have improved efficiency.
## Positive Analysis
A major success was the save and load system. By following Looman’s methodology, I created a robust system that stored the player’s transform and camera rotation, ensuring continuity in gameplay. The modular design allows for scalability, with the potential for future features like player stats or multiple save slots.

The dynamic surface state mechanics were another highlight. By implementing states like Oil, Fire, Sap, Water, and Ice, I created engaging puzzles that forced players to adapt to changing conditions. The Sap State, where the bubble drops sap to create platforms, enhanced puzzle complexity and added depth to the gameplay. Playtesting confirmed that players enjoyed the challenge and sense of discovery these states provided.
## Negative Analysis
Despite the successes, some challenges hindered development. A significant issue was the lack of detailed C++ documentation for complex systems. This gap led to slower development as I relied on AI to generate code snippets for state transitions and interactions, which sometimes added extra integration time.

Another challenge was balancing complex puzzle mechanics with player understanding. While multiple surface states offered depth, some players struggled to grasp the relationships between states and puzzles. This could have been addressed by improving the tutorial system and providing clearer visual cues to guide players through the mechanics more intuitively.
## Next Time
If I were to take on a similar project again, I would focus on gathering more C++ documentation for advanced Unreal Engine integration. Having a deeper understanding of C++ within Unreal would have accelerated development, particularly for complex systems like dynamic materials and state transitions.

I would also implement a gradual tutorial system that introduces players to new mechanics step-by-step. This would ease players into the complexity of the surface states, making the gameplay experience more intuitive and less overwhelming. Additionally, I would explore AI-assisted code generation more strategically, ensuring its use is efficient and targeted to specific tasks.

Lastly, I would improve the visual feedback for state interactions, using environmental cues or NPC guidance to help players better understand the game mechanics and progress with confidence.

In conclusion, the development of The Last Drop was a rewarding learning experience, offering both technical challenges and creative opportunities. The insights gained will be valuable for future projects, and I look forward to applying these lessons moving forward.
# Bibliography
 Looman, T. (2021) Unreal Engine C++ Save System (SaveGame). At: https://www.tomlooman.com/unreal-engine-cpp-save-system/ (Accessed  07/04/2025).
 Sphere Trace By Channel | Unreal Engine 5.5 Documentation | Epic Developer Community (s.d.) At: https://dev.epicgames.com/documentation/en-us/unreal-engine/BlueprintAPI/Collision/SphereTraceByChannel (Accessed  06/04/2025).
 How to Create material using C++ and apply it to static mesh? - Development / Rendering (2019) At: https://forums.unrealengine.com/t/how-to-create-material-using-c-and-apply-it-to-static-mesh/445061 (Accessed  06/04/2025).
 The ultimate guide | How to Save & Load your unreal engine 5 game | ue5 (2024) At: https://www.youtube.com/watch?v=H6rqJbwjRIk (Accessed  08/02/2025).
 Mechanics, Depth, and Portal 2 (s.d.) At: https://www.gamedeveloper.com/business/mechanics-depth-and-portal-2 (Accessed  06/04/2025).
 Components in Unreal Engine | Unreal Engine 5.5 Documentation | Epic Developer Community (s.d.) At: https://dev.epicgames.com/documentation/en-us/unreal-engine/components-in-unreal-engine (Accessed  06/04/2025).
 Sicart, M. (2008) 'Defining Game Mechanics' In: Game Studies 8 (2) At: https://gamestudies.org/0802/articles/sicart (Accessed  07/04/2025).




# Declared Assets


