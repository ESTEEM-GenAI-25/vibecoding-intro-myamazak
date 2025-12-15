# 🧭 Implementation & Ethics Memo
**Project:** RouteMark – AI-Enhanced Engraved Travel Cards  
**Author:** Masafumi Yamazaki  
**Date:** December 2025  

---

## How I Actually Used AI While Building

When I started working on RouteMark, I didn’t have a full technical plan. I had a mental image of a black aluminum card showing a curved line between two cities. I wanted it to look elegant, like something that could be physically engraved. To get there, I used AI mostly as a *thinking partner* rather than a black box that wrote the whole code for me.  

I worked mainly with **VS Code** and **Gemini**. I asked them to help me with HTML and JavaScript setup, the OpenLayers map functions, and the logic for drawing curved routes. The AI helped me quickly sketch out the structure, but the code it produced often needed manual fixing; coordinates were off and the map projection didn’t behave the way I expected. I spent a lot of time iterating on the modification.

For the user interface, I used AI more like a design assistant. It gave me layout ideas for the sidebar, buttons, and the card preview area. However, most of the visual tuning (spacing, alignment, and how “engraved” the map looked) came from my own experimentation. I realized AI was good at getting me to about 60% of the way there, but finishing the design always required human judgment.  
 

---

## Why the AI Feature in the Product Looks the Way It Does

Early in the project, I imagined a more ambitious AI feature. Maybe one that could automatically design the card’s layout or generate a photo-realistic engraving preview. But as I built more of the product, I realized that would distract from the real goal: creating a clean, believable memento of a journey.  

That’s why I decided the AI feature should be *interpretive*, not generative. Instead of making images or random designs, it will eventually focus on **describing the route in a meaningful way**. For example, if someone chooses “Tokyo – New York” with a “Premium” vibe, AI could write a short note about the character of that journey or why the line appears bold and bright. It’s a way of adding emotional context to something geometric.  

This approach felt right for the kind of product I was making. RouteMark isn’t about showing off AI—it’s about combining technology and craftsmanship. I wanted AI to support the storytelling side without taking over the visual identity of the product. The design should still feel like it could exist as a real, laser-engraved object, not just a digital experiment.  

I also kept the scope small on purpose. Generating complex visuals through AI image models could easily raise questions about originality or ownership. By keeping AI’s role narrow — explaining style choices or recommending line aesthetics — the product stays more transparent and easier to trust.

---

## Risks, Trade-offs, and Integrity

I thought a lot about privacy, bias, and trust during development. Even though RouteMark doesn’t collect personal data, it still takes user input that reflects real travel routes. I decided to keep everything client-side and avoid sending user data to external AI services until I can guarantee proper filtering. In the future, if I connect to an API like Gemini, I’ll make sure the route text is stripped down to just the city names before it’s sent anywhere.  

Bias is another issue I had to think about. If AI writes descriptions like “Tokyo – New York represents ambition,” that’s still a subjective statement that can reflect cultural assumptions. I plan to handle that by constraining prompts so they focus on neutral tone and avoid stereotypes. AI should describe the *style* of the design, not the meaning of the cities or people involved.  

I also made sure that AI is not essential for the app to work. The main features — drawing the route, stitching the coastlines, showing the card preview, and adding to cart — all work independently. If the AI feature stops working, the app should still function. This helps prevent users from being forced to rely on AI where it isn’t necessary.  

Finally, I want to be transparent about academic integrity. Every time I used AI, I edited the results, understood the logic, and rewrote large sections myself. The AI helped me learn new techniques faster, but it never replaced my own reasoning. In that sense, I see AI as a modern extension of open-source culture — it gives you pieces, but you still have to assemble them into something that’s yours.

---

## What I Learned About Building with GenAI

The biggest thing I learned from using AI was how much *direction* matters. When I gave vague prompts like “make a modern UI,” the results were random and usually messy. When I explained why I wanted something — for example, “create a layout that looks precise enough for an engraving preview” — the results were much closer to what I wanted. It taught me that writing good prompts isn’t about length; it’s about intent.  

Another lesson was that AI can’t replace aesthetic decisions. It’s very good at producing functional solutions, but not taste. The difference between a technical map and a product that *feels right* came from me adjusting small visual details — line weight, shading, balance. That’s something no model can predict yet.  

If another founder asked me for advice, I’d tell them to treat AI like a second pair of hands, not a second brain. It’s great for scaffolding and brainstorming, but it doesn’t understand the emotional or practical goals behind your product. You have to define those first.  

This project also changed how I think about AI in my future work. I used to see AI mainly as a research or analysis tool. Now I see it as something that can bridge creativity and engineering. In future ventures, especially in materials and design applications, I’ll keep this mindset: use AI for structure, but always let the human side shape meaning and final quality.
