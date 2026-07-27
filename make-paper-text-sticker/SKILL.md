---
name: make-paper-text-sticker
description: Create warm off-white paper text stickers from exact Chinese or English copy, matching the bundled photographed reference style. Use when the user asks to turn one or more sentences into rounded rectangular paper stickers with black printed text, subtle paper grain, no speech-bubble tail, and transparent PNG output.
---

# Make Paper Text Sticker

Use the bundled image at `assets/style-reference.png` as the style reference.

## Required result

- Make one sticker per sentence unless the user requests another grouping.
- Preserve the supplied text verbatim, including punctuation and letter case.
- Use a horizontal rounded rectangle with four smooth rounded corners.
- Do not add a speech-bubble tail, pointer, notch, tab, or protrusion.
- Use warm off-white matte paper, faint paper grain, subtle handmade printing texture, and bold black text.
- Keep a faint grey-beige inset outline.
- Center the text and size the sticker naturally to its length.
- Output a transparent PNG with a very subtle natural paper shadow.
- Do not add icons, illustrations, decorations, watermarks, or extra text.

## Workflow

1. Read the user’s copy and repeat it internally character by character. Treat it as immutable.
2. Use the `imagegen` skill and built-in image editing/generation tool with `assets/style-reference.png` as the style reference.
3. Generate on a perfectly uniform `#ff00ff` chroma-key background. Do not use magenta in the sticker.
4. In the prompt, include:
   - `Text (verbatim, mandatory): "<exact user text>"`
   - an explicit character-by-character accuracy rule;
   - `simple elongated rounded rectangle, four rounded corners, no tail or pointer`;
   - the material and exclusion requirements above.
5. Inspect the generated text before accepting it. If any character or punctuation differs, regenerate with a targeted text-accuracy correction.
6. Convert the chroma-key background to alpha using the imagegen skill’s transparency workflow. Remove any magenta fringe and validate transparent corners.
7. Save the final PNG non-destructively in the current project. Use a filename derived from the copy.
8. For multiple sentences, generate separate assets and return a ZIP plus a contact sheet.

## Prompt template

```text
Use case: product-mockup
Asset type: single transparent-ready paper text sticker
Input image: assets/style-reference.png — style reference only
Primary request: create one standalone sticker matching the reference.
Text (verbatim, mandatory): "<USER_TEXT>"
Text accuracy: reproduce every character, punctuation mark, space, and letter case exactly. No substitutions, omissions, additions, translation, or other text.
Shape: a simple elongated horizontal rounded rectangle with four smooth rounded corners. No speech-bubble tail, pointer, notch, tab, or protrusion.
Style: warm off-white matte paper, faint paper grain, subtle handmade print texture, bold black text, faint grey-beige inset outline.
Composition: centered text, comfortable padding, sticker sized naturally to the text, fully visible and centered.
Backdrop: perfectly flat uniform #ff00ff chroma-key background with no texture or gradient.
Lighting: soft neutral light and an extremely subtle paper shadow.
Avoid: icons, illustrations, decorative elements, extra borders, glossy vinyl, watermark, and any additional text.
```
