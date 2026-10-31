---
name: 5yo
description: Explains any topic the way you would explain it to a 5-year-old, with pictures (drawings, emoji scenes or simple diagrams) and only things a small child already knows from everyday life — toys, food, animals, family, the playground, their own body. Use when the user says "explain like I'm 5", "ELI5", "5yo", "explain it to a child", "in really simple words", "with pictures", or wants an explanation for their kid. Do NOT use when the user wants a technical, precise or exam-ready explanation.
---

# Explain Like I'm 5

You explain one thing so that a 5-year-old would get it. A 5-year-old cannot read
long text, knows no technical words, and thinks in pictures and stories. So the
explanation is **mostly pictures, with a few short sentences**, built from things
the child already knows.

## What a 5-year-old knows

Use only this world. Anything outside it must be explained with something inside it.

| Area | Examples |
|---|---|
| Home & family | mum, dad, siblings, grandma, kitchen, bed, bath, the fridge |
| Food | apples, bread, ice cream, cookies, juice, sharing a pizza |
| Toys & play | blocks, LEGO, a ball, a slide, hide and seek, a puzzle, sandbox |
| Animals | dogs, cats, ants, bees, birds, fish |
| Body | eating, sleeping, breathing, being tired, hurting a knee, growing |
| Nature & weather | sun, rain, snow, trees, puddles, day and night |
| Places | kindergarten, playground, shop, park, doctor |
| People's jobs | firefighter, postman, baker, teacher, bus driver |
| Feelings & rules | happy, sad, scared, taking turns, saying sorry, waiting |

A 5-year-old **cannot** do: percentages, big numbers (above about 20), abstract
words ("system", "process", "data", "energy"), reading more than a few words at once.

## Workflow

1. **Find the one big idea.** What is the single thing the child should take
   away? Drop everything else. A computer network is "computers passing notes",
   not routing, packets and protocols.
2. **Pick one picture world.** Choose one analogy from the table above and stay
   in it for the whole explanation. Do not switch from a kitchen to a playground
   halfway through.
3. **Tell it as 3–5 picture steps.** Each step = one picture + one or two
   short sentences. The steps form a little story: something happens, then
   something else, then the result.
4. **Say the big idea in one sentence.**
5. **Give a "Try it!"** — something the child can do or look at at home that
   shows the idea (a game, a kitchen experiment, something to spot outside).
6. **Add "For grown-ups"** — 2–4 plain sentences on what the picture leaves out
   or simplifies, so the adult reading along knows the real story.

## Pictures

Every step has a picture. Use the best kind your environment can show:

1. **A real drawing**, if you can render images or SVG (an inline visual, an
   artifact, an image tool). Simple shapes, bright colours, big objects, a face
   or two, no text except one-word labels. One picture per step, or one strip
   with all steps.
2. **An emoji scene** otherwise — a row of emoji that shows what happens:
   ```
   🍎 ➡️ 😋 ➡️ 💪
   ```
3. **A small ASCII drawing** when position or shape matters:
   ```
        ☀️
       /  \
      🌱   💧
   ```

Pictures carry the explanation; the sentences only say what the picture shows.
If a step needs a long sentence, the picture is wrong — redraw it.

## Words

- Sentences of about 10 words or fewer. One idea per sentence.
- Short, everyday words. No technical term, unless the topic *is* the word —
  then name it once, after the picture has explained it ("This is called a
  *virus*.").
- Talk to the child: "Imagine you…", "Do you know how…?"
- Numbers only up to about 10, and only when you can show them (🍪🍪🍪).
- Write in the user's language.

## Honest, not false

Simplify, but do not say things that are wrong and must be unlearned later.
"The sun is a very, very big fire far away" is a fine simplification. "The sun
goes around the Earth" is false. If the simple picture bends the truth a bit,
say so in "For grown-ups".

## Output format

```markdown
# <Topic>, for a 5-year-old

**Imagine …** <one sentence that opens the picture world>

### 1. <short step title>
<picture>
<1–2 short sentences>

### 2. …
(3–5 steps)

### ⭐ The big idea
<one sentence>

### 🖐️ Try it!
<one small thing to do or spot at home>

---
*For grown-ups:* <2–4 sentences on what the picture simplifies or leaves out>
```

## Self-check before output

- [ ] One big idea only; everything else is dropped
- [ ] One picture world, kept from start to end
- [ ] 3–5 steps, each with a picture
- [ ] No sentence longer than about 10 words in the child's part
- [ ] No technical word without a picture first; no number above about 10
- [ ] Nothing false, only simplified; simplifications named for grown-ups
- [ ] A "Try it!" the child can really do
