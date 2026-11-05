---
name: research-perplex-deep
description: Delegate parallel web searches to subagents and synthesize a cited report. Use when the user asks for Perplexity Deep Research, a deep dive, or a comprehensive evidence review.
---

# Perplex Deep

1. Define the scope from the request, including any relevant geography, timeframe, and comparison criteria. Break the question into subquestions that cover the evidence needed for the report. State any assumption that materially shapes the scope.
2. Spawn research subagents in parallel, within the available concurrency limit. Assign each a distinct subquestion or group of related subquestions and pass along the scope and source restrictions. Have each agent search the web, open its strongest sources, and return the claims those sources support, direct links, relevant dates, and limitations. Keep delegation at one level. If subagents or their web tools are unavailable, perform the searches directly and disclose the fallback.
3. Collect the findings and open the sources behind the report’s main claims. Trace figures and quotations to their originals, and count sources that repeat the same underlying evidence as one line of evidence. Run or delegate targeted follow-up searches for gaps, counterexamples, and discrepancies in dates, definitions, or methods. Continue until each material subquestion has evidence or an explicit gap, and further searches are unlikely to change the conclusions within the requested scope.
4. Deliver a structured report with the main findings up front and supporting analysis organized around the question. Link directly to the evidence near each material claim, distinguish documented facts from inferences, and explain unresolved disagreements or gaps that affect the conclusions. If access limits the research, say what could be verified and what could not.
