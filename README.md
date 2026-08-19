# LLM Writing Style

A system prompt that combines **Absolute Mode** with controlled-English rules based on the principles of **ASD-STE100** (Simplified Technical English). It strips filler, hype, emojis, and follow-up prompts. It enforces short, active-voice, single-action sentences and clear structure.

Use it for technical writing, instructions, and blunt, scannable answers.

It works with any AI chat model. Paste the ruleset into a system prompt, custom instructions, or a persona field. It also ships as a native output style for [Claude Code](https://claude.com/claude-code).

## What it does

**Behavioral constraints (Absolute Mode):**

- Removes conversational filler, pleasantries, greetings, emojis, and soft closures.
- Disables engagement optimization, motivational framing, and sentiment mirroring.
- Suppresses unsolicited follow-up questions, next steps, and call-to-action appendixes.
- Ends the response when the requested material is complete.

**Linguistic and structural rules (based on ASD-STE100):**

- Direct, objective, and unambiguous language. One meaning per word.
- Active voice. Simple present, simple past, or imperative tense.
- Instruction sentences under 20 words. Description sentences under 25 words.
- One instruction or one action per sentence.
- Bulleted lists for related items. Numbered lists for sequential procedures.
- No idioms, metaphors, or passive filler phrases.

## Usage

### Any AI model (ChatGPT, Gemini, Claude, local models, ...)

Copy the ruleset from `absolute-ste100.md` (the text below the frontmatter). Paste it into:

- the system prompt / developer message, or
- the custom instructions / persona field, or
- the first message of a chat.

### Claude Code (native output style)

1. Copy `absolute-ste100.md` to your output-styles directory:

   - macOS / Linux: `~/.claude/output-styles/`
   - Windows: `%USERPROFILE%\.claude\output-styles\`

2. Activate it. Open the config menu and select the entry:

   ```
   /config
   ```

   Then go to **Output Style** and select **Absolute + ASD-STE100**.

### Claude Desktop and all Claude surfaces

Add this key to your `settings.json` (`~/.claude/settings.json`):

```json
{
  "outputStyle": "Absolute + ASD-STE100"
}
```

The value is the `name:` field from the file's frontmatter, **not** the filename. This is the most common install error.

## When not to use it

This style suppresses follow-up questions, hedging, and exploratory framing. It is unsuited to teaching, brainstorming, or open-ended discussion. Remove it, or switch back to the default via `/config` -> **Output Style**, when you need those.

## Attribution

ASD-STE100 (Simplified Technical English) is a specification owned by the [AeroSpace and Defence Industries Association of Europe (ASD)](https://asd-ste100.org/). This output style is inspired by its principles. It does not reproduce or redistribute the specification, its rule text, or its controlled dictionary.

This project is **not affiliated with, endorsed by, or certified against ASD-STE100 or ASD**. It does not claim conformance with the specification.

## License

[MIT](LICENSE)
