# premium-web-design

A skill for making Claude build websites that don't look like Claude built them.

## Why this exists

If you've used AI to generate a landing page you already know the look: purple-to-blue gradient hero, Inter font, three feature cards in a row, testimonials, CTA, done. Technically functional. Visually forgettable. It's the design equivalent of beige.

This skill is an attempt to fix that. It's a long, opinionated prompt that tells Claude what NOT to do (most of the work, honestly) and then points it toward the stuff real design studios actually do — typography with personality, layouts that break the grid, scroll choreography, 3D done right, industry-appropriate color instead of default accent picks.

## When to use it

Use it when the output needs to look expensive. Marketing sites, portfolios, product pages, pitch sites, anything brand-facing where the design itself is the pitch.

Don't use it for dashboards, admin tools, or internal UI. Premium aesthetics work against readability there, and the regular `frontend-design` skill handles that category better.

Rough trigger words that activate it: "make it look expensive", "Awwwards-quality", "high-end", "luxury", references to brands like Apple, Aesop, Bottega, Stripe, or just "don't make it look AI-generated."

## What it actually does

Three things, roughly:

1. **A blacklist.** The specific fonts, colors, layouts, and motion patterns that scream AI template. Listed explicitly so Claude avoids them on purpose instead of hoping.
2. **A positive playbook.** Typography pairings, color philosophy, layout concepts, scroll-driven patterns, and the micro-details that separate "pretty good" from premium.
3. **A 3D rule.** Every site built with this skill is supposed to have a real 3D component — sourced from Spline's community library, embedded as an iframe. Not Three.js primitives glued together into something that looks like a car made of boxes. That rule alone carries a lot of weight.

There's also a short industry-research step: Claude is told to look at 2–3 real competitor sites before designing anything, so a site for an aerospace company ends up looking like aerospace (dark, restrained, SpaceX-adjacent) and not like a generic SaaS page with rockets on it.

## Output

React `.jsx` components. Single default export, no required props, drops into an artifact or any React environment. Uses Three.js r128, lucide-react, and a few other libraries that are available in the Claude artifact sandbox.

## Honest caveats

- It's not magic. You'll still get better results by giving Claude real brand assets (photos, colors, logos) than by asking it to invent a brand from nothing.
- Spline search sometimes returns nothing good for niche industries. The fallback is professional photography + parallax, which is fine but less distinctive.
- Mobile is designed second. The skill is desktop-first because visual impact is the whole point. If mobile parity is critical for you, say so up front.
- "Awwwards-quality" is aspirational. The skill raises the floor a lot. The ceiling still depends on the brief you give it.

## File layout

```
premium-web-design/
├── SKILL.md      # the actual skill — the prompt Claude reads
└── README.md     # this file
```

`SKILL.md` is the one that matters. This README is just context for humans.
