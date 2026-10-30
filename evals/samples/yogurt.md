# Eval sample 3 — Yogurt (Grandma, real dictation)

Source: Grandma's phone voice dictation, copied exactly as typed. **Do not edit
the transcript** — the errors are part of the test.

This is the **success-test dish**: a cousin who's never made it follows the app's
version, Grandma tastes it, and says it's hers.

## Transcript

```
Yogurt is a very simple dish you need about 1/2 gallon jug of milk and then one of these small 10 in yogurt container that is not flavored at all uh you heat up the milk make sure it doesn't boil uh just until it steams a little bit and then from there you add 1/3 a cup of sugar maybe less if you like it less sweet and then you mix in the yogurt with the milk you stir it into everything blends and then you put it into these little jars and then you put all these little jars into this incubator and you let it sit for about 8 hours if you don't like it too tangy but I like it at 12 hours super tangy and then from there you can either keep it in the fridge or freeze it and then serve
```

## What makes this hard

| Challenge | Example from the transcript |
|---|---|
| **The secret ingredient lost to dictation** | "small **10 in** yogurt container" — almost certainly "**Dannon**" (she said "a small container of Dannon yogurt" earlier, Q6). Could also be read as "10 oz." The cousin's interview says the starter brand is *exactly* why their yogurt never tasted right. |
| **A missing critical step** | She heats milk "until it steams" and then adds the yogurt — **no cooling step**. Steaming milk is too hot for live cultures; adding the starter then can kill them and the yogurt won't set. |
| Resolves an earlier ambiguity | "make sure it **doesn't** boil" — answers the "do boil / don't boil" question from Q6. |
| Sensory cue instead of a number | "until it steams a little bit" |
| Dials | sugar: ⅓ cup, "maybe less if you like it less sweet"; time: ~8 h (milder) vs. 12 h ("super tangy" — how she likes it) |
| Equipment assumed | "this incubator" — temperature not stated; most people don't own one |
| Unclear serving | "keep it in the fridge **or freeze it**" — two different end results |
| Conflicts with an earlier telling | Q6: "a whole jug of **whole** milk"; here: "about 1/2 gallon jug of milk" — milk type not stated this time |
| Under-specified | "not flavored at all" (plain — but does it have live and active cultures?); number/size of jars |

## Cross-check with interviews

- Grandma: *"Your grandfather likes it sour, so I let it ferment a little longer."*
  → matches the 12-hour "super tangy" dial.
- Cousin: *"I didn't realize that I needed to buy yogurt with live, active
  cultures … it had to be the specific yogurt container with the bacterial
  strain."* → the starter must be specified precisely, and the "10 in" error is
  exactly where that information gets lost.

## Expected behavior (eval checks)

**Her words**
- [ ] Transcript is stored verbatim, unchanged.

**Structure**
- [ ] Produces a title, ingredient list, and ordered steps.
- [ ] Milk is heated until steaming and **not boiled**.

**Flagged questions for the user** (must ask, not guess)
- [ ] **"10 in" yogurt container** — is this Dannon? What size? Plain with live and active cultures?
- [ ] **Cooling step** — does she let the milk cool before adding the yogurt? How does she tell when it's ready (e.g. can hold a finger in it)? *This is the most important check: without it the recipe can fail outright.*
- [ ] Whole milk, or another kind?
- [ ] What temperature is the incubator set to?
- [ ] Served chilled from the fridge, or frozen?

**When a question is skipped ("I don't know")**
- [ ] The app offers a **suggestion** the user can accept or edit (e.g. cool to ~110°F / 43°C — warm but comfortable to the touch — before adding the starter; incubate around 110°F).
- [ ] Every accepted suggestion stays visibly labeled as suggested, never shown as Grandma's.

**Dials and variations**
- [ ] Sugar: ⅓ cup, less for less sweet.
- [ ] Incubation: ~8 h → milder; 12 h → super tangy (Grandma's preference).
- [ ] No incubator: an alternative way to hold it warm (e.g. oven with only the light on), labeled as a suggestion.

**The why**
- [ ] Her reasons labeled as **hers**: don't boil; longer = tangier.
- [ ] AI-added science labeled separately: the starter brings the live cultures, so the brand/strain shapes the flavor; too-hot milk kills the cultures; longer incubation = more acid = tangier.
