# [AdvancedTechnicalArtProject]



Bora Tibet Ozdemir

2221180

## Research




In developing my Unreal Engine 5 project, I focused on creating an immersive gameplay experience centered around magic combat and enemy AI. To achieve this, I explored a wide range of features and tools offered by Unreal Engine, including Niagara Fluids for visual effects, behavior trees for AI, and Widget Blueprints for the HUD. My approach was guided by in-depth research and learning from tutorials, which provided practical examples and best practices.

Niagara Fluids and VFX in Unreal Engine 5
The magic combat system relied heavily on Niagara Fluids to deliver visually compelling effects. Using "Niagara Fluids Smoke Portal VFX Tutorial in Unreal Engine 5.3" (RedefineFX, 2024), I learned how to craft detailed, real-time simulations for fireballs, explosions, and energy trails. This tutorial highlighted how to:

Adjust particle behavior dynamically based on player input.
Optimize particle systems for real-time responsiveness without significant performance loss.
Add visual flair to effects like smoke trails, fire bursts, and magical impact effects.
These visual enhancements were integral to creating a game world where the use of magic felt powerful and satisfying.

UI and HUD Management
Player engagement requires clear communication of critical information, such as health and stamina. For this, I referred to "Best Practices for Creating and Managing Widgets | UI | Widgets | HUD | Unreal Engine 5 Tutorial" (2023). Key takeaways included:

Using Widget Blueprints to create dynamic health and stamina bars.
Ensuring widgets are responsive to in-game events, such as taking damage or casting a spell.
Organizing HUD elements to remain unobtrusive yet informative, contributing to an immersive experience.
The ability to update HUD elements in real-time provided players with immediate feedback, improving gameplay fluidity.

AI Behavior Using Behavior Trees
Creating intelligent enemy AI was a crucial aspect of the project. My implementation focused on two key states: chase and combat. Using "Smart Enemy AI | (Part 1: Behavior Trees) | Tutorial in Unreal Engine 5 (UE5)" (2023), I built an AI system that dynamically reacted to player presence.

Chase State: The skeleton AI transitions to this state upon detecting the player. A perception system triggers the chase behavior, directing the enemy toward the player's position while navigating around obstacles. This state adds tension and urgency to the gameplay as enemies actively pursue the player.

Combat State: Once the skeleton AI reaches proximity to the player, it transitions into a combat state. Here, the enemy executes attack animations using animation notifies to synchronize damage application with the swing of its weapon. The AI’s responsiveness in this state ensures engaging, action-packed encounters.

These behavior tree states provided a foundation for creating reactive and challenging enemies, with potential for further expansion into more complex AI behaviors.

Sword Tracing for Melee Combat
To make combat interactions feel precise and impactful, I implemented a sword tracing system. Following the principles outlined in "Unreal Engine 5 RPG Tutorial Series - #10: Sword Trace Damage and Hit Reactions" (2023), this system allowed for:

Accurate detection of sword collisions with player or enemy meshes.
Triggering particle and sound effects upon successful hits to enhance combat feedback.
Synchronizing damage with attack animations, ensuring that only well-timed attacks register.
Sword tracing added depth to melee combat, making encounters feel more dynamic and rewarding.

Animation Systems
Smooth and believable character animations are essential for maintaining immersion. Referring to "Unreal Engine 5 Tutorial - Animation Blueprint Part 1: State Machines" (2023), I set up state machines for both the player and skeleton enemies. Combined with animation notifies from "Unreal Engine 5 Tutorial - Animation Notifies" (2022), this system ensured:

Seamless transitions between idle, walking, chasing, and attacking animations.
Precise timing for visual and mechanical actions, such as attacks and hit reactions.
Flexibility to expand animations in the future, such as adding dodging or parrying.




## Implementation
Magic Combat System
The magic combat system was the centerpiece of the gameplay. By leveraging Niagara Fluids, I created visually dynamic spells that included:

Fireballs: Projectile-based spells with trails that explode on impact.
Area-of-Effect (AoE): Spells that create magical zones with effects like shockwaves or energy bursts.
Energy Trails: Persistent visual effects that follow the player's movements, adding a magical ambiance.
The system integrates seamlessly with the stamina mechanic, where casting spells depletes stamina, requiring players to balance their resources strategically.

Enemy AI Behavior
The skeleton enemies’ behavior is driven by a simplified yet effective behavior tree focused on two states: chase and combat.

