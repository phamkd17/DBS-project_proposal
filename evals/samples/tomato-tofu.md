# Eval sample 1 — Tomato Tofu (Grandma, real dictation)

Source: Grandma's phone voice dictation, copied exactly as typed. **Do not edit
the transcript** — the errors are part of the test.

## Transcript

```
Tomato Tofu
To make the tomato tofu I'm gonna cut these tomatoes into little pieces dice them down and then I'm also gonna chop the in onions into little strips after I chop them I put a little bit of oil into the pan and turn it on the heat get it just hot enough where everything starts sizzling when I put a chopstick into it and then the important part is that I add a little bit of fish sauce before it gets way too hot and burns everything just about that much and then from there let's wait until it starts bubbling and as soon as you see the liquid stop bubbling where it sticks to the bottom of the pan then you throw in your onions with like a lot of juices you want to get all the juices to cool down the pan so it doesn't burn the fish sauce and then you keep stirring it throw in a couple pieces of garlic maybe 2 here that is garlic so old let's put 5 in and then you just keep stirring around for 5 minutes and everything gets soft golden if I want it sweet and yeah let's do it 7 minutes I want a little bit of sweeter today and then tomatoes throw all your tomatoes in tomatoes kind of reduce too much I want to add more tomatoes so let's cut up some more tomatoes throw those in maybe 5 tomatoes so far keep cooking until everything caramelized together oh I forgot I gotta fry the tofu let's take the pan off the heat so it doesn't burn and then we deep fry the tofu same concept get the oil hot what's your chopstick starts boiling throwing a tofu and once it's lightly yellow then you take them out or actually you want to make sure that it's spongy very spongy on the inside but I know your sister likes the tofu less cooked so it's creamier so we'll keep a couple pieces less cooked and then we'll keep a couple pieces that are cooked very golden and crispy so it can absorb the sauce so you can both have whatever you want and then from there OK tofu is almost done let's put the pan with the onions back onto the heat to warm everything back up tomatoes bubbling when you add a little bit more water because the tomato is getting too dry but that's the thing you gotta remember you wanted 2 minutes to slightly caramelize too before you add the water because that can caramelize tomato adds a really meaty touch to the dish and then here you throw in your tofu add a little bit of water simmer it so the water extract all the flavor from the sauce tomato fish sauce into the inner parts of the tofu and just cook it for about 5 to 10 minutes until everything melts together and once that's done severed over steam white rice and then throw a little bit of a soy sauce and chili in the dipping dish if you wan
```

## What makes this hard

| Challenge | Example from the transcript |
|---|---|
| Dictation errors | "chop the in onions", "what's your chopstick starts boiling", "throwing a tofu", "severed over steam white rice", cut off at "if you wan" |
| Self-corrections | "garlic maybe 2 … that is garlic so old let's put 5 in" → final answer is 5 |
| Amounts that can't be recovered from text | "a little bit of fish sauce … **just about that much**" (a gesture) |
| Amounts never stated | tofu (how much? what kind?), onions (how many?), oil, water |
| Amounts that change mid-cook | tomatoes reduce "too much" → she adds more → "maybe 5 tomatoes so far" |
| Steps out of order | "oh I forgot I gotta fry the tofu" — comes after the sauce is started |
| Sensory cues instead of numbers | oil hot when a chopstick sizzles; fish sauce ready "as soon as you see the liquid stop bubbling where it sticks to the bottom" |
| Dials / variations | onions 5 min (golden) vs. 7 min ("a little bit sweeter today"); tofu less cooked + creamy (sister) vs. golden + crispy (absorbs sauce) |
| Her own reasoning | onion juices "cool down the pan so it doesn't burn the fish sauce"; caramelize tomato 2 min before water → "a really meaty touch"; simmer so the tofu absorbs the sauce |
| Optional extras | soy sauce + chili dipping dish "if you wan[t]" |

## Expected behavior (eval checks)

**Her words**
- [ ] Transcript is stored verbatim, unchanged.

**Structure**
- [ ] Produces a title, ingredient list, and ordered steps.
- [ ] Dictation errors are corrected in the recipe (e.g. "serve over steamed white rice"), not in her words.
- [ ] Tofu frying is moved to its proper place (before, or in parallel with, the sauce) and noted as reordered.

**Amounts**
- [ ] Garlic = 5 cloves (final answer), not 2. Optional note: older garlic is milder, so she used more.
- [ ] Tomatoes ≈ 5, with a note that she added more as they reduced.
- [ ] Does **not** invent silent amounts for fish sauce, tofu, onions, oil, or water.

**Flagged questions for Grandma** (must ask, not guess)
- [ ] How much fish sauce is "just about that much"?
- [ ] How much tofu, and what kind (firm, extra-firm)?
- [ ] How many onions?
- [ ] Roughly how much oil for deep-frying, and how much water?

**Dials and variations**
- [ ] Onions: 5 min → soft and golden; 7 min → sweeter.
- [ ] Tofu: lightly fried → creamier; deep golden → crispy and absorbs more sauce.
- [ ] Dipping sauce (soy + chili) marked optional.

**The why**
- [ ] Keeps her reasons, labeled as **hers**: onion juices cool the pan to protect the fish sauce; caramelizing tomato before adding water adds a meaty flavor; simmering pushes flavor into the tofu.
- [ ] Any science the AI adds is labeled separately from hers (e.g. chopstick test ≈ oil around 350°F; spongy fried tofu soaks up sauce).
