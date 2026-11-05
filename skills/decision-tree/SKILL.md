---
name: decision-tree
description: Build a Mermaid tree to explore a problem, compare choices, or trace decisions and their consequences.
---

# Decision tree

Turn the user's problem into a Mermaid flowchart that supports the decision or analysis they need to make.

## Frame the problem

Identify the question the tree must answer and the perspective of the person using it. Use the user's stated objective and constraints. If a missing fact would change the tree's structure, ask for it; otherwise state a reasonable assumption and continue.

Choose the root to match the task:

- **Decision:** the choice to make. Branches represent options, followed by conditions, consequences, or further decisions.
- **Analysis:** the outcome or problem to investigate. Branches decompose it into causes, factors, or hypotheses.
- **Diagnostic:** the symptom or question to resolve. Branches represent observable checks and their possible results.

## Research

When the tree's nodes, steps, or edges require factual research, use the `perplex-deep` skill to investigate the material subquestions. Use its evidence and identified gaps to shape the branches; distinguish sourced findings from assumptions and inferences. Link evidence near the corresponding claims in the explanation accompanying the tree.

## Build the tree

Expand each branch until its leaves identify an actionable choice, a consequence, a testable hypothesis, or a clearly stated unknown. Match the level of detail to the user's question.

Make sibling branches distinct and cover the meaningful possibilities. Include an "other" or "unknown" branch where the available information does not support an exhaustive split. Label edges with the condition, result, or option that leads to the next node.

Separate facts provided by the user from assumptions. Mark uncertain outcomes as uncertain and identify missing evidence to investigate. If the user asks for a recommendation, identify the criteria and explain how they affect the preferred branch.

## Deliver and check

Present the question the tree answers and any assumptions needed to read it, followed by a Mermaid `flowchart` in a fenced code block. End with the main takeaway and the next information or action that would move the analysis forward.

Check that every path starts at the root and ends at a meaningful leaf, every decision or check has labeled outgoing branches, and the Mermaid syntax is valid. Keep node labels concise and quote labels containing punctuation or special characters.