Chase State: Skeletons detect the player within a specified radius using Unreal Engine’s perception system. They dynamically navigate toward the player’s position, avoiding obstacles using the built-in navigation mesh.
Combat State: Upon reaching the player, skeletons transition to combat mode, executing attack animations. Damage is applied through sword tracing, synchronized with animation notifies to ensure precision.
These states create a reactive and engaging AI that challenges the player without feeling repetitive.

HUD with Health and Stamina
The HUD was implemented using Widget Blueprints to display health and stamina bars. These elements:

Update in real-time to reflect the player’s current status.
React to in-game events such as taking damage or using stamina for casting spells.
Provide intuitive feedback, helping players make informed decisions during combat.
Sword Tracing for Damage
The sword tracing system ensures realistic combat interactions by:

Detecting collisions between the skeleton’s weapon and the player character.
Triggering visual effects and sound cues on successful hits.
Adding a layer of realism by aligning damage events with weapon swings.










## Outcome
The development of this project resulted in the creation of a polished and cohesive game that successfully integrates several advanced systems, offering an engaging and immersive player experience. Beyond achieving technical goals, the project also served as a personal milestone, helping me grow significantly as a game developer. This section outlines the tangible and intangible outcomes of this project, from the game's systems and mechanics to its impact on my skills and aspirations.

A Complete and Playable Game
The most immediate and tangible outcome of this project was the creation of a fully functional game featuring a dynamic combat system, intelligent enemy behavior, and an immersive interface. These core elements worked in harmony to provide players with a challenging and satisfying gameplay loop, which includes:

Magic Combat System:

The magic combat system became the centerpiece of the game, offering players visually stunning and impactful offensive abilities. Each spell was meticulously designed to feel powerful and responsive, ensuring that combat moments felt rewarding.
Sword Tracing for Melee Combat:

The sword tracing system added precision to melee attacks, creating a sense of connection between the player’s actions and their effects in the game world. This system made close-range combat feel weighty and engaging.
Enemy AI with Chase and Combat States:

The behavior tree-driven enemy AI added tension and unpredictability to the game. Enemies dynamically transitioned between chase and combat states, making them feel alive and responsive. This simple but effective design kept players on their toes during encounters.
HUD Integration:

The health and stamina systems were effectively displayed on a responsive and polished HUD. This kept players informed about their character’s status, enhancing decision-making during combat and contributing to a smooth user experience.
Point System and Victory Condition:

The point system provided players with a clear objective—reaching 10,000 points to win the game. This mechanic added structure to the gameplay, giving players a sense of progression and accomplishment.
A Visually Polished Experience
Another significant outcome was the game’s visual presentation, which was greatly enhanced by advanced features in Unreal Engine 5:

Niagara Particle Effects:

Implementing Niagara particle systems allowed me to create visually stunning magic effects and environmental flourishes. These effects not only improved the aesthetic quality of the game but also contributed to gameplay feedback by making actions like casting spells feel impactful.
Atmospheric Lighting and Environments:

Carefully designed lighting and environments added depth and immersion to the game world. Dark and eerie tones complemented the skeleton enemies, enhancing the overall atmosphere.
Player Feedback and Replayability
Although this was a solo project, testing the game with friends and peers provided invaluable insights. Feedback confirmed that the game was both fun and challenging, with players praising the responsiveness of the combat system and the intensity of the enemy AI. The dynamic nature of the AI and the escalating difficulty ensured replayability, as no two playthroughs felt exactly the same.

Personal and Professional Growth
Beyond the technical achievements, this project marked a turning point in my personal and professional development as a game developer. It challenged me to grow in several key areas:

Improved Technical Skills:

I gained hands-on experience with Unreal Engine’s advanced features, including behavior trees, animation blueprints, and the Niagara particle system. These skills significantly expanded my toolkit and will serve as a strong foundation for future projects.
Enhanced Problem-Solving Abilities:

Debugging issues like AI transitions, collision detection in the sword tracing system, and performance optimization honed my analytical thinking and troubleshooting skills.
Time Management and Prioritization:

Successfully delivering a complete game within a set timeline required careful planning and prioritization. This project taught me to focus on high-impact features while deferring less critical elements for future iterations.
Broader Implications for My Development Journey
This game is the first project that I am genuinely proud of, marking a shift from experimentation to creating something meaningful and polished. It represents a culmination of the knowledge and skills I have accumulated so far and has instilled in me the confidence to tackle larger and more ambitious projects.

Next Steps for the Game
While the game is complete in its current state, there are numerous opportunities for improvement and expansion:

Additional Features:
Introducing new enemy types, environments, and spells would add variety and depth to the gameplay.
Polishing Visuals:
Further refining particle effects and animations could elevate the visual experience.
Performance Optimization:
Fine-tuning the game for better performance across different hardware configurations would make it more accessible to a wider audience.
Conclusion
In summary, the outcome of this project is multifaceted. Not only did I create a functional, enjoyable, and visually impressive game, but I also grew significantly as a developer. The systems I implemented—ranging from AI behavior to combat mechanics—came together to deliver a cohesive and compelling player experience. More importantly, this project has laid a strong foundation for my future as a game developer, equipping me with the skills, confidence, and ambition to push boundaries and create even more exciting projects.



## Critical Reflection
Embarking on this Unreal Engine 5 project has been a transformative experience, marking a significant milestone in my journey as a game developer. As the first game I am genuinely proud of, it challenged me to grow in various aspects, including technical skills, problem-solving abilities, and time management. This reflection delves into the personal and professional growth I achieved through this project and how the systems I developed contributed to crafting a compelling game.

Growth in Game Development Skills
One of the most valuable outcomes of this project was the improvement in my overall game development skills. Before starting this project, my experience with tools like Unreal Engine was limited to basic tutorials and smaller experiments. However, designing a complete game required me to move beyond the basics and delve into advanced systems, such as behavior trees, animation blueprints, Niagara Fluids, and HUD integration.

Technical Mastery: Developing complex systems like the behavior tree for enemy AI and the sword tracing system for melee combat taught me how to combine multiple Unreal Engine tools effectively. For example, linking animation notifies with combat logic to synchronize enemy attacks provided a deep understanding of how various systems interact within the engine.

Niagara Fluids: Crafting visually stunning magic effects using Niagara Fluids improved my proficiency in creating impactful visual effects. This skill not only added polish to my game but also gave me confidence in tackling future challenges related to real-time particle systems.

System Integration: I learned the importance of integrating different gameplay elements into a cohesive whole. For example, the HUD seamlessly displayed the player’s health and stamina in real-time, while the AI interacted dynamically with the player’s actions, making the game feel immersive and reactive.

Problem-Solving Skills
Game development is rife with unexpected challenges, and this project was no exception. Each hurdle I encountered demanded creative and analytical problem-solving, which became a significant area of growth.

AI Behavior Challenges: One major challenge was creating AI that felt intelligent and engaging despite being relatively simple. I spent hours debugging behavior tree transitions and ensuring the AI could reliably switch between chase and combat states. By testing and iterating, I refined the system until it felt smooth and responsive, gaining a better understanding of AI design principles.

Sword Tracing Accuracy: Initially, the sword tracing system wasn’t detecting collisions as accurately as I wanted. Fine-tuning the collision settings and syncing the damage logic with animation notifies resolved this issue. This process taught me the value of attention to detail in systems that directly affect gameplay.

Performance Optimization: Balancing the visual quality of Niagara Fluids with real-time performance was another obstacle. Through experimentation, I optimized the particle effects to maintain high-quality visuals without compromising frame rates, ensuring a smooth experience for players.

Each problem I solved during this project reinforced the importance of persistence and adaptability, skills that will undoubtedly serve me well in future projects.

Time Management Skills
Completing this game on a fixed timeline required careful planning and prioritization. Early in the project, I underestimated the time required for certain tasks, such as debugging AI behavior or tweaking animations. However, as the project progressed, I learned to break tasks into smaller, more manageable steps and allocate time accordingly.

Prioritization: I learned to distinguish between core features and optional additions, focusing my efforts on the systems that would have the most significant impact on gameplay. For example, while I initially wanted to include additional enemy types and spell variations, I decided to perfect the skeleton AI and core magic combat system instead.

Task Tracking: Using tools like Trello or simple to-do lists, I kept track of progress and deadlines. This helped me stay organized and avoid being overwhelmed by the scope of the project.

By the end of the project, my time management skills had improved significantly, allowing me to deliver a polished and complete game within the available timeframe.

Creating a Compelling Game
The systems I developed came together to create an engaging and immersive gameplay experience, making this project the first game I am truly proud of. The AI behavior, magic combat system, and responsive HUD worked in harmony to provide players with a sense of challenge and satisfaction. Here’s how these elements contributed to the game’s overall appeal:

Dynamic and Reactive Gameplay: The behavior tree AI ensured that skeleton enemies felt alive and threatening, constantly pursuing and attacking the player. This added a layer of tension and excitement to the gameplay, as players had to think strategically to survive.

