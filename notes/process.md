# Project Proposal — Process Log

Design, Build, Ship · MPCS 51238 · Autumn 2026
Due: Tuesday, November 3, 5:30 PM

This log records decisions made during the interview process, stage by stage.

## Checklist (from the brief)

- [ ] One static HTML page, hosted on Vercel
- [ ] One-line description: the problem, and the user
- [ ] What users told me (3+ interviews, in their words)
- [ ] Focus (Holistic Journey / Design / Systems / AI) and why
- [ ] Roadmap broken down to the fair (Nov 10 → Nov 17 v1 → Dec 1 v2)
- [ ] Tech stack, MCP servers, CLIs, and why they fit

## Stage 1 — Choosing what to build

### Initial idea (my words)

> A recipe tracker that incorporates food science into techniques and ingredients.
> Automatically scales ingredients for different portion counts, shown in grams,
> volume, or count — whatever makes the most sense. An agent estimates calories and
> creates a nutrition label. Import recipes from PDFs of recipe books, websites, or
> pictures. A section for recipe development and inspiration. Consistent format for
> steps, ingredients, and food science notes.
>
> Also: track all the restaurants I've been to — upload pictures and menu items,
> locate each on Google Maps — as inspiration for new recipes. Easy to share with
> friends and on Google Maps (e.g. all my Chicago spots, or places I've traveled).

### Breaking it apart

The idea has two distinct products in it:

- **A. Recipe tracker** — import (PDF / web / photo), consistent format, scaling with
  sensible units, food science notes, nutrition label agent, recipe development.
- **B. Restaurant journal** — log visits with photos + menu items, map them, share
  lists by city/trip.

Link between them: restaurant dishes → inspiration for recipe development.

### Questions explored

**Q1 (Idea A). Where does this come from? What's missing when you cook from a recipe?**

> You blindly follow instructions without really understanding how different
> components affect the end result. A common one: "sauté onions until translucent."
> But what if I like a more caramelized flavor? It could add variation and a food
> science bit: if you want a sweet profile, cook the onions on low heat to draw out
> the sugars.

Takeaway: the core problem isn't storing recipes, it's that recipes give
instructions without the *why* or the *dials* you can turn. Each step could
explain what it does to the result and how to change it to get the result you
want (sweeter, crispier, more tender...). This is the possible differentiator
from Paprika / Mela.

Open: hasn't said yet what they use today, or a specific recent time this happened.
