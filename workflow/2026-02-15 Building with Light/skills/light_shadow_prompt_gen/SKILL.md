---
name: Light and Shadow Prompt Generator
description: Generates high-quality image prompts focusing on architectural geometry, dramatic lighting, and solitary figures, highlighting material textures and atmospheric depth.
---

# Light and Shadow Prompt Generator

This skill generates image prompts based on the "Container + Pressure + Cut + Anchor" aesthetic formula. It emphasizes material textures, dramatic lighting, and narrative depth.

## Process

### 1. Materiality & Theme Analysis
- **Goal**: Establish the "Substance" of the scene.
- **Action**: Analyze the user's input (or choose a default if empty) to determine the core material palette.
- **Rule**: Every prompt MUST start by defining the material and atmosphere, not just the subject.
    - *Bad*: "A big room."
    - *Good*: "A cold, damp concrete chamber with water stains on the walls."
    - *Good*: "A rusting industrial corridor filled with steam."

### 2. Structural Formula Application
Construct the scene using this 4-step formula:

1.  **Container (The Geometry)**
    -   Describe a repetitive or imposing geometric structure.
    -   *Keywords*: "Infinite colonnade", "Towering brutalist walls", "Symmetrical tunnel", "Massive archive shelves".
    
2.  **Pressure (The Lens)**
    -   Use wide-angle lenses and low angles to create scale and "pressure".
    -   *Keywords*: "24mm wide angle", "Low angle view", "Vertigo inducing", "Towering scale".
    -   *Action*: Draw from `resources/variations.json` "lens_types" for variety.

3.  **Cut (The Light)**
    -   Describe light not as illumination, but as a physical object cutting the space.
    -   *Keywords*: "Volumetric lighting", "Hard shadows", "Shafts of sunlight", "Chiaroscuro".
    -   *Action*: Draw from `resources/variations.json` "lighting_styles" for variety.

4.  **Anchor (The Scale)**
    -   Place a single, small, static element to provide scale.
    -   *Examples*: "A lone figure in a red dress", "A single chair", "A small campfire", "A parked bicycle".
    -   *Rule*: The anchor must be small relative to the container.

### 3. Detail Injection (Texture & Props)
- **Goal**: Make it feel "real" and "lived-in".
- **Micro-Details**: explicit mention of surface imperfections.
    -   *Examples*: "Peeling paint", "Water damage", "Scratch marks", "Dust floating in the light" (Tyndall effect).
- **Contextual Props**: Add small scatter objects relevant to the theme.
    -   *Theme*: Ancient Temple -> *Props*: "Burnt-out candles", "Fallen petals".
    -   *Theme*: Cyberpunk -> *Props*: "Tangled wires", "Discarded takeout box".
    -   *Theme*: Office -> *Props*: "Scattered papers", "Overturned coffee cup".

### 4. Assembly & Variety Check
- Combine all parts into a cohesive prompt.
- **Negative Prompt**: Include a standard negative prompt for this style (e.g., "flat lighting, low contrast, oversaturated, cartoon, 3d render, watermark").
- **Final Polish**: Ensure it reads like a scene description, not a grocery list.

## Example Output Format

**Prompt:**
[Material/Atmosphere] + [Container] + [Pressure/Lens] + [Cut/Lighting] + [Anchor] + [Details/Props]

**Negative Prompt:**
[Standard Negative Prompt]

## Usage Examples

**Input:** "Subway Station"
**Output:**
*Prompt:* Rough, grime-covered ceramic tiles lining the walls of a desolate underground space. An infinite symmetrical subway tunnel stretching into darkness. 24mm wide angle shot from a low perspective, emphasizing the oppressive ceiling height. Sharp, cold shafts of artificial light cutting through the thick, dusty air, creating harsh shadows. A lone commuter standing still on the platform, waiting. Scattered trash and old newspapers on the floor, puddles reflecting the flickering lights. cinematic lighting, photorealistic, 8k.

**Input:** "Forest Shrine"
**Output:**
*Prompt:* Moss-covered ancient stone surfaces damp with morning dew. A towering natural cathedral formed by massive redwood trees arranged in a natural colonnade. Ultra-wide panoramic perspective looking up at the canopy. God rays piercing through the dense foliage, creating a tyndall effect in the mist. A single small stone idol placed at the base of a tree. Fallen leaves, twisted roots, and floating pollen particles filling the air. mystical atmosphere, intricate texture, unreal engine 5.
