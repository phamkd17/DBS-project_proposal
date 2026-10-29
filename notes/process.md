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

**Q2 (Idea A). A specific recent dish — did you look for answers, and where?**

> I want the app to teach the user and think creatively about how to make the dish
> to their liking. Most people would blindly follow a recipe. If they have to pull
> out their phones to research more, they will get annoyed and not do it.

Takeaway: the hypothesis is **friction**. The knowledge exists (Serious Eats,
ChatGPT), but nobody stops mid-cook to research it, so it has to be in the step
itself. Goal: teach + encourage creative customization to the cook's own taste.

To verify in user interviews: do people actually skip research mid-cook? Do they
wish they'd customized? (Still no concrete personal example — "most people" is a
hypothesis, not evidence yet.)

**Q3. Who is this for, specifically?**

> The main user of this app is me, a passionate home cook. I want to store recipes
> that I like for inspiration. I also want to understand the science behind why
> recipe authors write the way they do, select certain ingredients, and use certain
> techniques. I will also use it to track recipe development and experimental dishes
> or trials. I want a mood board–like logbook to capture inspiration from
> places/restaurants I have tried or recipes I have seen elsewhere.
>
> Another user is my grandmother, who cooks daily and just wings it. She has a very
> strong intuition for how to make a dish spectacular with the items she has. I want
> the app to be easy for her to use so that she can share her recipes with the
> younger generation. It has to be easy for her to log items, as she is not as
> tech-savvy. There have been many times when my cousins and I have asked, "Do you
> remember the yogurt Grandma made?" We discuss it, but no one knows how to
> recreate it.
>
> Other users are my friends, who are new to the culinary world and blindly follow
> recipes as procedures. The app needs to make it easy for them to learn techniques
> and food science so they do not get overwhelmed. It should be all-encompassing so
> they do not have to use multiple tools to understand something.
>
> The last user is anyone who just wants to follow certain cooks because they like
> a particular person's style and taste. This person could have any level of
> culinary skill.
>
> I want this app to be educational for new users, an experimental logbook for more
> experienced cooks, and an easy way for people to capture and share ideas, even if
> they are not tech-savvy.

Four user types identified:

| User | Need | Implies |
|---|---|---|
| Me (passionate home cook) | Understand the why; log experiments/trials; inspiration mood board (incl. restaurants) | Food science annotations, versioned trials, inspiration board |
| Grandma (intuitive, not tech-savvy) | Capture recipes she wings so family can recreate them | Very low-effort capture (voice/photo?), AI turns it into a structured recipe |
| Friends (beginners) | Learn technique without being overwhelmed or juggling tools | In-step explanations, progressive detail |
| Followers (any level) | Follow a cook whose taste they like | Profiles, following, feed — social layer |

Strongest concrete evidence so far: **"Do you remember the yogurt Grandma made?"**
— a real, recurring family problem with a real person to interview.

Reachable interviewees: grandma, cousins, beginner friends, myself.

Concern: four users with different needs is too much for ~3 weeks. Need a primary
user for v1.

**Q4. If only one person could use v1, who and why?**

> The main users for V1 would be my grandma and me because it is a way for us to
> stay connected. In addition, there is a dichotomy between our technological
> skills: I understand technology well, but she does not. However, she is an expert
> cook. If we can capture both of our capabilities, the app will be useful for
> everyone.

**Decision: v1 users = me + grandma.** One product with two sides:

- **Grandma — capture.** Expert cook, not tech-savvy. Must be able to log a dish
  with almost no effort.
- **Me — enrich + experiment.** Tech-savvy home cook. Turns captured dishes into
  structured, recreatable recipes, adds the food science, logs my own trials.

Why: it keeps us connected, and designing for both ends of the tech-skill range
(expert cook / novice user, and the reverse) should cover the people in between.

Deferred: beginner friends (learning mode), followers (social layer), and
restaurant journal → candidates for v2 / ambitious version.
