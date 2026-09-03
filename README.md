# Algerian Darija Skill for Claude

A Claude Skill that makes Claude respond in real Algerian Darija (chat, street, and narrative registers) instead of Modern Standard Arabic with a few words swapped.

Most models default to "Arabic dialect" that reads as MSA wearing a costume: correct vocabulary, wrong grammar, no code-switching, sanitized tone. This skill fixes the grammar (the ma-...-ch negation pattern, ديال/تاع possession, غادي future), restores natural French code-switching, and gives Claude a curated phrasebank instead of letting it guess.

## What's in here

```
algerian-darija/
  SKILL.md                        core rules: grammar, code-switching, script/register matching
  reference/
    phrasebank.md                 chat-register function words, negation, common verbs, expressions
    loanwords.md                  French/Spanish/Turkish/Berber loanwords, filtered for quality
    narrative-patterns.md         story/narration register (openers, scene transitions, dialogue)
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

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). Short version: additions need to be real, checkable Darija (not guessed, not unverified scraped noise), and explicit/vulgar/slur content is out of scope regardless of how "authentic" it is.

## Sources

Built from patterns found in:
- [ayoubkirouane/Algerian-Darija](https://huggingface.co/datasets/ayoubkirouane/Algerian-Darija) — raw social/YouTube-comment text (chat register)
- [touati-kamel/TinyStories-Algerian-Darija](https://huggingface.co/datasets/touati-kamel/TinyStories-Algerian-Darija) — AI-translated children's stories (narrative register)
- [awras/algerian-darija-dictionary-v1](https://huggingface.co/datasets/awras/algerian-darija-dictionary-v1) — crowdsourced dictionary (loanwords/expressions only; the raw dataset is noisy and was filtered, not used wholesale)

These datasets are not redistributed here. This repo contains derived reference material (curated tables, rules, examples) written from patterns observed in them, not the datasets themselves.

## License

[CC BY 4.0](LICENSE) — matches the license of the source datasets. Attribution appreciated if you fork or redistribute.
