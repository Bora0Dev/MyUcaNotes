# [Anti-Aliasing]



Bora Tibet Ozdemir

2221180

## Research





In modern game development, anti-aliasing (AA) plays a crucial role in improving visual quality by smoothing out jagged edges (aliasing) that appear on rendered objects. However, different anti-aliasing techniques come with their own trade-offs between visual fidelity and performance. My research focused on various anti-aliasing methods, how they impact performance and quality, and their optimal implementation in Unreal Engine 5 (UE5).

1. Overview of Anti-Aliasing Methods
There are several prominent anti-aliasing techniques used in real-time rendering, each offering a different balance between image quality and computational cost:

MSAA (Multisample Anti-Aliasing): One of the oldest methods, MSAA samples multiple points within each pixel to smooth out edges. While it offers decent quality, it tends to be computationally expensive, especially in deferred rendering environments like UE5.

FXAA (Fast Approximate Anti-Aliasing): FXAA is a post-processing technique that blurs jagged edges by analyzing contrast in the image. It's extremely fast and light on performance but can lead to a soft, less detailed final image, particularly in high-contrast scenes.

TAA (Temporal Anti-Aliasing): TAA is a more advanced method that utilizes information from multiple frames over time to reduce aliasing. While it provides better results than FXAA, it can introduce motion blur or ghosting artifacts if not properly calibrated. In UE5, TAA is one of the most widely used AA methods due to its balance between quality and performance.

DLSS (Deep Learning Super Sampling): Leveraging AI and NVIDIA's GPUs, DLSS uses a neural network to upscale lower-resolution images while maintaining high visual quality. It's an advanced solution that can significantly boost performance while maintaining (or even improving) image quality, but it’s only available on supported hardware.


In my research on anti-aliasing in Unreal Engine 5, I focused on the documentation provided by Epic Games regarding TAA (Temporal Anti-Aliasing) and TSR (Temporal Super Resolution). The source provided valuable insights into how Unreal Engine handles these techniques natively and offered practical commands for fine-tuning TAA. I also explored how TSR can be implemented to balance performance and quality, with a particular emphasis on how the engine utilizes temporal data to upscale rendering while maintaining image clarity. The benchmarks comparing different anti-aliasing methods, especially between TAA and TSR, were useful in understanding the trade-offs for various hardware setups and game types.

I found the documentation on TAA and TSR in Unreal Engine 5 to be comprehensive and well-structured, especially in terms of explaining the trade-offs between visual quality and performance. TAA was well-explained, with practical examples of its settings and how they affect ghosting and blurring, but I felt that more examples on optimizing TAA for specific scene types, such as fast-moving or high-detail environments, could have been provided. I appreciated the detailed explanation of TSR, which provided a clear understanding of how it improves performance by rendering at a lower resolution and then upscaling using temporal data to produce a high-quality output.

While I agreed with the general recommendation of TAA for most projects due to its balanced performance-to-quality ratio, I found TSR to be a more versatile solution, particularly because it doesn’t rely on specific hardware (unlike DLSS). However, I would have liked more discussion in the documentation about the potential downsides of TSR, such as how it handles extreme motion or high-complexity scenes. In contrast to TAA, which can be more predictable but sometimes results in ghosting, TSR’s advanced upscaling might not always deliver the sharpest image in every scenario.

To supplement my understanding, I plan to explore additional third-party guides and community discussions on fine-tuning TSR for different platforms, as well as how TAA can be optimized in highly dynamic environments.
# Example Documentation

Certainly! Here’s the revised version, tailored to improving the quality of your Undead Samurai game by implementing TAA and TSR anti-aliasing methods:

In an effort to enhance the visual quality of my Undead Samurai game, I focused on implementing and fine-tuning Temporal Anti-Aliasing (TAA) and Temporal Super Resolution (TSR) within Unreal Engine 5. Both anti-aliasing techniques were essential to achieving sharper and more polished visuals while maintaining smooth performance, especially in a game like Undead Samurai, where the atmosphere is dark, and fast-paced combat can introduce visual noise or aliasing issues. To better understand and apply these methods, I referred to the Unreal Engine Blueprints API References and Unreal Engine 5 Documentation (Unreal Engine Blueprint API Reference | Unreal Engine 5.4 Documentation | Epic Developer Community, s.d.).

I found that implementing both TAA and TSR significantly improved the visual fidelity of my game. The smooth, high-quality rendering of dynamic scenes and the reduction of aliasing made the game’s fast combat and atmospheric environments more immersive. However, I plan to further explore community resources and third-party tutorials to optimize these settings for different hardware configurations, ensuring Undead Samurai performs well across various platforms while retaining its visual quality.
# Example Game Source

