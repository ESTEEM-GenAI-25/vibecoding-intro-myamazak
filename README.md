Phase 2: Prototype Implementation Update

1. Overview & Goal

The core goal remains to offer premium, AI-designed metal keepsakes of user travel routes. This Phase 2 prototype shifts focus from conceptual planning to technical demonstration. The immediate goal was to implement and visualize the core AI feature—the Aesthetic Route Optimization—using a single, functional web page.

2. Core Features (Implemented)

The prototype focused on implementing the crucial AI-driven user flow.

Route Input and Geocoding (Simulated): Allows user input of cities and converts them to coordinates (using a hard-coded lookup table for simplicity).

AI Aesthetic Vibe Selector (Implemented with AI Logic): A dropdown allows the user to input their subjective "vibe."

AI Aesthetic Optimization (Implemented): The core applyAIVibeStyle function translates the subjective vibe into concrete design parameters.

Route Visualization: Renders the resulting route on an OpenLayers map, visually displaying the AI's aesthetic decision.

3. AI Specification

The AI is functional and demonstrably integrated into the user flow.

What AI Does (Task/Process): The AI component, simulated by the JavaScript function applyAIVibeStyle(vibe), performs a Design Parameter Translation. It takes a user's emotional descriptor (vibe) and maps it to a set of hard design rules (color hex code, stroke width, line dash pattern).

Where it Appears in the User Flow: It is activated immediately after the user selects a "Vibe" and clicks "Generate AI Route," acting as the decision-engine before the map rendering occurs.

What Model or Feature is Used: For this prototype, a proprietary Rule-Based Classification Engine is simulated in client-side JavaScript. The final production version would use the Gemini API (gemini-2.5-flash-preview-09-2025) to handle more complex, natural language inputs (e.g., "Make it look like a historic expedition") and generate the design parameters object based on a much wider set of rules and visual training.

4. Technical Architecture

The prototype is a Single-Page Web Application (SPA) written in plain HTML, CSS (via Tailwind CDN), and Vanilla JavaScript. It uses the OpenLayers library for map rendering.

Frontend: HTML/Tailwind CSS for responsive UI design.

Mapping: OpenLayers for map display and vector feature drawing.

AI Logic: Self-contained JavaScript function (applyAIVibeStyle) to simulate the AI decision layer.

Backend/Hosting: No backend required for this phase. Hosted directly via index.html.

5. Prompting Strategy & Iteration Log

The following prompts were used in Google AI Studio to develop and refine the prototype code (index.html):

#

Prompt Used in AI Studio

Output and Refinement Notes

1

“Generate the complete, responsive HTML/Tailwind CSS for a travel route planner that uses the OpenLayers library. Include a single text input for a route string (e.g., 'City1 - City2'), a 'Draw Route' button, and a large map div with ID 'map'."

Output: Generated the initial skeleton. Refinement: Added the Inter font import and ensured the ol.js and ol.css links were correct to make the map functional.

2

“Modify the HTML from Prompt 1. Add a <select> dropdown with the ID 'vibe-selector' and options: 'efficient', 'leisurely', and 'premium'. Then, modify the JavaScript to include a function applyAIVibeStyle(vibe) that returns a design object with color/width/lineDash based on the vibe. Ensure the result is applied to the OpenLayers line stroke.”

Output: Generated the core AI logic (applyAIVibeStyle) and integrated it into the drawButton event listener. This established the functional link between user input and aesthetic output.

3

“Refine the HTML/Tailwind CSS by changing the color scheme to purple for a more 'premium' brand look, and add a dedicated output box with ID 'ai-design-output' below the map that uses a highly visible background color (like indigo-100) and a border to clearly display the AI's textual rationale to the user.”

Output: Successfully changed the button colors and created the styled ai-design-output div, which provides the necessary textual justification for the AI's decision, making the feature less opaque and satisfying the documentation requirement.

6. UX & Design Notes

The interface is clean and centered, adhering to a premium, minimalist brand identity. The primary user action is immediately visible. The main UX trade-off was the use of simulated geocoding (hard-coded city list) instead of a real API call, which simplifies the scope for Phase 2 but limits real-world usability. The design prioritizes visual clarity of the AI's decision.

7. Next Steps (Phase 3)

Strengthen AI Integration: Replace the hard-coded applyAIVibeStyle logic with a call to the Gemini API using a precise system prompt to generate the design parameters based on true natural language input (e.g., "Describe the color and line thickness for a route that suggests a 'fast, business-like journey'").

Design Polish: Enhance the #ai-design-output to look like a truly final, laser-engraved card preview.

Interactivity: Implement dynamic markers for start and end points of the route.