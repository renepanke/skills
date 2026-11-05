# Writing style

Apply this light form of Simplified Technical English, adapted from the
[ste-writing skill](https://github.com/1fc0nfig/ste-writing) by Ege Çelebi and
Matyas Cerny (MIT), to user-facing text. It is not a certified ASD-STE100 check.

- Write short sentences, normally no more than 25 words. Use active voice and
  name the actor. Use verbs for actions and familiar words where they fit.
- Use one consistent name for each thing. Avoid filler, stacked hedges,
  marketing language, semicolons, and dashes in prose. Use lists when they make
  parts or steps easier to follow.
- In English, prefer common words, avoid contractions, and keep articles.
  In other languages, use the same principles with natural local wording.
- Apply the style to prose, captions, and diagram labels. Preserve the user's
  language, requested format, essential technical terms, accuracy, and citations.
  Do not rewrite code, identifiers, commands, or quoted source material.
- Before delivery, check sentence length, voice, word choice, and consistency.
  For substantial English prose, when Python is available, run
  `python3 <skill-directory>/scripts/ste-lint.py < draft.md`, fix useful findings,
  and run it again. The linter is a mechanical aid, not a content check. Do not
  chase a zero score or lint other languages.
