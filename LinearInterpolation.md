# [Linear Interpolation]



Bora Tibet Ozdemir

2221180

## Research





To create smooth texture transitions in my project, I focused on Unreal Engine's Blueprint system, using the Linear Interpolation (Lerp) node combined with a Sine function for dynamic texture blending. Instead of referring to Unreal's official documentation (as I couldn't find specific material on this topic), I relied on YouTube tutorials to guide me through the process. YouTube, with its wide variety of visual and step-by-step content, provided a much easier way to learn this particular technique.

I followed a tutorial by [Hoj Dee] that demonstrated how to use the Lerp node to switch between two textures. The Lerp node works by interpolating between two input textures based on a float value, known as the alpha. The alpha value determines the blend, with 0 representing one texture and 1 representing the other. To make the transitions smoother and more visually interesting, I added a Sine function to control the alpha input. The sine wave oscillates between -1 and 1, but by scaling and offsetting it, I was able to have the alpha move between 0 and 1, creating a rhythmic pulsing or fading effect between the two textures.Linear |Interpolate or Lerp Node EXPLAINED! Unreal Engine Materials| (2024) At: https://www.youtube.com/watch?v=tBib8qQxd1M (Accessed  20/10/2024).


This setup allowed me to achieve a seamless, natural-looking transition between the textures. The combination of the Lerp node and the Sine function provided a flexible system that can be used for various effects, such as day-night cycles or dynamic material changes based on environmental conditions. By adjusting the frequency and amplitude of the sine wave, I can easily control the speed and intensity of the texture transition.

The tutorial was invaluable for learning this technique, as it provided a clear, hands-on approach that I could follow at my own pace. I did wish, however, that it had gone into more detail about how to customize the sine wave for specific use cases. Despite this, the flexibility of combining the Lerp node with the Sine function opened up a lot of possibilities for dynamic material manipulation in my project, without needing to write complex code.
# Example Documentation

Certainly! Here’s the revised version, tailored to improving the quality of your Undead Samurai game by implementing TAA and TSR anti-aliasing methods:

In an effort to enhance the visual quality of my Undead Samurai game, I focused on implementing and fine-tuning Temporal Anti-Aliasing (TAA) and Temporal Super Resolution (TSR) within Unreal Engine 5. Both anti-aliasing techniques were essential to achieving sharper and more polished visuals while maintaining smooth performance, especially in a game like Undead Samurai, where the atmosphere is dark, and fast-paced combat can introduce visual noise or aliasing issues. To better understand and apply these methods, I referred to the Unreal Engine Blueprints API References and Unreal Engine 5 Documentation (Unreal Engine Blueprint API Reference | Unreal Engine 5.4 Documentation | Epic Developer Community, s.d.).

I found that implementing both TAA and TSR significantly improved the visual fidelity of my game. The smooth, high-quality rendering of dynamic scenes and the reduction of aliasing made the game’s fast combat and atmospheric environments more immersive. However, I plan to further explore community resources and third-party tutorials to optimize these settings for different hardware configurations, ensuring Undead Samurai performs well across various platforms while retaining its visual quality.
# Example Game Source






## Implementation



### What creative or technical approaches did you use or try, and how did this contribute to the outcome?


I used the Sine node in Unreal Engine to create a dynamic and visually engaging material that smoothly transitions between two textures. By feeding the output of the Sine node into the Lerp node’s alpha input, I was able to create a rhythmic, oscillating effect between the two textures. The sine wave naturally fluctuates between values, which made the blending feel fluid and organic, creating a pulsing effect that was both eye-catching and responsive to in-game conditions.

<iframe src="https://blueprintue.com/render/db569jl6/" scrolling="no" allowfullscreen></iframe>

<iframe width="560" height="315" src="https://www.youtube.com/embed/XCaNEkDLiag?si=Es82W5f-fqlevLLD&amp;start=1" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


## Outcome
The outcome of using the Sine node in combination with the Lerp node to blend two textures was a dynamic and visually captivating material that added depth to the game’s visuals. The smooth oscillation created by the sine wave allowed for a continuous and rhythmic transition between textures, giving the material a "living" quality. This effect enhanced the overall aesthetic by drawing attention to certain elements, making them stand out more effectively.

The technique proved to be highly adaptable, as I could easily adjust the speed and intensity of the transitions based on different gameplay scenarios. This resulted in a polished and professional-looking material that contributed to the immersive experience of the project, making the visual elements more interactive and responsive to the game’s environment.


## Critical Reflection
In reflecting on the use of the Sine node and Lerp function to create dynamic material transitions, I found the technique to be both effective and versatile, but not without challenges. The use of a sine wave to drive texture blending introduced an organic and visually engaging effect, making the material feel more interactive and alive. However, while the result was aesthetically appealing, it required significant fine-tuning to achieve the desired effect, particularly in controlling the speed and amplitude of the transitions.

One limitation I encountered was the lack of precision when using the Sine node for specific timing or controlled effects. The oscillation was smooth, but not always ideal for situations where a more linear or predictable transition was needed. Additionally, this method works best for materials that benefit from a continuous, rhythmic change, but may not be as effective for more abrupt or event-driven transitions.

On the positive side, the process deepened my understanding of Unreal Engine’s material editor, specifically how nodes like Sine and Lerp can be used creatively to enhance game visuals. It also highlighted the importance of experimenting with different parameters to tailor the effect to the game's needs. Overall, while the technique worked well for the context of this project, I recognize that alternative approaches may be better suited for different visual or gameplay scenarios.





## Bibliography

Linear Interpolate or Lerp Node EXPLAINED! Unreal Engine Materials (2024) At: https://www.youtube.com/watch?v=tBib8qQxd1M (Accessed  20/10/2024).
-


Sine, Append, Abs & Lerp (2017) At: https://jesshiderue4.wordpress.com/material-basics/sine-append-abs-and-lerp/ (Accessed  20/10/2024).
-

