# Claude-Skills

A growing collection of custom **Skills for Claude** — packaged instructions that teach Claude how to do a specific kind of work well.

Each skill is a folder containing a `SKILL.md` file. The file has YAML frontmatter that tells Claude *when* to invoke the skill, and a markdown body that tells Claude *how* to do the work once it's invoked. Drop a skill into your `~/.claude/skills/` directory (or your project's `.claude/skills/`) and Claude Code will load it automatically the next time it matches a request.

---

## Repo structure

```
Claude-Skills/
├── README.md                     ← you are here
├── premium-web-design/
│   └── SKILL.md
└── <future-skills>/
    └── SKILL.md
```

Every top-level folder is one skill. The folder name is the skill's slug (kebab-case). The `SKILL.md` inside is the entire skill — no other files required.

---

## Skills in this repo

### `premium-web-design`

Create **Awwwards-quality landing pages** as React (.jsx) components — the kind of work a top-tier agency billing $50k+ produces. Trigger when a user asks for a website, landing page, or web component that should look "expensive," "luxury," "editorial," "high-end," or "agency-quality," or when they reference brands like Apple, Aesop, Bottega Veneta, or Stripe.

**What it teaches Claude:**

- The **AI-aesthetic blacklist** — banned fonts (Inter, Poppins, Montserrat, etc.), banned palettes (purple-to-blue gradients), banned layouts (the generic SaaS template), banned motions.
- A **15-entry Structural DNA Catalog** so no two sites in a batch share a template. Includes Index Manuscript, Pinned Narrative, Horizontal Navigation, Conversation Timeline, Dashboard Tile Grid, and more.
- **Deep industry research** — study at least 5 reference sites per project, pull specific patterns from each, compose a design-reference brief before writing any JSX.
- **A rigorous Spline 3D playbook** — the 4-format URL reference table, the `<spline-viewer>` `background` attribute for theme-matching, the rule against real-branded-product scenes, scene uniqueness per session, the layered fallback hierarchy (Spline → photography → SVG illustration), and a mandatory after-build render-size check.
- **A 15-point prompt checklist** every build must answer before writing JSX — field, scene match, structural DNA, references, palette, fonts, nav pattern, voice, structure, copy hooks, motion, banned moves, verification checkpoint.

→ [`premium-web-design/SKILL.md`](./premium-web-design/SKILL.md)

---

*More skills coming.*

---

## How to use a skill

### Option A — Claude Code (CLI), user-level

Drop the skill into your user skills directory so it's available in every project:

```bash
git clone https://github.com/sayginsaman/Claude-Skills.git
mkdir -p ~/.claude/skills
cp -r Claude-Skills/premium-web-design ~/.claude/skills/
```

Restart Claude Code. Claude will auto-load the skill whenever a request matches its `description` in the frontmatter.

### Option B — Claude Code, project-level

If you want a skill available only inside a specific project (and committed to that project's repo):

```bash
mkdir -p .claude/skills
cp -r ~/somewhere/Claude-Skills/premium-web-design .claude/skills/
```

### Option C — Manually, as prompt context

Paste the body of the `SKILL.md` (without the frontmatter) into your prompt as context. The frontmatter is metadata for auto-loading; the markdown body is the instruction set.

---

## How a skill works

A minimal `SKILL.md` looks like this:

```markdown
---
name: email-triage
description: >
  Use this skill whenever the user wants to sort, categorize, or draft
  responses to a batch of emails. Trigger on phrases like "go through my
  inbox," "triage these emails," or "draft replies to everything from
  last week." Do NOT trigger for single-email responses or for composing
  a new email from scratch.
---

# Email Triage

[The actual instructions Claude follows when this skill is active.]
```

- The `name` and `description` are YAML frontmatter at the top of the file.
- Claude reads the `description` to decide when to load the skill — the more specific and trigger-phrase-rich the description is, the more reliably the skill fires on the right requests (and doesn't fire on the wrong ones).
- The markdown body is the entire instruction set. Be specific. Vague skills produce vague output.

---

## License

MIT — see [LICENSE](./LICENSE). Use, adapt, fork freely.

---

Built by [@sayginsaman](https://github.com/sayginsaman).
