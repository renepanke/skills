# Handbook Structure (Reference)

Detailed reference for the `handbook-writer` skill. Derived from a series of about 80 printed subject handbooks (DevOps, cloud, CI/CD, IaC, databases and more), translated into a **pure Markdown format**; brand-neutral.

The source booklets were laid out as one printed page per chapter. In Markdown there are no pages: a "page" becomes one `##` chapter section, and the visual elements of the print layout map to Markdown constructs as shown below.

---

## 1. Key Facts

| Attribute | Value |
|---|---|
| Output format | **one Markdown document** (`.md` or chat message); no PDF, DOCX, HTML or rendered pages |
| Length | **1 cover block + 20 chapters**; large volumes = 40 / 60 chapters (only on request) |
| Unit | **1 chapter = 1 `##` section**, numbered 1–20 |
| Separation | `---` horizontal rule between cover, chapters and closing line |

---

## 2. Section Types

### 2.1 Cover block (top of the document)
| Print element | Markdown |
|---|---|
| Title | `# <TOPIC> HANDBOOK` |
| Subtitle | blockquote with `###` subtitle + one italic sentence on focus/scope |
| Topic tiles/icons | one blockquote line: `<emoji> <sub-area> · …` (4–6 items) |
| Badge bar | one bold line in capitals, items separated by ` · ` |
| Slogan | one italic line |

### 2.2 Chapter section (chapters 1–19) – fixed skeleton
```markdown
## <n>. <CHAPTER TITLE IN CAPITALS>

> "<motto sentence>"

### ① <box title>
<content>

### ② <box title>
<content>

(3–6 boxes, numbered ①–⑥)

> **🔑 KEY TAKEAWAY**  or  > **💡 PRO TIP**
> <1–2 sentences>

---
```

| Print element | Markdown |
|---|---|
| Page header with number | `## n. TITLE` (no "PAGE n / OF 20" counter) |
| Motto line | blockquote with the sentence in quotation marks |
| Numbered content box | `### ①` … `### ⑥` subsection |
| Diagram (hand-drawn style) | numbered list or ASCII diagram inside a code block |
| Takeaway / tip strip | blockquote with bold emoji label |

### 2.3 Final chapter (chapter 20)
Always a summary, in one of these variants:
*Master Checklist* · *Production Readiness Checklist/Review* · *Final Review* · *Final Mock Interview* · *Final (Practical) Project* · *Mastery Roadmap*
Format: 5–8 `###` blocks with emoji headings and `- [ ]` task-list items, followed by `---` and a two-line closing blockquote.

---

## 3. Building Blocks for Boxes

The boxes are filled from a fixed repertoire, but not according to a mandatory scheme.
Shares = how often the block appears on a chapter in the source handbooks (orientation, not a quota).

| Block | Share | Markdown form |
|---|---|---|
| Commands / code / config example | ~80 % | fenced code block with language tag (`bash`, `yaml`, `hcl`, `gherkin` …) |
| Pro Tip | ~27 % | closing blockquote |
| Best Practices | ~23 % | bullet list |
| How it works / architecture | ~20 % | numbered steps or ASCII diagram in a code block |
| Troubleshooting | ~18 % | table: symptom → cause → fix |
| Real-World / Production Scenario | ~15 % | short paragraph with numbers and outcome |
| What is / Overview | ~15 % | 2–3 sentences |
| Security | ~15 % | list or table |
| Key Takeaway | ~14 % | closing blockquote |
| Checklist | ~12 % | `- [ ]` task list |
| Option/Purpose/When-to-use table | frequent | Markdown table |
| Common Mistakes / Anti-Patterns | ~8 % | table: recognisable by → remedy |
| Interview angle | ~8 % | bold question + answer |

**Typical order within a chapter:** concept/explanation → table or commands → flow diagram → practical/failure scenario → Key Takeaway/Pro Tip.

---

## 4. Chapter Arc (Macro Structure)

### 4.1 Standard: teaching/production handbook (majority)

| Phase | Chapters (of 20) | Typical titles |
|---|---|---|
| 1. Entry | 1–2 | Introduction to X · What X is · Overview · X Architecture |
| 2. Setup | 2–4 | Installing X · Your first project/job · Bootstrap |
| 3. Core concepts | 4–12 | one concept per chapter, from simple to complex |
| 4. Integration | ~10–14 | X with Jenkins / Kubernetes / Helm / Docker |
| 5. Operations & hardening | ~12–17 | Security · RBAC · Secrets · Observability · Logging · Scaling · Performance |
| 6. When things break | ~15–19 | Troubleshooting · Disaster Recovery · Anti-Patterns · Production Case Study |
| 7. Wrap-up | 19–20 | Cheat Sheet · Production Readiness Checklist · Final Review · Final Project |

In 40/60-chapter volumes the same arc is stretched, e.g. CKA: fundamentals → workloads → networking → storage → security → troubleshooting → exam technique → mock exams → quick reviews → readiness assessment.

Example (Argo CD Production Handbook):
1 GitOps & architecture · 2 Installation & design · 3 Applications · 4 Reconciliation/sync · 5 Sync policies · 6 Sync waves & hooks · 7 Repository design · 8 Helm · 9 Kustomize · 10 ApplicationSet · 11 (Projects) · 12 Auth/RBAC/SSO · 13 Secrets · 14 Multi-cluster · 15 Progressive delivery · 16 Notifications · 17 Observability · 18 Troubleshooting · 19 DR/upgrades/security · 20 Enterprise architecture

### 4.2 Variants

| Type | Recognisable by | Chapter structure | Chapter content |
|---|---|---|---|
| **Scenario/interview handbook** | "Interview", "Scenarios", "40 Real-World …" | each chapter = one production problem ("Disk is 100 %", "Terraform wants to destroy …") | symptom → investigation/commands → cause → fix → prevention |
| **Reference/command handbook** | e.g. "Linux Production Handbook" | thematic command groups (process, user, network, storage, logs, packages …), no teaching arc | command tables |
| **Workflow handbook** | "Daily Operations", "Migration", "Takeover" | follows the real-world flow (start of day → … → handover; assessment → 7 Rs → planning → migration → testing → cutover → rollback → post-migration) | steps + checklists |
| **Beginner handbook** | "for Beginners", "from Zero" | like standard, but more setup/"Your first …", ending with "Beginner Checklist/Project" | more explanation, less enterprise |
| **Case file** | incident write-ups | one narrative incident instead of teaching chapters | timeline → impact → root cause → fix → lessons |
