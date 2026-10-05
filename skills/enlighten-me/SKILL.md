---
name: enlighten-me
description: Help users understand language model output through ASD-STE100 writing, diagrams or images, interactive HTML pages, or custom narrated explainer videos. Use for explanation requests, based on the formats described in Andrej Karpathy's post.
---

# Enlighten Me

Help the user understand language model output using the ideas in Andrej Karpathy's post.

As models do more work autonomously, more human work will focus on oversight and understanding. Models can help with this too by creating explanations in richer formats.

## Explanation formats

The post moves from writing to diagrams, web pages, and explainer videos, introducing each next format with "But even better." These are explanation formats, not a required sequence of four steps. Karpathy expresses the strongest interest in custom explainer videos.

### Writing

Explain using ASD-STE100, a controlled English specification originally developed for aerospace maintenance documentation. Its constraints on writing can make explanations easier to read.

When the full specification is too strict, soften it to "80% of the way to ASD-STE100," as Karpathy suggests.

The [supplied overview image](references/karpathy-post.png) shows writing rules such as using the same word for the same thing, active voice in procedures, and one topic per paragraph. Use that image when applying the writing guidance shown in it.

### Diagrams and images

Create a diagram or image instead of relying only on writing. Visual explanations can be easier to process and understand.

### Web pages

Create output in HTML as an interactive web page. Use interactions and animations to help explain the topic.

### Explainer videos

Create a fully custom explainer video for the topic, with visuals and audio narration.

Karpathy's example is a 3b1b-style video explainer with ElevenLabs used for narration. ElevenLabs requires an API key; the post also suggests finding suitable free alternatives that use local computing resources.

## Custom, discardable output

Create explanations for a specific question, including custom web apps or video explainers. These can be large, purpose-built outputs that the user can discard after use. As intelligence and code become more abundant, such outputs can make sense to create where they did not before.

## Source

Read [the supplied article text](references/karpathy-post.md) for the original wording and [the attached image](references/karpathy-post.png) for its ASD-STE100 overview. They are the source of truth for this skill's account of Karpathy's ideas.
