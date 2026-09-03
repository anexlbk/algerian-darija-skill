# Contributing

This skill gets better the more real Darija goes into it. A few rules keep it useful instead of turning into another noisy scraped dump.

## What to add

- A word, expression, or grammar pattern you can vouch for as real, current Algerian Darija
- Regional variants (label the region: Algiers/central, Oran/west, Constantine/east, south) if something differs from the default
- Corrections to anything already in the reference files that's wrong, outdated, or too Moroccan/Tunisian-leaning
- New categories if something is missing entirely (e.g. business/admin vocabulary, youth slang, religious-context phrases)

## What not to add

- Explicit sexual content, slurs, or insults, even if "that's how people actually talk." Authenticity is not the only bar. If a pull request is mostly a vocabulary list of vulgar terms, it will be rejected regardless of accuracy.
- Content about specific named private individuals (gossip, insults tied to a real person's name). General slang is fine, personal attacks are not.
- Political or religiously inflammatory content framed as "vocabulary."
- Unverified scraped text dumped wholesale. If you're adding from a dataset or scrape, pull out the specific useful patterns and cite the source, don't paste in raw walls of text.

## Format

- Follow the existing table format in the relevant reference file (`phrasebank.md` for chat/function words, `loanwords.md` for borrowed vocabulary, `narrative-patterns.md` for storytelling/narration structure).
- If your addition doesn't fit an existing file, propose a new `reference/<topic>.md` file and add a line for it in `SKILL.md`'s "Before responding" section so Claude knows when to check it.
- Keep entries short: word/phrase, meaning, one line of usage notes if needed. This is a reference for a model to check quickly, not an essay.

## Sourcing

Note where an entry came from when you can (a specific dataset, a personal check, a regional source). Entries with no traceable basis are more likely to get questioned or removed later. This isn't bureaucracy for its own sake, the last dictionary dataset mined for this project had real quality problems mixed in with good entries, and unsourced additions are how that happens again.

## Testing your change

Before opening a PR, try prompting Claude with the skill installed and see if the output actually sounds different/better with your addition versus without it. If it doesn't change anything observable, it probably doesn't need to be in the skill.
