# Algerian Darija Skill for Claude

A Claude Skill that makes Claude respond in real Algerian Darija (chat, street, narrative, and commercial registers) instead of Modern Standard Arabic with a few words swapped.

Most models default to "Arabic dialect" that reads as MSA wearing a costume: correct vocabulary, wrong grammar, no code-switching, sanitized tone. This skill fixes the grammar (the ma-...-ch negation pattern, ديال/تاع possession, غادي future), restores natural French code-switching, and gives Claude a curated phrasebank instead of letting it guess.

## What's in here

```
algerian-darija/
  SKILL.md                        core rules: grammar, code-switching, script/register matching
  reference/
    phrasebank.md                 chat-register function words, negation, common verbs, expressions
    loanwords.md                  French/Spanish/Turkish/Berber loanwords, confidence-tagged (common/regional/rare)
    narrative-patterns.md         story/narration register (openers, scene transitions, dialogue)
    commercial-copy.md            business/marketing register: CTA phrasing, brand voice, platform formatting
```

## Install

**Claude.ai / Claude apps with custom skills:** upload the `algerian-darija/` folder as a skill.

**Claude Code:** drop the `algerian-darija/` folder into `.claude/skills/` in your project (or your user-level skills directory).

**Other environments that support the Skill format:** place `algerian-darija/` wherever that environment loads skills from.

Once installed, Claude should pick it up automatically when you write to it in Darija or ask for Darija output. No configuration needed.

## Example

> **Prompt:** "قولي كيفاش نحضر قهوة بالحليب"
>
> **Without the skill (typical MSA-leaning output):** كيف يمكنني تحضير قهوة بالحليب... (correct Arabic, wrong dialect, reads like a textbook)
>
> **With the skill:** راك تحتاج قهوة، حليب، وسكر... خلي الحليب يسخن شوية، بعدها زيد القهوة... ماتنساش السكر واش تحب

## What's confidence-tagged

`loanwords.md` tags every entry `common`, `regional`, or `rare` so Claude defaults to widely-understood vocabulary and only reaches for a regional or rare word when the context specifically calls for it. This matters more than it sounds: an early version of this skill's loanwords file used Moroccan-coded transliteration (پ/گ) for some French borrowings, which is exactly the kind of error that reads as fake to an actual Algerian even when the underlying word choice is fine. That's been corrected; Algerian written Darija uses ب for the French p-sound and ڨ (or غ/ق) for the hard g-sound, not پ/گ.

`commercial-copy.md` similarly flags which of its sections are grounded in real observed data versus built from judgment and the grammar rules elsewhere in this skill. Check that file's grounding note before treating every line in it as equally verified.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). Short version: additions need to be real, checkable Darija (not guessed, not unverified scraped noise), and explicit/vulgar/slur content is out of scope regardless of how "authentic" it is. If you're contributing a dataset-sourced fact, double-check it's actually Algerian and not Moroccan or Tunisian Darija mislabeled: dabâ (دابا) for "now" instead of درك/توا is the fastest tell of Moroccan content passed off as Algerian, and it has shown up more than once in datasets labeled "Algerian" on public hubs.

## Sources

Built from patterns found in:
- [ayoubkirouane/Algerian-Darija](https://huggingface.co/datasets/ayoubkirouane/Algerian-Darija): raw social/YouTube-comment text (chat register)
- [touati-kamel/TinyStories-Algerian-Darija](https://huggingface.co/datasets/touati-kamel/TinyStories-Algerian-Darija): AI-translated children's stories (narrative register)
- [awras/algerian-darija-dictionary-v1](https://huggingface.co/datasets/awras/algerian-darija-dictionary-v1): crowdsourced dictionary (loanwords/expressions only; the raw dataset is noisy and was filtered, not used wholesale)
- a large corpus of real Algerian property-marketplace listings: CTA phrasing and platform-formatting conventions only (commercial-copy.md), not grammar. License/attribution terms for this source weren't clearly stated on the hub listing, so nothing from it is reproduced verbatim here, only generalized patterns.

Two other candidates considered during development were excluded entirely after inspection: both were labeled "Algerian" but their actual text/audio content (heavy دابا for "now", Moroccan dirham references, named Moroccan political parties) showed they were Moroccan Darija mislabeled. They were not partially used or cross-checked against; they were dropped outright once identified, since even keeping them as a "reference to filter against" risks quietly reintroducing Moroccan-coded vocabulary into this skill.

These datasets are not redistributed here. This repo contains derived reference material (curated tables, rules, examples) written from patterns observed in them, not the datasets themselves.

## License

[CC BY 4.0](LICENSE): matches the license of the source datasets. Attribution appreciated if you fork or redistribute.