---
name: handbook-writer
description: Creates practical subject handbooks as pure Markdown documents (never PDF, DOCX or HTML) in a fixed structure (cover block + 20 chapter sections, motto line, numbered boxes, Key Takeaway/Pro Tip, closing checklist), without any publisher or brand branding. Use this skill whenever someone wants a handbook, guide, production handbook, cheat-sheet booklet, interview/scenario handbook, field guide or study booklet on a technical, professional or role-based topic (e.g. "create a Kubernetes handbook", "write me a handbook on product ownership", "Erstelle ein Handbook zu Terraform"), even if they don't mention "structure" or "template", and when an existing handbook should be brought into this structure.
---

# Handbook Writer

This skill produces handbooks as **Markdown documents** in the style of a compact study-booklet series: **one cover block and 20 chapters, each chapter one self-contained `##` section**. Every chapter stands on its own; together they form an arc from fundamentals to production readiness. The structure was modelled on printed booklets with one page per chapter. In Markdown that "page" is simply a chapter section, so there is no page layout, page numbering or print formatting to reproduce. The full structure description with all tables is in `references/structure.md`. A fill-in template is in `assets/template.md`.

## Workflow

1. **Clarify topic, audience and scope.** If something essential is missing, ask briefly. Otherwise fill in sensible assumptions yourself and state them at the end. Scope constraints set by the user (e.g. "pure PO role, there is a separate PM") run through the whole booklet: into the role tables, examples, anti-patterns and the checklist. They are not a footnote in chapter 1.
2. **Choose the handbook type** (details in `references/structure.md`, section 4):
   - *Teaching/production handbook* (default): from fundamentals to production readiness
   - *Scenario/interview handbook*: every chapter is a problem case
   - *Reference/command handbook*: thematic command groups
   - *Workflow handbook*: follows a real-world process
   - *Beginner handbook*: like the default, with more setup and explanation
3. **Draft the chapter list** (20 titles) following the arc of the chosen type. Before writing, check that each chapter covers exactly one topic and that the order builds up logically.
4. **Write the cover, 20 chapters and closing line** in the format below.
5. **Self-check** (see below), then output.

## Output format

The deliverable is **one Markdown document**, delivered as a chat message. If the user asks for a file, save it as a single `.md` file. Do not create PDF, DOCX, HTML or slides, and do not run conversion tools such as pandoc or a PDF skill. The handbook is meant to be read, edited and versioned as plain Markdown. If the user explicitly wants another format later, that is a separate step outside this skill.

Use only standard GitHub-flavoured Markdown: headings, blockquotes, tables, lists, task lists and fenced code blocks. Draw diagrams as ASCII inside code blocks, not as images or Mermaid. Separate the cover, chapters and closing line with `---`.

### Cover
```markdown
# <TOPIC> HANDBOOK

> ### <Subtitle: "From <foundation> to <production goal>">
> *<One sentence on focus/scope>*
>
> <Emoji> <sub-area> · <Emoji> <sub-area> · … (4–6 topic tiles)
>
> **BEGINNER FRIENDLY · TEMPLATES & EXAMPLES · REAL-WORLD SCENARIOS · CHECKLISTS · PRODUCTION READY**
>
> *<Three-part slogan, e.g. "Clear role. Clear backlog. Clear value.">*
```

### Each chapter section (1–19)
```markdown
## <n>. <CHAPTER TITLE IN CAPITALS>

> "<Motto: one punchy sentence carrying the chapter's core idea>"

### ① <Box title>
…
### ② <Box title>
…
(3–6 boxes)

> **🔑 KEY TAKEAWAY**   or   > **💡 PRO TIP**
> <1–2 sentences>
```
Alternate KEY TAKEAWAY and PRO TIP, roughly 1:1. A takeaway sums up the chapter; a pro tip gives one concrete move.

### Chapter 20 (wrap-up)
A checklist ("<Topic> Readiness Checklist", "Production Readiness Review", "Final Review" or similar). Group it into 5–8 thematic blocks with emoji headings and `- [ ]` items that cover the earlier chapters. Then a closing line:
```markdown
---
> *<Maxim for the whole booklet>*
> **<THREE · KEYWORDS · IN CAPITALS>**
```

## Building blocks for the boxes

Fill the boxes from this repertoire. A chapter comes alive through the mix: **explanation → table or code/template → flow → practical case**. Five paragraphs of prose do not make it come alive.

| Block | Form |
|---|---|
| Definition / What is … | 2–3 sentences |
| Commands, code, configuration | code block with language; for non-technical topics use templates instead (story format, agenda, form) |
| Comparison or reference table | e.g. option / purpose / when to use; ✅/❌ contrast |
| Flow / architecture | numbered steps or ASCII diagram in a code block |
| Real-world scenario | concrete case with numbers and an outcome |
| Best practices | short list |
| Common mistakes / anti-patterns | table *recognisable by → remedy* |
| Troubleshooting | table *symptom → cause → fix* |
| Checklist | `- [ ]` items |
| RACI / role matrix | when responsibilities are part of the topic |
| Interview angle | typical question + key answer |

The blocks are a toolbox, not a mandatory scheme: in each chapter use what the topic supports. Across the whole booklet, tables, code or templates and scenarios should appear regularly. Readers pick up a booklet like this because they want something they can apply.

## Chapter arc (default type)

| Phase | Chapters | Typical content |
|---|---|---|
| 1. Entry | 1–2 | What X is, architecture or role model |
| 2. Setup | 2–4 | Installation, setting up, "Your first …" |
| 3. Core concepts | 4–11 | one concept per chapter, ascending |
| 4. Integration | ~10–14 | X with tool A / role B / neighbouring system |
| 5. Operations & hardening | ~12–17 | security, observability/metrics, scaling, quality |
| 6. When things break | ~15–19 | troubleshooting, anti-patterns, disaster recovery, case study |
| 7. Wrap-up | 20 | readiness checklist / final review |

For scenario, reference and workflow handbooks, use the respective arc from `references/structure.md` instead. Multi-volume or large booklets (40/60 chapters) stretch the same arc. Only do this when explicitly asked.

## Branding

Handbooks are **brand-neutral**: no publisher name, no logo placeholder, no social media handles, no copyright line. Cover and closing line carry only the title, subtitle, topics, badges and slogan. If the user wants their own brand, use exactly that one and never invent one.

## Language and tone

- Write in the user's language. Common technical terms stay in their usual form (backlog, deployment, rollback).
- Address the reader directly ("you").
- Stay concrete: real commands, realistic numbers, named tools. Platitudes like "communication matters" only when paired with a concrete move.
- Motto lines are short and punchy and may be pointed.

## Self-check before output

- [ ] Cover + exactly 20 chapters, numbered, chapter 20 is the checklist
- [ ] Each chapter has a motto line, 3–6 numbered boxes and a takeaway or pro tip
- [ ] The arc fits the chosen type; no chapter repeats another
- [ ] The user's scope constraints are visibly applied across several chapters
- [ ] At least half the chapters contain a table, a code/template block or a scenario
- [ ] No branding
- [ ] Output is a single Markdown document: no PDF/DOCX/HTML, no page numbers, no images

After the handbook, add at most 2–3 sentences: which type was chosen, which assumptions were made, and what could easily be adjusted.
