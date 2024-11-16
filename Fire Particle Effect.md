# [Fire Particle Effect]



Bora Tibet Ozdemir

2221180

## Research
Creating visually dynamic effects is an essential aspect of game design, and Unreal Engine 5’s Niagara Particle System offers powerful tools for crafting complex particle behaviors. For this project, I developed a fireball particle effect by modifying the Niagara Fountain emitter. My approach was informed by the following resources:

Video Tutorial-Fire Simulation FX in Unreal Engine Niagara | in 12 minutes (2023)
YouTube Video (Accessed 15/11/2024).
This tutorial provided a concise walkthrough of key techniques to create fire-like effects in Niagara, including velocity adjustments, drag implementation, and the use of color curves for optimal visual results.
Epic Games Documentation-Overview of Niagara Effects for Unreal Engine | Unreal Engine 5.5 Documentation | Epic Developer Community
Epic Games Documentation (Accessed 15/11/2024).
This resource provided a comprehensive overview of Niagara’s core functionalities, including emitter properties, forces, and material integrations to achieve advanced visual effects.
Key Insights-
The Niagara Particle System is a versatile tool that allows developers to fine-tune particle behaviors and visuals. Key techniques utilized in this project include:

Emitter Customization: The Fountain emitter serves as a base for creating upward particle motion, ideal for effects like flames or projectiles.
Color Gradients: Curves allow precise control over particle color transitions, critical for creating lifelike fire effects.
Forces and Physics: Curl Noise forces add randomness, simulating turbulent movement typical of fire.
Material Integration: Using a fire-specific material enhances the visual realism of the particles.











## Implementation

Creative and Technical Approaches
To create the fireball particle effect, I leveraged Niagara’s modular design and iterative workflow to customize the Fountain emitter as follows:

1. Base Emitter Selection and Setup
I began by selecting the Niagara Fountain emitter as a starting point. This emitter's default upward motion served as an ideal base for the fireball’s flaming effect.

2. Emitter Property Modifications
Several key properties of the emitter were adjusted to simulate realistic fire behavior:

Velocity:
Increased the initial velocity range to create faster-moving particles, mimicking the dynamic, upward motion of flames.

Lifetime Mode:
Switched to a randomized lifetime range, ensuring that particles extinguished at varying intervals for a more natural effect.

Gravity:
Disabled gravity to prevent particles from falling back, maintaining the upward flow characteristic of fire.

Drag:
Increased drag forces to slow particle motion over time, giving the flames a smooth and cohesive appearance.

3. Visual Enhancements
To enhance the visual fidelity of the fireball, I implemented several techniques:

Color Curve:
Added a gradient that transitions from bright orange at particle birth to pale yellow before fading out. This mimicked the appearance of flames cooling and dissipating over time.

Scale by Sprite Size:
Enabled dynamic scaling of particles, ensuring they expanded as they moved upwards and shrank before fading, simulating the combustion process.

4. Forces and Randomization
To introduce realistic randomness and turbulence to the fireball’s motion:

Curl Noise Force:
Added a curl noise force to create irregular, swirling motion, enhancing the organic, chaotic nature of fire.
5. Material Integration
Finally, I applied the M_FireUV material from the UE5 Starter Content as the particle sprite texture. This material, designed for fire effects, added fine details such as flickering patterns and gradients, greatly enhancing the overall realism of the fireball.
~
<iframe width="560" height="315" src="https://www.youtube.com/embed/qFvSdweBHEI?si=vDvfVKmmvoLCPblj" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>



## Outcome
The final fireball particle system featured dynamic motion, lifelike color transitions, and responsive scaling that effectively simulated a flaming projectile.

Visual Quality
Realism:
The combination of curl noise, color gradients, and the fire-specific material created a convincing fireball effect suitable for fantasy or action games.

Dynamic Behavior:
Particles moved organically, with varied lifetimes and turbulence, capturing the unpredictable nature of flames.

Performance
The system was optimized for performance, ensuring that it could run smoothly even in scenes with multiple instances of the fireball effect. This was achieved by balancing particle count, drag forces, and material resolution.



## Critical Reflection
Strengths
Customization:
Niagara’s flexibility allowed me to fine-tune every aspect of the fireball effect, from motion to visual details.

Visual Impact:
The final system successfully mimicked a realistic fireball, with natural movement and vibrant colors.

Limitations
Collision and Interactivity:
The current implementation lacks collision detection, preventing the fireball from interacting with other game objects.

Post-Processing Effects:
While the fireball effect itself is realistic, additional effects like heat distortion and light emission could further enhance immersion.

##Future Improvements
To enhance the fireball’s realism and interactivity, I plan to:

Add Collision Events:
Enable the fireball to interact with the environment, triggering secondary effects like explosions or smoke.

Implement Heat Distortion:
Use post-processing materials to simulate the distortion caused by heat around the fireball.

Incorporate Light Emission:
Integrate dynamic lighting to illuminate the surrounding environment, adding another layer of realism.

## Bibliography
Overview of Niagara Effects for Unreal Engine | Unreal Engine 5.5 Documentation | Epic Developer Community (s.d.) At: https://dev.epicgames.com/documentation/en-us/unreal-engine/overview-of-niagara-effects-for-unreal-engine (Accessed  16/11/2024).
-
Creating Visual Effects in Niagara for Unreal Engine | Unreal Engine 5.5 Documentation | Epic Developer Community (s.d.) At: https://dev.epicgames.com/documentation/en-us/unreal-engine/creating-visual-effects-in-niagara-for-unreal-engine (Accessed  16/11/2024).
-
Fire Simulation FX in Unreal Engine Niagara | in 12 minutes (2023) At: https://www.youtube.com/watch?v=q8avHL7syC4 (Accessed  16/11/2024).
-
What is Niagara (2022) At: https://cghero.com/glossary/what-is-niagara (Accessed  16/11/2024).
-



ChatGPT (s.d.) At: https://chatgpt.com (Accessed  10/10/2024).






The following assets were created or modified with the use of GPT 4o:
- Development Journal.html
