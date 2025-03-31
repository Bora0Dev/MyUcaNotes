# Development Commentary
Last Drop is a 3D side-scrolling puzzle game that combines dynamic environmental interactions with physics-based mechanics. The game’s central feature is the character, who is equipped with a bubble that is attached to their head. This bubble plays a crucial role in solving puzzles and overcoming obstacles throughout the game. The player must manipulate the bubble to interact with various surfaces and objects, navigating through intricate levels that increase in complexity as the player progresses.

At the heart of the game is the Surface State System, a mechanic that dynamically changes the behavior of the bubble based on the surface it interacts with. Different surfaces affect the bubble in various ways. For example, if the bubble comes into contact with an oil surface, it will change to an “Oil” state, making it vulnerable to fire. If the bubble touches a fire surface, it will immediately switch to a "Fire" state, where it becomes destructible. This state-changing mechanic is designed to challenge the player’s strategic thinking, as they must carefully plan their bubble’s movements to avoid dangerous surfaces and solve puzzles in the environment.

Another critical feature is the Checkpoint Saving System, which allows the player to save their progress throughout the game. The checkpoint system works by automatically saving the player’s location and the state of the bubble when the player activates a checkpoint. This ensures that the player can resume from the last checkpoint if they fail or need to take a break, providing a smoother and less frustrating gameplay experience. The save system relies on Unreal Engine's SaveGame functionality, which stores the player’s transform data and camera rotation. This ensures that when the player reloads the game, they resume at the exact position they were at before.

The core puzzles in Last Drop are centered around solving challenges by manipulating the bubble’s state and interacting with different surfaces and objects within the environment. Players need to think critically and react quickly, often needing to control the bubble's movement with precision while also managing the dynamic environment around them. The game’s difficulty ramps up gradually, with early levels introducing simple surface interactions and later levels requiring the player to use all of the bubble's states and abilities to complete increasingly complex puzzles.

The design of the levels incorporates a mix of physics-based puzzles and platforming elements. The environments are carefully crafted to encourage exploration and experimentation, with multiple solutions to certain puzzles. The player must adapt to the environment and make use of the bubble's interactions with surfaces to progress. The combination of physics mechanics and puzzle-solving creates a unique challenge that requires the player to think creatively while navigating a visually engaging world.

In addition to the bubble mechanics and puzzle-solving elements, the game also features game materials to visually represent the bubble's state changes. These effects enhance the player’s immersion, providing clear and immediate visual feedback for state transitions, such as when the bubble switches states. The use of Niagara effects adds to the overall aesthetic of the game, enhancing the atmosphere and providing a more polished visual experience.

Ultimately, Last Drop is a game that emphasizes creativity, strategic thinking, and careful decision-making. By combining physics, puzzle-solving, and dynamic environmental interactions, the game provides a unique and engaging experience that challenges players to use their wits to progress through a series of increasingly complex levels. The checkpoint save system ensures that players can enjoy the game without the frustration of losing significant progress, further enhancing the overall experience.
# Project Outline (Suggested Word Count 500)
Last Drop is a 3D side-scrolling puzzle platformer that revolves around a unique mechanic where the player controls a character with a bubble attached to their head. This bubble reacts to different surfaces in the environment, changing states based on the surface the player interacts with. The game is set across four distinct seasonal levels—Spring, Summer, Autumn, and Winter—each introducing its own set of mechanics and challenges. Players must solve puzzles by manipulating the bubble and using the environmental effects, all while navigating through intricate level designs. The game also focuses on performance optimization using material-based state changes rather than relying heavily on particle effects.

## Core Gameplay
The core mechanic in Last Drop revolves around a bubble that is attached to the player's character. The bubble's behavior changes when it interacts with various surfaces, and the player must manipulate the environment to use these interactions to solve puzzles and progress through the game. The bubble can enter different states, which are determined by the environmental surface it comes in contact with. These states include Oil, Fire, and the states tied to each of the four seasons: Spring, Summer, Autumn, and Winter.

## Level Design
Oil, Fire, Spring, Summer, Autumn, and Winter: The bubble will change states when interacting with different surfaces. For example, the bubble may become oily when it comes into contact with an oil surface, making it slippery and difficult to control. In Fire-related areas, the bubble may combust and become destructible.

- Spring Level: The bubble might become wet, allowing it to float or move through water. The player may need to use water-based interactions to navigate through obstacles.
#

- Summer Level: The bubble may heat up, requiring the player to find ways to cool it down by avoiding intense heat or seeking cooler areas.
#

- Autumn Level: Surfaces like mud and debris might cause the bubble to become sticky, forcing the player to use the bubble’s new properties to solve weight- and traction-based puzzles.
#

- Winter Level: Ice-based surfaces may freeze the bubble, making it fragile. The player will need to avoid breaking the bubble while navigating slippery and frozen terrain.
#

The player must adapt to each level’s unique mechanics, using the bubble’s states to interact with the environment and solve puzzles. The changing states create opportunities and challenges as the player progresses.



