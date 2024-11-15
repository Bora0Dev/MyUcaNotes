# [Single Layer Water Material in Unreal Engine 5]



Bora Tibet Ozdemir

2221180

## Research
Realistic water effects play a vital role in creating immersive environments in game design. Unreal Engine 5 (UE5) provides a specialized Single Layer Water shading model designed to simulate thin water surfaces efficiently. My research focused on understanding the implementation of this shading model, informed by two primary resources:

Video Tutorial


This video offered practical, step-by-step instructions for creating a simple water material in UE5. It emphasized using Normal Maps, Base Color, and Panner nodes to simulate realistic water motion and reflections.
How to Make a Simple Water Material in Unreal Engine 5 (2023)

Single Layer Water Shading Model in Unreal Engine | Unreal Engine 5.5 Documentation | Epic Developer Community
Epic Games Documentation (Accessed 15/11/2024).
This documentation provided a theoretical understanding of the Single Layer Water shading model, detailing its properties and optimal usage scenarios.
Key Insights
The Single Layer Water shading model is designed for flat, thin water surfaces, such as puddles, lakes, and oceans. Unlike volumetric water shaders, it does not simulate subsurface scattering, making it lightweight and efficient.

Core Features:
Refraction: Simulates the bending of light through the water surface.
Specular Highlights: Enhances reflective properties.
Normal Maps: Adds dynamic wave and ripple patterns.
Transparency: Allows for depth effects based on the water's Base Color.
This shading model offers a robust balance between performance and realism, making it ideal for interactive environments in games

The Single Layer Water shading model is designed for flat, thin water surfaces, such as puddles, lakes, and oceans. Unlike volumetric water shaders, it does not simulate subsurface scattering, making it lightweight and efficient.

Core Features:
Refraction: Simulates the bending of light through the water surface.
Specular Highlights: Enhances reflective properties.
Normal Maps: Adds dynamic wave and ripple patterns.
Transparency: Allows for depth effects based on the water's Base Color.
This shading model offers a robust balance between performance and realism, making it ideal for interactive environments in games.




## Implementation
Creative and Technical Approaches
To create a realistic water material, I followed these steps:

Material Setup

Selected Single Layer Water as the shading model in UE5’s Material Editor.
Configured Base Color to simulate depth by blending a gradient of deep blue and green tones.
Normal Maps for Ripples

Imported a tiling Normal Map texture to simulate waves.
Used a Panner Node to animate the Normal Map, creating dynamic motion.
Refraction and Lighting

Adjusted the Refraction Index to 1.33, mimicking realistic water properties.
Enhanced specular properties to reflect sunlight and environmental lighting.
Transparency

Controlled opacity based on camera distance, providing a seamless blend with the surrounding environment.

<iframe src="https://blueprintue.com/render/mgjrds62/" scrolling="no" allowfullscreen></iframe>
-

<iframe width="560" height="315" src="https://www.youtube.com/embed/cBWJ7vyFdfs?si=WQedrNzsz_B3kdcV" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
-



## Outcome
The implemented water material demonstrated:

Realism: Refraction, lighting, and Normal Maps combined to create visually compelling water effects.
Efficiency: Achieved high performance with minimal resource usage.
The material was suitable for a variety of environments, from tranquil lakes to dynamic rivers, ensuring versatility in game development.


## Critical Reflection
The Single Layer Water shading model provided an accessible yet powerful framework for water simulation.

Strengths
Easy to implement and customize.
Effective for thin, shallow water surfaces.
Limitations
Lacks support for volumetric effects like subsurface scattering or underwater light diffusion.
Requires additional materials or post-processing to simulate foam or shoreline interactions.
Future Improvements
Explore integration with Caustics Generator plugins for enhanced light patterns.
Investigate techniques for realistic shoreline foam using complementary particle systems.

Dynamic Water Movement

Challenge: Ensuring natural wave patterns without noticeable repetition.
Solution: Combined multiple Normal Maps with different scales and panning speeds to create a layered effect.
Performance Optimization

Challenge: Maintaining smooth frame rates while using detailed textures.
Solution: Reduced Normal Map resolution and optimized material parameters for efficient rendering.


## Bibliography

Single Layer Water Shading Model in Unreal Engine | Unreal Engine 5.5 Documentation | Epic Developer Community (s.d.) At: https://dev.epicgames.com/documentation/en-us/unreal-engine/single-layer-water-shading-model-in-unreal-engine (Accessed  15/11/2024).
-

How to Make a Simple Water Material in Unreal Engine 5 (2023) At: https://www.youtube.com/watch?v=o6f7n4UhYq0 (Accessed  15/11/2024).
-

ArtStation - Water Shader - Single Layer Material (2023) At: https://www.artstation.com/blogs/rovana_c/poGo/water-shader-single-layer-material (Accessed  15/11/2024).
-






The following assets were created or modified with the use of GPT 4o:
- Development Journal.html
