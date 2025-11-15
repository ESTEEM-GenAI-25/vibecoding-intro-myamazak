# 📑 Product Requirements Document (PRD)

## 1. Project Overview
- **Summary:**  
  RouteMark is a premium service that transforms user travel itineraries into elegant, credit-card-sized metal keepsakes, using AI to generate and optimize the aesthetic design of the route visualization.

- **Context/Background:**  
  This prototype phase (Phase 2) is focused on translating the business concept (from Phase 1) into a working demonstration of the core technical differentiation: the Aesthetic Route Optimization AI.

## 2. Goals and Objectives
- **Primary Goal(s):**  
  Successfully implement and visually demonstrate the core AI functionality (Route Vibe Selector).

  Create a single-page interactive prototype that clearly explains and showcases the product's value proposition.

- **Secondary Goal(s):**  
  Document the AI implementation strategy and prompting process thoroughly for technical review.

  Establish a solid, modular technical foundation for Phase 3 integration (Gemini API).

## 3. Target Audience
- **Who are the users?**  
  Individuals seeking high-end, personalized memorabilia (B2C) and corporate clients looking for unique, premium gifts or loyalty rewards (B2B).

- **User Needs:**  
  - A tangible, lasting reminder of a significant travel experience.
  - Assurance that the final product will be aesthetically perfect and high-quality.
  - An easy, interactive way to personalize the design based on the feeling of their trip.

## 4. Key Features / Requirements
- **Must-Have Features:**  
  - Route Input and Visualization: Must accept comma-separated city strings and render a route on a card-sized canvas. (Simulated geocoding is accepted for Phase 2).
  - AI Aesthetic Vibe Selector (Input): A user-facing dropdown must allow the user to input their subjective "vibe"
  - AI Aesthetic Optimization (Core Logic): The proprietary applyAIVibeStyle function must translate the user's emotional descriptor (vibe) into concrete design parameters (stroke width, line dash, color/material contrast).

- **Nice-to-Have Features (Optional):**  
  - AI Output Justification: A text box must display the AI's rationale for its design choice upon generation.
  - Prompting Strategy Traceability: Must include a log of at least three specific Google AI Studio prompts used to build the prototype, linking them directly to the implemented code components.

## 5. Design & User Experience
- **Visual Style / Vibe:**  
  Premium, minimalist, and technical, using a palette of slate and amber for contrast and elegance.

- **Branding / Colors / Fonts:**  
  Inter font family. Slate primary colors (bg-slate-50, text-slate-900) with Amber accents (bg-amber-500) for call-to-action elements.

- **Accessibility Considerations:**  
  Mobile responsive design is mandatory. High color contrast is enforced by the dark/light contrast in the material simulation and text areas.

## 6. Content Requirements
- **Pages / Sections:**  
  - Hero (Headline/CTA)
  - The Problem (Context/Background)
  - AI Simulator (Core Interactive Demo)
  - How It Works (3-Step Process Flow) 
  - Market / Product Details (B2C/B2B Use Cases)
  - Footer (CTA/Waitlist Form)

- **Specific Content to Include:**  
  Textual descriptions of the AI's optimization process, material options (Anodized Aluminum, Brushed Steel), and the card's physical dimensions.

## 7. Technical Constraints
- **Technology Stack:**  
  Single-Page Application (SPA) using HTML, Vanilla JavaScript, and Tailwind CSS (CDN).

- **Hosting / Deployment:**  
  Self-contained website.html file, intended for hosting via GitHub Pages or direct upload.

- **Performance / Security Requirements:**  
  Must be fully mobile responsive. Load time must be fast (minimal external resources).

## 8. Out of Scope
- Full production back-end for order fulfillment or real-time payment processing.
- Integration with external, real-world geocoding APIs (simulated in Phase 2).
- Integration of the final Natural Language AI (Gemini API) (Planned for Phase 3).
- Advanced interactivity like dynamic markers for all city points (Planned for Phase 3).

## 9. Acceptance Criteria
- The prototype loads successfully in a modern browser.
- All main features (Input, Vibe Selection, Generation) work as described.
- The canvas visualization correctly updates its line style based on the selected AI Vibe.
- The prd.md and README.md are complete and clearly detail the AI component and prompting log.  