Just Cause 3 is an action-adventure game developed by Avalanche Studios, it features a mechanic where the player can navigate the open world with the use of a parachute and a wingsuit(Just Cause 3, 2015).

The wind becomes more prominent in the mix and its volume and speed is based on the player's velocity when using the wingsuit or parachute. It is not too overwhelming during action sequences to ensure audio responses can be clearly heard.

I found their implementation and choice great for the context of their narrative and game mechanics. However, for the sequences featured in the assignment, it is more “cinematic” allowing for a different approach for the mix and can be “exaggerated” to drive its narrative function.




## Implementation

<html>
<body>

<iframe width="1280" height="720" src="https://www.youtube.com/embed/NbYD3lNKyrQ" title="Anti Aliasing methods Unreal Engine test" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</body>
</html>

g UE5UndeadSamurai.html…]()



*Figure 1. An example of using a script as a figure. This script has a `Start()` method!*

### What creative or technical approaches did you use or try, and how did this contribute to the outcome?





## Outcome
After testing both TAA and TSR in my Undead Samurai game, I ultimately decided to use TAA over TSR. While TSR delivered superior visual quality, the performance trade-off was simply not worth it. Implementing TSR resulted in a significant frame rate drop of 30 FPS, which negatively impacted the gameplay experience, especially during action-heavy sequences. Although TAA doesn't offer quite the same level of sharpness as TSR, it still provides a strong balance between visual fidelity and performance, maintaining smoother gameplay while delivering good image quality. Given the fast-paced nature of Undead Samurai, ensuring consistent frame rates is critical, and TAA allowed me to achieve that without compromising too much on visuals.



## Critical Reflection
After testing TAA and TSR in Undead Samurai, I chose TAA due to performance concerns. While TSR produced sharper visuals, it resulted in a 30 FPS drop, which significantly affected gameplay, especially in fast-paced combat sequences. Although TAA isn’t as visually crisp, it provided a much better balance between image quality and performance, maintaining a smooth and responsive experience.

This process taught me that, while visual fidelity is important, performance takes priority in action-heavy games like Undead Samurai. A slight reduction in graphical quality is an acceptable trade-off if it ensures consistent gameplay, and TAA offered that balance. Going forward, I will continue optimizing for both visuals and performance, but my priority will always be the player experience.

### What did or did not work well and why?
During testing, FXAA (Fast Approximate Anti-Aliasing) didn’t perform well for Undead Samurai. While it is lightweight and didn’t impact performance much, the image quality suffered. FXAA tended to blur fine details, especially in the game’s complex textures and dark environments, leading to a less crisp and polished look. The lack of clarity was especially noticeable during fast-paced combat, where sharp visuals are essential to maintaining immersion and focus.

In contrast, TAA (Temporal Anti-Aliasing) worked much better. It effectively reduced jagged edges and maintained better image sharpness compared to FXAA, while still balancing performance. While TAA can sometimes introduce blurring or ghosting in fast-moving scenes, these issues were minimal after fine-tuning its settings. This made TAA the superior choice, providing a smoother and visually pleasing experience without significantly affecting the game's performance.

### What would you do differently next time?

- Are there any new approaches, methodologies or different software that you wish to incorporate if you have another chance?
- Is there another aspect you believe should have been the focus?

## Bibliography

Temporal Super Resolution in Unreal Engine | Unreal Engine 5.5 Documentation | Epic Developer Community (s.d.) At: https://dev.epicgames.com/documentation/en-us/unreal-engine/temporal-super-resolution-in-unreal-engine (Accessed 10/10/2024).
Gameinspired (2021) UE4 — TemporalAA vs FXAA. At: https://gameinspired-mail.medium.com/ue4-temporalaa-vs-fxaa-4ae71d3e89b6 (Accessed  10/10/2024).
Anti Aliasing and Upscaling in Unreal Engine | Unreal Engine 5.5 Documentation | Epic Developer Community (s.d.) At: https://dev.epicgames.com/documentation/en-us/unreal-engine/anti-aliasing-and-upscaling-in-unreal-engine (Accessed  10/10/2024).
ChatGPT (s.d.) At: https://chatgpt.com (Accessed  10/10/2024).


## Declared Assets

Modular Asian Medieval City in Environments - UE Marketplace (s.d.) At: https://www.unrealengine.com/marketplace/en-US/product/modular-asian-medieval-city (Accessed 10/10/2024).
Mixamo (s.d.) At: https://www.mixamo.com/#/ (Accessed  10/10/2024).




The following assets were created or modified with the use of GPT 4o:
- Development Journal.html