## Visual Design & Material Usage
To optimize performance and ensure smooth gameplay, Last Drop uses materials instead of relying heavily on Niagara particle effects to indicate changes in the bubble’s state. Different surface interactions will change the bubble’s material properties, which are visually represented with dynamic textures and effects. This allows for smoother performance while still delivering immersive visual feedback to the player.

However, Niagara effects are still used in the environment, such as falling leaves in Autumn, drifting snow in Winter, and heat distortion effects in Summer. These environmental effects help set the atmosphere of each seasonal level and enhance the game’s visual appeal without overloading the system.

## Audio Design
The audio design in Last Drop is crucial in immersing players into the world of the game and reflecting the unique atmosphere of each season. Sound plays a significant role in helping players understand the state of the bubble and the environment around them.

Spring: The background features soft, melodic tunes with sounds of birds chirping and flowing water, creating a tranquil atmosphere. The bubble’s interaction with wet surfaces produces gentle splashing sounds, reinforcing the watery theme.

Summer: The soundtrack features warm, vibrant melodies, with ambient sounds such as buzzing insects, wind rustling through trees, and distant waves. The bubble’s interaction with hot surfaces might include sizzling or popping sounds as it heats up.

Autumn: The sounds of crunching leaves, whistling wind, and a calming, earthy soundtrack set the tone. The sticky bubble on autumn surfaces might create subtle squelching or tacky noises as it adheres to objects or surfaces.

Winter: A cold, crisp soundscape, with snow crunching, icy winds, and soft, ambient winter music. The bubble’s interactions with ice are accompanied by cracking or shattering sounds as it becomes fragile.

The audio helps to signal important environmental changes and reinforces the feeling of each season. Additionally, sound effects linked to the bubble’s interactions—such as sizzling in Summer or cracking in Winter—serve as valuable feedback to the player, indicating the bubble’s current state.#
# Research (Suggested Word Count 1,100)

## Methodology

## Game Sources

## Academic Sources

## Documentation Sources

# Implementation (Suggested Word Count 1,100)

## Process
The surface state and saving system for Last Drop was designed to enhance gameplay mechanics by introducing different surface states that dynamically alter the behavior of the bubble. Each state (Oil, Fire, Water, Ice, Sap, and seasonal states like Spring, Summer, Autumn, and Winter) changes the bubble's interactions with the environment, providing both challenges and puzzle-solving opportunities for the player.

The SurfaceStateComponent was created as a custom actor component attached to the bubble, allowing the system to detect the surface beneath the bubble using a sphere trace. Based on the detected surface, the bubble’s state changes accordingly. The states are represented using materials instead of Niagara particle effects to optimize performance. This decision was crucial as it allowed for dynamic visual updates without sacrificing frame rates, especially in complex levels with numerous surface interactions.

Each state affects the bubble’s properties differently:

Oil State: The bubble becomes slippery, making it difficult for the player to control its movement.

Fire State: The bubble is highly volatile and bursts upon contact with a fire surface.

Water State: The bubble floats on water surfaces, offering buoyancy that helps navigate water-filled areas.

Ice State: The bubble becomes slick and brittle, sliding on surfaces and breaking upon impact with hot objects.

Sap State: When the bubble enters the Sap State, it drops sap liquid onto the floor. This sap creates a platform that the player can use to launch themselves or navigate obstacles. This added layer of interactivity enhances puzzle-solving, as players must use sap to create platforms and overcome vertical challenges.

For the SurfaceStateComponent, materials were dynamically swapped when a new state was detected. For instance, when the bubble enters the Water state, the material becomes a semi-transparent, wet texture, while the Ice state gives the bubble a frosted, brittle appearance. Environmental Niagara effects (like fire, water splashes, and ice crackles) were still utilized, but these were kept to environmental interactions to avoid excessive performance overhead.

The SaveGameData class, derived from Unreal's USaveGame class, was used to serialize and persist the player's position and bubble state. This ensures that when the player reloads, the game picks up right where they left off with the correct bubble state. The Game Instance handles saving and loading, storing data in a save slot like "Slot1." This functionality is essential for maintaining continuity in puzzle progression, where the bubble's state plays a key role in solving challenges.
## New Approaches
A critical approach for handling multiple surface states across levels was the use of dynamic material changes. This allowed each state—Oil, Fire, Water, Ice, Sap, and the seasonal states—to have distinct visual representations without the performance overhead associated with particle effects. The materials were parameterized to adjust the visual properties in real-time, based on the bubble’s interaction with the surface it was on.

Using C++ enums to manage the bubble's state made the system highly modular and easy to extend. For example, adding new surface states like Water or Ice was straightforward because of the clean separation between the game mechanics and the graphical assets. This flexibility allowed for the bubble’s behavior to be easily modified or expanded as new gameplay mechanics were introduced.

