---
name: voice-profile
description: Use when someone asks to capture their voice, tone or writing style, or when copy and content work has no voice file yet. Builds a written voice profile for a person or brand from a short interview and three to five real texts they wrote, and saves it as about-me.md and voice.md. Asks before starting the interview.
disable-model-invocation: true
---

# Voice profile

Copy written "in your voice" without a reference ends up in the model's voice. A voice profile fixes that with two short files built from evidence: who the person is (`about-me.md`) and how they write (`voice.md`).

## Before anything else

This skill does not start on its own. When it loads, ask first:

1. Whose voice is this (a person or a brand), and where should the files go? Default: `.agents/about-me.md` and `.agents/voice.md`.
2. Do they want to do the interview now (about ten minutes) and can they share three to five texts they wrote themselves?

Wait for a yes. If the files already exist, offer to update them instead of starting over.

## Interview

Ask a few questions at a time and keep the answers in their own words:

- What they do, for whom, and what they want to be known for.
- The story behind it: how they got here, in two or three facts, not adjectives.
- Opinions they hold that others in their field would disagree with.
- Topics they always come back to, and topics they never touch.
- Words and phrases they use a lot, and ones they would never use.
- People or writers whose style they like, and what exactly they like about it.
- How formal they are with their audience (tú or usted, slang, emoji, swearing).

## Samples

- Three to five texts they wrote without help: posts, emails, talks, long messages. Several formats are better than five of the same kind.
- Texts written by someone else, by a tool or heavily edited do not count. Ask if unsure.
- Do not store the samples in the repo unless the owner asks; quote only short excerpts in `voice.md`.

## What to extract

From the samples, not from the interview alone:

- Sentence length and rhythm, and how they open and close a text.
- Vocabulary: recurring words, regionalisms, technical level, words they avoid.
- Structure: lists or prose, use of questions, stories, numbers.
- Stance: how direct they are, humor, how they disagree, how they ask for something.
- Formatting habits: line breaks, emoji, capitalization, punctuation.

When the interview and the samples disagree, trust the samples and note the gap.

## Files

`about-me.md`: one paragraph of who they are, the story facts, expertise, audience, opinions, topics in and out. Facts only, approved by them.

`voice.md`: a one-line summary of the voice, then "do" and "don't" lists with a short real example for each rule, the vocabulary lists, formatting habits, and per-channel notes if the voice changes by channel. Add a version and a changelog line.

## Rules

- Every rule in `voice.md` must point to evidence in a sample or an interview answer. No generic rules like "be authentic".
- Do not invent biography, credentials, clients or numbers for `about-me.md`. Unknown stays unknown.
- Show both files to the person and apply their corrections before saving them as final.
- Do not collect personal data the profile does not need (family, health, addresses, private messages of third parties).

## Output

The two file paths, the one-line voice summary, and what is still missing (for example "no samples of long-form writing").

## Known failures

_Record real mistakes here with a date and the rule that prevents them._
