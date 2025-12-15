# 📘 RouteMark — Product Requirements Document (Updated Final Version)

## 1. Product Overview (Updated)

RouteMark addresses a common gap between **digital travel memories** and **tangible keepsakes**. Many travelers wish to preserve meaningful journeys — from their first international flight to a memorable honeymoon — in a form that feels both artistic and personal. Yet, most digital souvenirs (e.g., map screenshots or itinerary apps) lack the material presence of something you can hold or gift.

**Users:** RouteMark targets travel enthusiasts, designers, and gift shoppers who appreciate minimalist, high-end personalization. B2B opportunities include companies seeking elegant branded gifts for clients or employees.

**Current Product State:**  
The current RouteMark prototype is a **web-based configurator** for custom-engraved aluminum cards. Users can input routes (e.g., “Tokyo – New York”), visualize great-circle paths on a realistic black aluminum canvas, and simulate engraving. It features live OpenLayers map rendering, adjustable styles (“vibes”), seam-cleaned coastlines, and a working **cart drawer system** with persistent local storage — preparing for e-commerce integration.

---

## 2. Core Features & Status

| Feature | Description | Status | AI Dependency |
|----------|--------------|--------|----------------|
| Route Visualization | Great-circle routes between major cities using OpenLayers | ✅ Implemented | ❌ Conventional |
| Coastline Stitching | Seam-cleaned TopoJSON coastlines & borders | ✅ Implemented | ❌ Conventional |
| Vibe Selector | Adjusts line width/dash based on “Premium,” “Efficient,” or “Leisurely” styles | ✅ Implemented | ⚙️ Future AI tuning |
| Aluminum Card Preview | Simulated black anodized background with brush texture | ✅ Implemented | ❌ Conventional |
| Add to Cart Drawer | Persistent cart using localStorage, subtotal calculation | ✅ Implemented | ❌ Conventional |
| PNG Export | One-click export of engraved card as image | ✅ Implemented | ❌ Conventional |
| AI Route Style Explanation | Auto-explanation of visual style (why certain aesthetics were chosen) | 🔜 Planned | ✅ AI-based |
| City Autocomplete / Geocoding | AI-assisted city name resolution for user-entered routes | 🔜 Future | ✅ AI-based |
| Checkout Integration | Payment flow (Stripe / Shopify API) | 🔜 Future | ❌ Conventional |

---

## 3. AI Specification (Final)

**Planned AI Task:**  
AI will **interpret user-entered routes and preferences** to generate descriptive text and visual style recommendations.

### Task Definition
- **Inputs:**  
  - User-entered route string (e.g., “Paris – San Francisco”)  
  - Selected vibe (Premium / Efficient / Leisurely)  
- **Outputs:**  
  - A short, stylistically aligned description (e.g., “A premium route connecting cosmopolitan capitals across the Atlantic — rendered in bold white to evoke clarity and ambition.”)  
  - (Future) Adjusted visual parameters (color warmth, line curvature bias)

### Integration Points
- Appears in the **preview generation flow**: after route parsing and before the visualization is drawn.  
- Text is displayed in a side panel or tooltip near the card.

### Model & Tools
- **Model:** Google Gemini 1.5 (via AI Studio API)
- **Invocation:** REST call from the front-end JavaScript using fetch() with prompt payload.
- **Constraints:**
  - Rate limit: ≤ 3 AI calls per minute per session.
  - Filtered input: sanitized city names only (no freeform user text).
  - Guardrail: description length capped at 3 sentences, neutral tone enforced.

---

## 4. Technical Architecture (Reality Check)

**Front-End Stack:**
- HTML5, Vanilla JavaScript, TailwindCSS  
- OpenLayers 8.2 for geospatial rendering  
- TopoJSON for map data (coastlines, borders)

**AI Call (Planned Integration):**
- Triggered post-route parsing  
- Handled by `fetch()` to Gemini endpoint with JSON body `{route, vibe, styleHints}`  
- Response injected into DOM element `#ai-description`

**External Dependencies:**
- `world-atlas@2` (TopoJSON)
- `OpenLayers` (OL library)
- Gemini API (future)

**Diagram (Simplified):**
```
[User Input] → [Parser → RouteBuilder] → [Map Rendering]
                               ↓
                        [AI Style Recommender]
                               ↓
                      [Updated Visualization + Text]
                               ↓
                          [Cart System]
```

---

## 5. Prompting & Iteration Summary

RouteMark’s design process heavily relied on **prompt-driven development** to achieve realistic, manufacturable visuals.

**Key Prompts Used During Development:**
1. *“Create an HTML5 card preview simulating aluminum surface with realistic shadows and curvature.”*  
   → Generated initial layout and visual base.
2. *“Simulate great-circle flight routes between cities using OpenLayers.”*  
   → Implemented 3D-to-2D arc mapping with seam handling.
3. *“Stitch multiple global map projections to remove visible seam lines.”*  
   → Led to the `cleanFeatureGeometry()` function.
4. *“Add e-commerce cart drawer using Tailwind and localStorage.”*  
   → Built the persistent, demo-ready cart system.

**Prompt Iteration Insights:**
- The most stable results came from **incremental prompting** (building one module at a time).  
- Explicitly naming UI components (“drawer,” “badge,” “preview card”) improved generation accuracy.  
- Prompting for *aesthetic realism* (e.g., “black anodized aluminum”) required rebalancing brightness filters in CSS.

---

## 6. UX & Limitations

**Intended Journey:**
1. User enters route (e.g., “Tokyo – New York”)  
2. Chooses vibe → preview updates dynamically  
3. Adjusts engraving options → adds to cart  
4. Optionally exports preview as PNG or proceeds to checkout

**Known Limitations:**
- AI city parsing not yet implemented (manual entry required).
- Cart is local only (no server sync or user accounts).
- No live pricing or inventory logic.
- Coastal seam correction works at medium zoom only.

**Ethical / Trust Considerations:**
- AI-generated descriptions are for stylistic purposes only — not factual or geographical claims.
- No personal or location data is stored or transmitted.

---

## 7. Future Roadmap

1. **Integrate Gemini AI fully** for style narrative generation and route beautification.  
2. **Implement city name autocomplete** using AI-based geocoding or Maps API.  
3. **Enable live checkout** through Stripe or Shopify with order confirmation.  
4. **Enhance visual realism** with GPU-accelerated WebGL card rendering.  
5. **Add social export** (generate shareable card URLs and QR code previews).  