Impactful Combat: The sword tracing system made melee interactions precise and rewarding, while the magic combat system allowed players to unleash visually stunning spells. Together, these elements created a combat experience that was both engaging and satisfying.

Immersive Presentation: The HUD provided real-time feedback on health and stamina, ensuring players remained connected to their character’s status during intense battles. Coupled with the atmospheric visual effects of Niagara Fluids, the game’s presentation elevated its overall quality.

For the first time, I created a game that felt cohesive and enjoyable, from the mechanics to the visuals. Seeing the various systems I implemented come together into a complete and polished product was immensely rewarding.

Reflections on Pride and Future Goals
This project marked a turning point in my journey as a game developer. Unlike my previous attempts, which often felt incomplete or unpolished, this game represents the culmination of my efforts to create something meaningful. I am proud not only of the technical achievements but also of the growth I experienced along the way.

Moving forward, I aim to build on this foundation by tackling more ambitious projects. Future goals include:

Expanding AI systems to include more complex behaviors, such as teamwork or environmental interactions.
Enhancing gameplay depth by introducing mechanics like enemy weaknesses, player upgrades, or advanced spellcasting.
Optimizing performance further to ensure smooth gameplay across a wider range of hardware.
This project has not only solidified my passion for game development but also provided me with the skills and confidence to pursue larger and more challenging endeavors.

In conclusion, this project was a transformative experience that significantly improved my skills in game development, problem-solving, and time management. The systems I implemented helped create a compelling and immersive game, making it the first project I am genuinely proud of. I look forward to building on this success and continuing to grow as a developer.

##Future Improvements
As I reflect on the development of this game and its potential, I am excited to explore opportunities for expansion and enhancement. The core systems I have implemented provide a strong foundation, but there are many areas where I can add depth, variety, and complexity to elevate the overall experience. Below are the specific features and improvements I plan to implement in the future:

Enhancements to Magic Combat
Magic combat is a central aspect of the game, and expanding its functionality can add depth and strategic options for players. Planned improvements include:

New Spells and Abilities:

Introduce a variety of new spells, such as area-of-effect attacks, healing abilities, defensive shields, and elemental magic (e.g., fire, ice, and lightning).
Each spell could have unique visual effects, cooldowns, and resource costs, encouraging players to experiment with different playstyles.
Spell Customization:

Allow players to upgrade and modify spells, adding mechanics like increased damage, larger areas of effect, or reduced stamina cost. This would give players a sense of progression and control over their combat abilities.
Combo Mechanics:

Add a combo system where chaining specific spells together yields powerful effects, rewarding skillful and strategic gameplay.
Environmental Interactions:

Enable spells to interact with the environment (e.g., setting objects on fire, freezing water, or breaking obstacles). This would make combat more dynamic and immersive.
Improved Enemy Behavior
Enhancing enemy AI is critical for creating a more challenging and engaging gameplay experience. Planned upgrades include:

Advanced AI States:

Expand the existing AI behavior tree to include new states such as patrolling, evading, guarding, and retreating.
Introduce adaptive behavior where enemies respond dynamically to the player’s actions, such as grouping together to flank or retreating when low on health.
Unique Combat Styles:

Design AI to reflect different combat styles, such as aggressive enemies that rush the player, defensive enemies that block and counterattack, and ranged enemies that keep their distance.
Enemy Synergy:

Implement cooperative behavior among enemies, such as ranged units providing cover fire for melee attackers or healers buffing other enemies. This would add layers of strategy to encounters.
New Enemy Types
Variety in enemy types can greatly enhance the challenge and excitement of the game. Planned additions include:

Elite Enemies:

Introduce stronger, more complex enemies with unique abilities, such as shielded skeletons, mages, or berserkers.
Boss Fights:

Create boss battles that test the player’s skills and provide memorable, climactic moments. Bosses could feature multi-phase fights with changing attack patterns and vulnerabilities.
Creature Diversity:

Expand the enemy roster to include non-skeletal creatures, such as ghosts, ghouls, or giant beasts, each with distinct behaviors and attack styles.
Level Expansion
Expanding the level design is essential for keeping the game fresh and engaging. Planned improvements include:

New Maps:

Design additional maps with unique themes, such as a haunted forest, ancient ruins, or a fiery volcanic landscape. Each map would feature its own challenges and environmental mechanics.
Expanded Current Level:

Add hidden areas, shortcuts, and secrets to the existing level to encourage exploration and reward curiosity.
Dynamic Environments:

Introduce dynamic elements like traps, destructible objects, and environmental hazards that change how players approach combat and navigation.
Level-Up and Progression System
Adding a level-up system would give players a sense of progression and ownership over their character’s development. Key features include:

Experience Points (XP) System:

Reward players with XP for defeating enemies and completing objectives. Accumulated XP would allow players to level up and grow stronger.
Skill Tree:

Introduce a skill tree where players can unlock new abilities or improve existing ones, such as increasing spell damage, reducing cooldowns, or enhancing stamina regeneration.
Stat Upgrades:

Allow players to allocate points to core stats like health, stamina, or magic power, offering personalized progression.
Additional Features for Immersion and Gameplay Depth
Quests and Objectives:

Add side quests or mini-objectives that provide rewards and give players additional reasons to explore the game world.
Multiplayer or Co-op Mode:

Explore the possibility of adding multiplayer functionality, allowing players to team up against waves of enemies or compete for high scores.
Achievements and Leaderboards:

Implement an achievement system and leaderboards to encourage replayability and competition among players.


## Bibliography
Best Practices for Creating and Managing Widgets | UI | Widgets | HUD |  Unreal Engine 5 Tutorial (2023) At: https://www.youtube.com/watch?v=7b7a20j0azc (Accessed  30/11/2024).
Unreal Engine 5 Tutorial -  Animation Blueprint Part 1: State Machines (2023) At: https://www.youtube.com/watch?v=etRZu5UG_S0 (Accessed  30/11/2024).
Unreal Engine 5 RPG Tutorial Series - #10: Sword Trace Damage and Hit Reactions (2023) At: https://www.youtube.com/watch?v=zbbWk851IXk (Accessed  30/11/2024).
Unreal Engine 5 Tutorial - Animation Notifies (2022) At: https://www.youtube.com/watch?v=2Su20IGg0tw (Accessed  30/11/2024).
Niagara Fluids Smoke Portal VFX Tutorial in Unreal Engine 5.3 | Real-Time Simulation | RedefineFX (2024) At: https://www.youtube.com/watch?v=nOirmGz8YG4 (Accessed  30/11/2024).
Smart Enemy AI | (Part 1: Behavior Trees) | Tutorial in Unreal Engine 5 (UE5) (2023) At: https://www.youtube.com/watch?v=-t3PbGRazKg (Accessed  30/11/2024).



ChatGPT (s.d.) At: https://chatgpt.com (Accessed  10/10/2024).


## Declared Assets

Modular Asian Medieval City | Fab (s.d.) At: https://www.fab.com/listings/cebef7c2-a093-42e0-a3ce-dcd7c06317da (Accessed  30/11/2024).
-
Mixamo (s.d.) At: https://www.mixamo.com/#/ (Accessed  10/10/2024).
-
Browse Fonts (s.d.) At: https://fonts.google.com/ (Accessed  10/11/2024).
-
Free Sound Effect Categories (s.d.) At: https://www.zapsplat.com/sound-effect-categories/ (Accessed  26/10/2024).
-
shield guard | Royalty-free Music (s.d.) At: https://pixabay.com/sound-effects/shield-guard-6963/ (Accessed  30/11/2024).
-
Mega Magic VFX Bundle (s.d.) At: https://www.fab.com/listings/d0b1351a-acbf-4da6-ab4e-32fc934a255f (Accessed  30/11/2024).
-
Leonardo.Ai (s.d.) At: https://app.leonardo.ai/?via=jaji&gad_source=1&gclid=CjwKCAiAjKu6BhAMEiwAx4UsAvZnWnDyodT23t-nH01L45UJk3sCPQny-1QNPNjih50xCKXc4jwnyBoC48EQAvD_BwE (Accessed  30/11/2024).
-
Jacquard 24 (s.d.) At: https://fonts.google.com/specimen/Jacquard+24 (Accessed  30/11/2024).
-
Money free icon designed by Umeicon (s.d.) At: https://www.flaticon.com/free-icon/money_2806415?term=coin&page=2&position=90&origin=search&related_id=2806415 (Accessed  30/11/2024).
-
Fire free icon designed by Freepik (s.d.) At: https://www.flaticon.com/free-icon/fire_785116?term=fire&page=1&position=1&origin=search&related_id=785116 (Accessed  30/11/2024).
-




The following assets were created or modified with the use of GPT 4o:
- Development Journal.html