Incorporating AI tools like ChatGPT for code assistance proved to be a valuable approach during the development. As I was unable to find adequate documentation for implementing specific mechanics in C++, I utilized AI to help generate the necessary code snippets. AI tools like ChatGPT helped in writing complex logic for state transitions, collision detection, and interaction mechanics, such as the platform creation in the Sap State. This assistance expedited the development process and allowed me to focus on more creative aspects of the game.
## Testing
Testing the surface state system involved rigorous checks to ensure the bubble reacted correctly to different surfaces and environmental conditions. Each state had to behave according to the designed mechanics. For example, when transitioning to the Fire State, the bubble needed to burst if it came into contact with fire, whereas in the Oil State, the bubble had to slide across surfaces uncontrollably.

Testing also focused on edge cases, such as ensuring the bubble didn’t get stuck or break unintended rules—e.g., no transitions from Fire to Oil—and verifying that the Sap State worked as expected. The Sap mechanic, in particular, was challenging to implement and test. When the bubble dropped sap liquid onto the floor, it created a platform. We tested this mechanic to ensure the sap liquid would be persistent and form a usable platform for the player to jump off. Adjustments were made to the timing and physics of the sap liquid to make the platform creation reliable and consistent for the player.

The Save and Load System was tested by saving the game at different points and ensuring that the player’s position and bubble state were correctly loaded. We conducted multiple rounds of load tests to verify that the bubble’s state remained intact upon reloading, and no data was lost during the save/load process. This was especially critical because the bubble’s behavior can dramatically alter puzzle solutions, and the player needs to resume with the same state when they load the game.
## Technical Difficulties
 - Finding Documentation for C++ Implementations: One of the primary challenges during development was finding comprehensive and up-to-date documentation for implementing surface state mechanics in Unreal Engine using C++. While there was a lot of information available on basic gameplay systems, there was little guidance on how to implement specific mechanics like dynamic material swapping or creating complex surface interactions (such as the Sap mechanic). To overcome this, I turned to AI tools like ChatGPT to generate C++ code snippets for logic and state transitions. AI assistance allowed me to quickly implement the functionality needed to handle different surface types and behaviors, as well as manage complex transitions between states.
 #

- Sap Mechanics Implementation: The Sap State mechanic, where the bubble drops sap liquid to create a platform, presented its own set of difficulties. The sap needed to persist after the bubble changed states or moved away. Ensuring the sap liquid interacted with the environment and created a solid platform that the player could jump off was particularly challenging. Physics interactions were required to simulate the sap’s liquid state and ensure it solidified into a usable platform. It was a time-consuming process to refine the liquid-to-platform mechanic so that it was consistent and reliable during gameplay.
#

- Managing State Transitions: With multiple surface states interacting in complex ways, managing state transitions between Oil, Fire, Water, Ice, Sap, and seasonal surfaces (Spring, Summer, Autumn, Winter) required careful attention to detail. Conflicting interactions between states had to be avoided—e.g., preventing the Fire State from transitioning into the Oil State. Developing a robust state transition system was essential, and there were moments where the logic for state switches needed to be reworked to accommodate more edge cases and ensure smooth gameplay.
#

- Performance Optimization: Although using dynamic materials helped reduce performance costs compared to particle effects, there were still challenges with maintaining performance in larger levels with multiple surface interactions. Some levels were more graphically demanding, and ensuring that material transitions between different states didn’t cause noticeable lag was important. Optimizing the material parameters and using material instances helped mitigate these issues, but testing performance across various devices and hardware configurations was essential.
#
# Outcomes (Suggested Word Count 300)

## Source Code/Project Files

## Build Link

## Video Demonstration

# Reflection (Suggested Word Count 500)

## Research Effectiveness
Assess the usefulness of the research conducted during the project.
Highlight which sources (games, academic, documentation) had the most significant impact on your work and explain why.
Identify any research gaps or areas where additional information could have improved your project outcomes.
## Positive Analysis

Reflect on the successful aspects of the project.
Highlight specific elements that worked well, such as technical solutions, creative decisions, or user feedback.
Provide evidence to support your analysis, such as test results, screenshots, or user comments.
## Negative Analysis

Identify the areas of the project that did not go as planned or could have been improved.
Discuss challenges you faced, whether technical, creative, or time-related, and evaluate their impact on the final product.
Reflect on any mistakes or missteps and what you learned from them.
## Next Time

Outline what you would do differently if you were to undertake a similar project again.
Suggest improvements to your workflow, research methods, or implementation process based on your reflections.
Consider any new tools, techniques, or approaches you would explore in future projects to achieve better results.
# Bibliography

Compile a complete list of all sources referenced throughout your project. This may include articles, journals, videos, games, software, documentation, or any other materials.
Ensure all references are formatted according to the university's citation method.
Organise your references in alphabetical order. Alternatively, you may separate them by type (e.g., academic sources, games, videos), but consistency is key.
# Declared Assets

Provide a detailed list of any third-party assets used in the project.
This includes asset packs, music, sound effects, 3D models, textures, scripts, or code from external sources.
Declare any use of AI tools (e.g., ChatGPT, GitHub Copilot, Meshy) or pre-existing code. Specify the purpose of these assets/tools and how they were integrated into your work.
Ensure you clearly distinguish between your original work and any external contributions to maintain academic integrity.
