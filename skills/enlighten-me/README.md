# enlighten-me

Understand language model output through the explanation formats described in [Andrej Karpathy's post](https://x.com/karpathy/status/2105819303471976479).

The supplied article text and image are saved in [the source reference](references/karpathy-post.md).

## What it does

- **Writing:** explain in ASD-STE100, or soften it to "80% of the way" when the full specification is too strict.
- **Diagrams and images:** make the explanation easier to process and understand through visuals.
- **Web pages:** create an interactive HTML page, including animations.
- **Explainer videos:** create a custom video for the topic with visuals and audio narration.

The post moves toward richer explanation formats and is most enthusiastic about custom explainer videos. It does not give a required four-step process or a default rule to choose the simplest format.

Its larger idea is custom output that helps the user understand something and can then be discarded. The skill contains the article's guidance, without added personal writing preferences or an implementation checklist.

## Examples

```text
$enlighten-me Explain this model output in ASD-STE100.

$enlighten-me Explain this topic about 80% of the way to ASD-STE100.

$enlighten-me Create a diagram to explain this topic.

$enlighten-me Explain this topic in an interactive HTML page.

$enlighten-me Create a custom video explainer on this topic with audio narration.
```

## Installation

Keep the whole skill folder together so its references remain available. For personal use in Codex, copy `enlighten-me/` into `~/.codex/skills/`, or into `skills/` under your `CODEX_HOME` if it is set. Preserve an existing copy before replacing it. Start a new chat, then use `$enlighten-me`.

Video creation needs tools that can produce video and audio. The article mentions ElevenLabs for narration and free alternatives that use local computing resources.

## Files

- [SKILL.md](SKILL.md): instructions based on the article.
- [agents/openai.yaml](agents/openai.yaml): the name and starter prompt shown in Codex.
- [Karpathy's supplied post](references/karpathy-post.md): source text and image.

This is a skill inspired by Andrej Karpathy's post, not an official skill by him.
