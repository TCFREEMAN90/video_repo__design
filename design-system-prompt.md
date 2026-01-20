# Design System Prompt (The Boss Move)

**Use with:** Claude Code, Cursor, Windsurf, or any AI coding assistant

**Purpose:** Generate two documents that lock in your design forever—a Design Concept and a Design System

---

## Why This Matters

When you apply a theme to your app, it looks good... until you add the next feature. Then the AI guesses. And guesses on guesses degrade over time.

These two documents solve that:

1. **Design Concept** - The "why" and "feel" of your design (like what a creative director would write)
2. **Design System** - The specific tokens, components, and rules (like what a designer would hand off in Figma)

With these in place, every future feature follows the same visual language automatically.

---

## The Prompt

```
I want to codify the design of this application so that anything created going forward will follow this visual language.

Create two documents:

---

## Document 1: Design Concept (design-concept.json)

This is the design direction document—the ethos and principles that guide the visual feel.

Include:
- Core vision statement (1-2 sentences describing the feeling/atmosphere)
- Mood and inspiration (what emotions, what references)
- Design principles (3-5 guiding rules for decisions)
- Typography philosophy (what the fonts should convey)
- Color philosophy (what the palette should feel like)
- Spacing philosophy (tight vs. airy, when to use which)
- Component expression (how buttons, cards, inputs should feel)

This document answers: "If we need to make a decision not covered by the design system, what principles guide us?"

---

## Document 2: Design System (design-system.json)

This is the technical specification—exact values, tokens, and component definitions.

Include:
- Color tokens (primary, secondary, background, surface, text, borders, states)
- Typography scale (font families, sizes, weights, line heights)
- Spacing scale (base unit, standard increments)
- Border radius tokens
- Shadow/elevation tokens
- Component specifications (buttons, inputs, cards, badges, etc. with exact styles)
- Animation/transition defaults

This document answers: "What exact values do I use when building a new component?"

---

Save these as:
- design-concept.json
- design-system.json

Analyze the current application thoroughly before generating these documents. Base them on what actually exists, not hypotheticals.
```

---

## How to Use

1. First, get your app looking the way you want (using the ideation → redesign workflow)
2. Once you're happy with it, run this prompt
3. You'll get two JSON files that define your design language
4. For all future work, tell your AI coder: "Use the design system in design-system.json"

---

## What You Get

**Design Concept example snippet:**
```json
{
  "vision": "Create a dreamy, calming digital environment that feels like looking through frosted glass at a serene sky",
  "mood": {
    "emotions": ["calm", "playful", "airy"],
    "inspirations": ["soft clouds", "soap bubbles", "morning light"]
  },
  "principles": [
    "Breathing room over density",
    "Soft edges over sharp corners",
    "Subtle motion over static interfaces"
  ]
}
```

**Design System example snippet:**
```json
{
  "colors": {
    "primary": "#6B9BD2",
    "surface": "#F8FAFC",
    "text": "#1E293B"
  },
  "borderRadius": {
    "sm": "8px",
    "md": "16px",
    "lg": "24px"
  },
  "shadows": {
    "card": "0 4px 12px rgba(0,0,0,0.08)"
  }
}
```

---

## Tips

- Run this AFTER you've gotten your app looking good—it codifies what exists
- The design concept is for edge cases and future decisions
- The design system is for exact implementation
- When adding new features, include both files in your context and say "follow the design system"
- Update these documents if your design evolves significantly
