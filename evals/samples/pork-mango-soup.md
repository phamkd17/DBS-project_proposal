# Eval sample 2 — Pork Mango Soup (Grandma, real dictation)

Source: Grandma's phone voice dictation, copied exactly as typed. **Do not edit
the transcript** — the errors are part of the test.

## Transcript

```
Alright I'm making pork mango soup for the family tonight start off by making rice you know how to do that from there you're gonna cut up pork ribs into tiny little chunks you want the porks with the bone on them 'cause the bone gives a little bit more flavor to the broth and then from there you wanna boil the meat real quick with salted water then from there you pour away the salted water and then you re boil it you want to get rid of all the blood and the scum and all the gunk that comes off of the bone that adds a weird flavor to this soup and makes it a little cloudy I don't like those extra proteins and collagens and all that stuff floating around I like crystal clear broth so that's why you boil it a couple times get rid of it remove all this foam at the top and then after you boil that a couple of Times Now everything is wet so this is where you add oil to the pot or you add oil to a different pan you turn up the heat test up the chopstick make sure that the chopsticks boiling and then from there you sear the pork until it's nice and brown golden on the side and then once it's golden you do the same technique you put your fish sauce in you caramelize it or you add your fish sauce no first you add your pepper then your fish sauce give it about like a 32nd so that the fish house tries and the cracked black pepper uh reese's it's aroma it's an oil and then you throw in the onions and then you sear the onions around scrape up all the brown residual on the bottom of the pin and then once that onion becomes slightly translucent you add water to the soup I see add water and then you put the pork pieces back in and you simmer it for like 30 minutes an hour where it becomes nice and soft to chew on the pork and then from there you're gonna slice up white onions 'cause I don't like onions to be a little too sweet in this soup 'cause there's a fruit component and the fruits are a sweet and sour so you slice up the onions into thin little strips you get a little bit cilantro and then you get uh green onions where you cut them into little pieces too and then you cut mangoes into one inch strips green mangoes you want the mangoes to be really sour uh 'cause that's what the signature of the soup is and then once the pork gets all nice and soft then you throw an the mangoes and you cook the mangoes for about 5 minutes or until it's slightly soft because raw mangoes it's very crunchy and hard you just want to cook it down so that I release it sourness and blends all the flavor together and then once the mango is soft after 10 minutes then you throw in your freshly cut white onions and cilantro and then you serve that over rice and then if you want add a little bit of Chili Peppers as a garnish that will be add a little bit of a nice green and red heat to the dish
```

## What makes this hard

New challenges this sample adds beyond tomato tofu are marked **(new)**.

| Challenge | Example from the transcript |
|---|---|
| Dictation errors | "a **32nd**" (30 seconds), "the **fish house tries**" (fish sauce fries/dries), "**reese's it's aroma it's an oil**" (releases its aroma into the oil), "bottom of the **pin**" (pan), "**I release it** sourness", "throw **an** the mangoes", "**I see** add water" |
| Self-corrections of order | "you put your fish sauce in … **no first you add your pepper then your fish sauce**" |
| **(new)** Contradictions | mango cooks "about 5 minutes" … then "once the mango is soft **after 10 minutes**" |
| **(new)** Ranges | simmer "for like 30 minutes an hour" → 30–60 min, until pork is tender |
| **(new)** Assumed knowledge | "start off by making rice **you know how to do that**" |
| **(new)** Prepped but never used | green onions are cut "into little pieces too" but never added |
| **(new)** Ambiguous equipment | "add oil to the pot **or** you add oil to a different pan" |
| **(new)** Which ingredient? | "the onions" seared early vs. sliced "white onions" added at the end — same kind? |
| **(new)** Cross-recipe techniques | "**you do the same technique**" — chopstick oil test + caramelized fish sauce, same as tomato tofu |
| Amounts never stated | pork ribs, salt, pepper, fish sauce, water, mangoes, cilantro, onions |
| Sensory cues | oil ready when the chopstick bubbles; pork "nice and brown golden"; onion "slightly translucent"; mango "slightly soft" |
| Her own reasoning | bone adds flavor; parboiling removes "blood and the scum" for a "crystal clear broth"; white onions because the mango already brings sweet + sour; green mango because sourness is "the signature of the soup" |
| Optional extras | chili pepper garnish "if you want" |

## Expected behavior (eval checks)

**Her words**
- [ ] Transcript is stored verbatim, unchanged.

**Structure**
- [ ] Produces a title, ingredient list, and ordered steps.
- [ ] Dictation errors are corrected in the recipe ("30 seconds," "releases its aroma into the oil," "pan"), not in her words.
- [ ] Pepper goes in **before** fish sauce (her self-correction wins).
- [ ] Rice is listed as a component/side, not expanded into invented steps.

**Amounts and times**
- [ ] Simmer shown as a range: 30–60 min, until the pork is tender.
- [ ] Does **not** invent silent amounts for pork, salt, pepper, fish sauce, water, mangoes, onions, or cilantro.

**Flagged questions for the user** (must ask, not guess)
- [ ] Mango: 5 minutes or 10 minutes? (contradiction)
- [ ] Green onions are prepped but never added — when do they go in? (with the white onions and cilantro at the end?)
- [ ] Sear in the same pot or a separate pan?
- [ ] Are the onions seared early the same kind as the white onions added at the end?
- [ ] How many parboils is "a couple times"?
- [ ] Amounts for the unstated ingredients (pork, fish sauce, water, mangoes, ...).

**When a question is skipped ("I don't know")**
- [ ] The app offers a **suggestion** the user can accept or edit.
- [ ] Every accepted suggestion stays visibly labeled as suggested, never shown as Grandma's.

**Dials and variations**
- [ ] Chili pepper garnish marked optional.
- [ ] Mango sourness noted as the key dial (greener = more sour).

**The why**
- [ ] Keeps her reasons, labeled as **hers**: bone-in for flavor; parboil + skim for clear broth; white onion because the mango already brings sweet and sour; cook the mango to soften it and release its sourness.
- [ ] Any science the AI adds is labeled separately (e.g. pepper blooms in hot oil; scraping the browned bits adds flavor to the broth).

**Cross-recipe**
- [ ] "The same technique" is recognized as the chopstick oil test + caramelized fish sauce from tomato tofu (v2: link to Grandma's technique library).
