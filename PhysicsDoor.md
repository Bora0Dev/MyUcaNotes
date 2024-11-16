# [Physics Door]



Bora Tibet Ozdemir

2221180

## Research




Interactive environments are an essential component of immersive gameplay, enabling players to interact with the world in intuitive and meaningful ways. Physics-based systems, such as dynamic doors, add realism by responding naturally to player actions. In Unreal Engine 5, the physics system provides a robust framework for simulating real-world interactions through components like Physics Constraints, which enable detailed control over motion and behavior.

To create a physics-based door, I utilized Unreal Engine 5's Physics Constraint component and configured the door's motion to react realistically to player input. My implementation was informed by the following resources:

Unreal Engine Documentation


This documentation provided an in-depth overview of physics constraints, their parameters, and how they can be applied to achieve controlled physics-driven motion in actors like doors.(Physics Constraint Component User Guide in Unreal Engine | Unreal Engine 5.5 Documentation | Epic Developer Community, s.d.)
YouTube Tutorials

I consulted video tutorials demonstrating physics-based mechanics in Unreal Engine to better understand how to configure constraint settings for interactive gameplay elements. These tutorials served as practical references for implementing swing motion and setting up character interactions.
Key Insights
Physics Constraints
Physics Constraints are pivotal for limiting and controlling the motion of physics-driven actors in Unreal Engine. They simulate realistic joint behavior by restricting movement along specified axes or within defined angular ranges. Key parameters include:

Swing and Twist Motions: Control rotational movement around specific axes.
Angular Drive Mode: Enables dynamic motion based on physical forces such as pushing or pulling.
Simulated Physics
Setting an actor to "Simulate Physics" allows it to interact with forces like gravity and player input. This feature, combined with collision generation, ensures the actor responds realistically to its environment.(How to Make a Physics Door in Unreal Engine 5, 2023)



## Implementation
<iframe width="560" height="315" src="https://www.youtube.com/embed/BMPEsIlKDTE?si=LYWdffHfwHjma21j" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
#

Creative and Technical Approaches
To create the physics-based door, I followed a structured workflow leveraging Unreal Engine 5's physics system.

1. Door Actor Creation
I began by creating a Door Actor blueprint to serve as the container for the door system components. This modular approach allows the door to be reused in multiple instances with consistent behavior.

2. Static Mesh and Collision Setup
Static Mesh:
Added the door asset from Unreal Engine 5’s Starter Content as the static mesh for the Door Actor. This provided a visually realistic door model for the system.
Collision:
Generated a simple box collision for the door. This ensured the door could interact physically with other objects and the player character.
3. Physics Simulation
Enabled "Simulate Physics" for the static mesh, allowing the door to respond naturally to environmental forces, including the player pushing it.

4. Physics Constraint Component
Added a Physics Constraint component to the Door Actor and configured its settings:

Attachment:
Linked the Physics Constraint to the static mesh to control its motion.
Swing 1 Motion:
Limited the Swing 1 axis to 90 degrees, allowing the door to open in the direction of the player’s push.
Swing 2 and Twist Motion:
Locked these motions to prevent unintended rotational behaviors, ensuring the door remains stable.
Angular Drive Mode:
Enabled Twist and Swing and set the strength to 50, providing a balanced resistance and natural motion when pushed.








## Outcome
The final physics-based door system allowed for realistic and interactive behavior.

Functionality
Natural Motion:
The door swung open dynamically in response to the player’s movement, aligning with the direction of the push.
Controlled Limits:
The 90-degree constraint ensured the door opened within a realistic range, preventing unnatural behavior like over-rotation or excessive swinging.
Player Interaction
Intuitive Gameplay:
Players could interact with the door by simply walking into it or applying force, enhancing immersion and realism.
Responsive Feedback:
The physics simulation provided immediate visual feedback, making the interaction feel smooth and natural.



## Critical Reflection
Strengths
Realism:
By simulating physics and applying constraints, the door behaved naturally, contributing to the overall immersion of the environment.
Modularity:
The blueprint-based approach allows the physics door to be easily replicated or modified for use in other projects.
Limitations
Collision Optimization:
The simple box collision worked well but might require refinement for more complex door shapes or scenarios involving detailed interactions.
Limited Interactions:
The current implementation only supports basic pushing interactions. Additional features like locking mechanisms or scripted opening could enhance functionality.
Future Improvements
To enhance the system further, I plan to:

Add Locking and Unlocking Functionality:
Introduce a mechanism to lock the door, requiring specific player actions (e.g., keys) to unlock it.

Integrate Audio and Visual Feedback:
Add sounds and visual cues (e.g., creaking noises or particle effects) to make the interaction more engaging.

Advanced Physics Options:
Experiment with soft constraints or dynamic hinge joints to simulate more complex door behaviors, such as sliding or double-swing doors.



## Bibliography
How to Make a Physics Door in Unreal Engine 5 (2023) At: https://www.youtube.com/watch?v=30G-WJ5aMpA (Accessed  16/11/2024).
-
Physics Constraint Component User Guide in Unreal Engine | Unreal Engine 5.5 Documentation | Epic Developer Community (s.d.) At: https://dev.epicgames.com/documentation/en-us/unreal-engine/physics-constraint-component-user-guide-in-unreal-engine (Accessed  16/11/2024).
-
Physics Constraint Between Character And Physics Object - Programming & Scripting / Blueprint (2022) At: https://forums.unrealengine.com/t/physics-constraint-between-character-and-physics-object/647342 (Accessed  16/11/2024).
-



ChatGPT (s.d.) At: https://chatgpt.com (Accessed  10/10/2024).


## Declared Assets

Modular Asian Medieval City in Environments - UE Marketplace (s.d.) At: https://www.unrealengine.com/marketplace/en-US/product/modular-asian-medieval-city (Accessed 10/10/2024).
Mixamo (s.d.) At: https://www.mixamo.com/#/ (Accessed  10/10/2024).




The following assets were created or modified with the use of GPT 4o:
- Development Journal.html
