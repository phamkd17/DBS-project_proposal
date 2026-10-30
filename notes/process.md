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

**Q5. How does grandma use technology today?**

> She uses a smartphone and is able to take pictures. My aunt can help her write
> down or type out her techniques. Voice input is also very useful, as she can speak
> while she cooks. Let's assume English is the main language. It would be cool if
> she could describe what she is doing and the app could automatically convert that
> into a recipe with instructions and explanations of why she took each step, based
> on food science or best practices from experience.

Takeaway — the core v1 flow is taking shape:

1. Grandma narrates while she cooks (voice), snaps photos. Aunt can help.
2. App transcribes and turns the narration into a structured recipe: ingredients,
   steps, amounts.
3. Each step gets a **"why"**: the food science or best practice behind what she did.
4. I (and cousins) can read it, recreate it, and log our own trials.

Constraints: English for v1. Smartphone + camera available. Aunt is a possible
helper — the capture flow may have a second operator.

### Research: similar products

Voice-to-recipe capture for grandparents **already exists**, so capture alone
isn't the differentiator:

- [Touta](https://touta.app/) — "record grandma's recipes," AI transcribes voice + handwritten cards. Free, iOS/web.
- [Recipe Diary](https://recipediary.app/) — voice note → recipe card, editable.
- [CookNest](https://cooknest.app/en/features/dictation) — dictation → recipe (PRO tier).
- [Recipio](https://recipio.app/knowledge/add-recipe-by-voice) — voice entry, review before saving.
- Several DEV posts of people building this for their own grandmother
  ([1](https://dev.to/saurav10codes/i-built-a-platform-for-my-grandma-and-others-so-that-they-can-upload-their-voice-notes-for-a-545),
  [2](https://dev.to/shivamgravity/my-dadis-recipes-were-trapped-in-voice-notes-so-i-built-her-an-ai-cookbook-44g4)).
- Lesson from [SayChef](https://dev.to/saychef/building-a-voice-first-ai-recipe-manager-lessons-i-learned-k1b):
  the hard problem is messy natural speech, not speech recognition.

None of these mention explaining **why** each step is done, resolving vague
amounts ("a handful," "until it smells right"), or a logbook of trials against the
original. That's where this project can stand apart.

### Research: speech-to-text options (free tiers, approximate — verify on vendor pages)

- **Groq (hosted Whisper)** — ongoing free plan with rate limits (~2,000 req/day).
- **Deepgram** — one-time $200 credit, no card.
- **AssemblyAI** — one-time $50 credit, no card.
- **Browser Web Speech API** — free, no key, but quality/browser support varies.
- OpenAI — no standing free tier.

Sources: [DEV free quotas (Oct 2026)](https://dev.to/unicodefawn/free-speech-to-text-and-text-to-speech-api-quotas-oct-2026-with-the-catches-17hg),
[Spokenly free STT limits](https://spokenly.app/blog/free-speech-to-text-apis).

**Q6. What does grandma actually say? What should the app do with vague parts?**

> One phrase she used was, "Use a whole jug of whole milk and an entire small
> container of Dannon yogurt, and add a bit of sugar to sweeten it to your liking.
> Then put it in the incubator."
>
> I want the app to preserve her dialogue in the journal and convert it into a
> recipe by adding food science details. For example, if you don't have a yogurt
> maker, heat the milk to a certain temperature. [Clarify whether "Do boil" means
> "Boil" or "Don't boil," and how this affects the proteins.]

**Decision: two layers per recipe.**

1. **Her words** — the original narration, kept verbatim in the journal. Never
   overwritten.
2. **The recipe** — structured version generated from it, with:
   - **Resolved amounts** — "a whole jug" → gallon or half gallon? "a small
     container of Dannon" → ~5.3 oz / 150 g. Brand/package sizes become real units.
   - **Flagged ambiguities** — things the app must ask about rather than guess.
     E.g. "do boil" vs. "don't boil" (could also be a transcription error), or
     which size jug.
   - **Why + alternatives** — the food science per step, and what to do if you're
     missing something (no incubator → hold the milk at a set temperature another
     way).

Worked example for the yogurt (food science to verify):
- Heating milk to ~180°F / 82°C (not necessarily a full boil) denatures the whey
  proteins, which then bind with casein → thicker yogurt that weeps less whey.
- Cooling to ~110°F / 43°C before adding the starter matters — too hot kills the
  live cultures.
- "Put it in the incubator" = hold at ~110°F for several hours. Without one: oven
  with the light on, a cooler with warm water, etc.
- "Sugar to your liking" is a dial: added before incubating it also feeds the
  cultures; after, it's just sweetness.

**Q7. How will I know it works? Which dishes for v1?**

**Success test (v1):** A cousin who's never made it follows the app's version of
grandma's yogurt, grandma tastes it, and says it's hers.

**v1 dishes:** yogurt, flan, tomato tofu.

Note: a good spread for testing. Yogurt and flan are both precise
temperature/protein dishes (culture temperature; custard setting, water bath,
caramel) — strong food-science content. Tomato tofu is a savory stovetop dish
cooked by feel — tests how the app handles "wing it" cooking and
"to your liking" seasoning.

**Q8. Scope sort — what's in v1, v2, out?**

Agreed with the proposed sort, with one change:

> Instead of restaurant journal I want to have something to capture inspiration so
> I can develop recipes later.

| Feature | Scope |
|---|---|
| Voice capture + photos (grandma/aunt) | **v1** |
| Her words kept verbatim | **v1** |
| AI: narration → structured recipe | **v1** |
| Flagged ambiguities | **v1** |
| Food science "why" per step | **v1** |
| Sign up + share a recipe with family | **v1** |
| **Inspiration capture** (replaces restaurant journal) | v2 (TBD) |
| Portion scaling | v2 |
| Trial logbook vs. original | v2 |
| Nutrition label agent | v2 or out |
| Import from PDF / web / cookbook photo | v2 or out |
| Restaurant journal + Google Maps sharing | **Out** → ambitious version |
| Beginner learning mode, following cooks | **Out** → ambitious version |

Note: inspiration capture could reuse the same capture pipeline as grandma's
narration (photo + voice note), just tagged as "inspiration" instead of "recipe."

**Q9. The last time something inspired a dish idea?**

> I recently saw an inspiring example: a chef deeply caramelized onions until they
> were almost as caramelized as those used in French onion soup. He then dehydrated
> them and used them to top buttered bread. They could also be added to burgers and
> other dishes. I want to be able to document this to capture his creativity so I
> can later develop something based on the concept of dehydrated caramelized onions.

Takeaway: an inspiration is a **technique or concept**, not a recipe. An entry
needs:

- **The concept** — "deeply caramelized onions, then dehydrated"
- **Source** — who/where (chef, video, restaurant), photo or link
- **Where it could go** — buttered bread, burgers, ...
- **The science** (AI-added) — long caramelization builds sweetness and browned
  flavor; dehydrating concentrates it and makes it crunchy and shelf-stable
- **Later → a trial** — the entry becomes the starting point for recipe development

(Callback to Q1: same onions, same "what dial am I turning" idea.)

Open: didn't say what I did with it at the time or whether I went back to it —
good question for my own user interview.

**Scope: inspiration capture → v2.** The v1 success test is grandma's yogurt; this
builds on the same capture + science pipeline once it works.

## Stage 2 — Focus

**Decision: AI.**

> AI, because turning grandma's messy speech into recipes is the hard part. I want
> to learn how to better leverage the AI.

What going deep looks like here:

- **Pipeline:** narration (+ photos) → transcript → structured recipe → resolved
  amounts → flagged ambiguities → food-science "why" per step.
- **Tools the model can call:** e.g. package-size lookup ("small Dannon" → 150 g),
  unit conversion, a food-science reference.
- **Evals:** a set of test narrations (grandma's real ones + tricky synthetic ones)
  with checks: ambiguities get flagged rather than guessed ("do boil" / "don't
  boil"), amounts resolve correctly, her words are preserved, science notes are
  accurate.

## Stage 3 — User interviews

Draft questions in `notes/user-interviews.md`.

**Q13. Does grandma have existing recordings? What does she record with?**

> It's more of voice to transcribing.

Interpretation (to confirm): she uses her phone's **voice dictation** —
speech becomes text as she talks (e.g. into a notes app or a text message) —
rather than saving audio files. So her existing "recordings" are **text with
dictation errors**, which is exactly where "do boil" vs. "don't boil" comes from.

Implication for v1: the input can be **dictated text** (pasted or typed via the
phone's built-in dictation), so the app may not need its own speech-to-text in v1.
The AI's job starts at messy text → recipe. In-app audio recording can come later.

**Q14. Can you get 2–3 of her actual dictated notes?**

Confirmed by example: provided Grandma's real dictated **tomato tofu** note.
Saved verbatim as the first eval case: `evals/samples/tomato-tofu.md`, with a list
of what makes it hard and the expected-behavior checks.

Biggest new finding: **"just about that much"** — she gestured. Some amounts
can't be recovered from text at all, so the app *must* be able to send questions
back to her.

**Q15. Who answers the app's questions, and how?**

> I say the app saves the transcript and when the user is ready to create the
> recipe from the transcript, the questions will be asked to the user for
> verification. If the user doesn't know, the app will make its own guesses.

**Decision: capture and recipe creation are two separate moments.**

1. **Capture** — dictate (or paste) → transcript saved verbatim. Nothing else
   asked. Grandma just talks.
2. **Create recipe** — whenever the user is ready, the app drafts the recipe and
   asks its verification questions ("How much fish sauce?").
3. **Unknown → suggestion.** If the user doesn't know, the app offers a
   **suggestion** (wording correction from me: "suggestions, not guesses") that
   the user can accept or edit. Accepted suggestions stay **visibly labeled as
   suggested**, so a cousin can tell Grandma's amounts from the AI's.

This keeps the burden off Grandma and matches the existing family workflow
(she talks, someone else writes it up later).

Second real sample: **pork mango soup** → `evals/samples/pork-mango-soup.md`.
New problem types: contradictions (mango 5 vs. 10 min), ranges, assumed knowledge
("you know how to do that"), prepped-but-unused ingredients (green onions), and
**cross-recipe techniques** ("you do the same technique" — chopstick oil test +
caramelized fish sauce). Grandma has signature techniques she reuses across dishes
→ v2 / ambitious: a library of *Grandma's techniques* linked from every recipe
that uses them.

## Stage 4 — Roadmap

_Drafting._
