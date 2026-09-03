---
name: algerian-darija
description: Use when the user writes to Claude in Algerian Darija, asks Claude to reply or write in Darija/Algerian Arabic, or asks for something to sound like a "real Algerian" (chat, captions, comments, casual copy). Makes Claude respond in authentic Algerian street Darija instead of Modern Standard Arabic or generic "Arabic dialect."
---

# Algerian Darija

Algerian Darija is not MSA with a few words swapped. It has its own grammar, its own function words, and heavy code-switching with French (and some Berber/Spanish/Turkish loanwords in specific regions). Claude's default instinct when asked to "speak Arabic dialect" is to lean MSA-with-accent, which reads as fake to an actual Algerian. This skill corrects that.

## Before responding

1. Check `reference/phrasebank.md` for authentic function words, verb patterns, and expressions before writing Darija content of any real length (more than a couple of sentences).
2. If the task involves French/Spanish/Turkish/Berber loanwords, or the user wants a specific term rendered naturally, check `reference/loanwords.md` first rather than guessing or over-translating into MSA. Each entry is tagged `common` / `regional` / `rare` — default to `common` entries unless the user's context specifically calls for a regional or rare one.
3. If the task is a story, anecdote, or any longer narrated piece (not chat), check `reference/narrative-patterns.md` for how narration, dialogue, and scene transitions actually work in written Darija.
4. Match the user's own script. If they wrote in Arabic script, reply in Arabic script. If they wrote in Arabizi/Latin letters (numbers standing in for letters like 3=ع, 7=ح, 9=ق), reply in Arabizi. Don't switch script on them.
5. Match their register. WhatsApp message to a friend ≠ a formal caption ≠ marketing copy ≠ a written story. Darija flexes a lot by context.

## Core rules

**Grammar, not just vocabulary**
- Present tense uses the "ka-/ta-" or bare imperfect depending on region; Algiers-area Darija commonly drops MSA's dual and most case endings entirely. Don't invent MSA-style endings.
- Negation wraps the verb: "ma-...-ch" (مانيش، ماكانش، مانحبش) — this is the single most distinctive marker of Darija and gets missed constantly. "ما نحبش" not "لا أحب."
- Possession usually goes through "ديال / تاع" (dyal / taa3) rather than MSA's idafa construction: "الكتاب تاعي" not "كتابي" in casual speech (both exist, but tاع/ديال is the natural spoken form).
- Future is "غادي/راح" + verb, not MSA's سـ prefix.

**Code-switching is normal, not sloppy**
- French words are used for tech, admin, education, workplace, and modern-life concepts even mid-sentence: "نروح نخدم" but "عندي réunion", "بصح", "franchement", "quoi", "voilà" scattered naturally. This isn't a mistake to clean up — it's how people actually talk.
- Don't overdo it either. French insertion should feel like a native speaker code-switching, not a French sentence with Arabic words sprinkled in. When unsure, keep the sentence spine in Darija and let 1-2 words be French.

**Vocabulary that signals "not MSA"**
Use `reference/phrasebank.md` for the fuller list, but the highest-signal swaps: واش (what, not ماذا), كي/كيفاش (when/how, not متى/كيف), بزاف (a lot, not كثيرا), دروك (now, not الآن), راه/راهي (emphasis/"indeed", no MSA equivalent), وقتاش (when), هاد/هاذ (this, not هذا), حنا (we, not نحن), نتا/نتي (you, not أنت/أنتِ), واحد النهار (one day — literal calque, common), يا سيدي / خويا / خوتي as address terms.

**Tone**
Real Darija in casual contexts is direct, often self-deprecating or teasing, uses religious expressions naturally and non-performatively (إن شاء الله، الحمد لله، ربي يعاون), and isn't afraid of blunt humor. Don't sanitize it into polite MSA tone while keeping Darija words — that's the "fake Algerian" failure mode.

## What to avoid

- Don't default to Moroccan or Tunisian Darija markers (e.g. Moroccan "ديال" is fine, but avoid heavy Moroccan-specific slang or Tunisian "برشا"/"إيمالا" unless the user is clearly coding for that dialect).
- Don't write a grammatically MSA sentence and just swap 2-3 words for "Darija flavor." If the sentence structure would work in a Cairo newspaper, it's not Darija yet.
- Don't over-translate French loanwords back into Arabic when a French word is what a real speaker would use (e.g. "portable" for phone, "gaz" for gas, is normal — forcing "هاتف" reads stiff).

## Regional note

Algeria's Darija varies (Algiers/central, Oran/west with more Spanish influence, Constantine/east, deep south with more Berber influence). Default to widely-understood central/Algiers-style Darija unless the user specifies a region or their own writing signals one.

## Sources

Built from patterns in raw social/YouTube-comment Darija text, an AI-translated children's-story corpus (for narrative register), and a filtered subset of a crowdsourced Darija dictionary (loanwords and expressions only — the dictionary's own card flags it as noisy/spammy, so slang not cross-checked against other sources was left out). Add new phrases to the relevant reference file as they come up rather than creating new files per source.
