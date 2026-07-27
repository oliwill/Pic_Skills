---
name: baozi-watercolor-elements
description: Generate or restyle characters, objects, mascots, decorative illustrations, hero art, cards, backgrounds, and other baozi.space website assets in a consistent Japanese hand-painted watercolor style. Use when creating a new watercolor image, transforming a supplied photo or sketch, extending an existing series, or revising an image while preserving its subject identity and established visual language.
---

# Baozi Watercolor Elements

Create image-generation prompts and, when an image-generation tool is available, generate the requested asset. Keep the series recognizable as one physical watercolor world rather than a collection of unrelated “watercolor-like” filters.

## Workflow

1. Identify the asset type: character, object, scene, or image restyle.
2. Record all invariants from the request and references: identity, pose, viewpoint, clothing, object count, anatomy, crop, and required empty space.
3. Choose an output mode and aspect ratio before composing.
4. Assemble the prompt from the fixed anchors, the relevant template, and concrete subject details.
5. Add negative constraints and explicit count/anatomy constraints.
6. Generate directly when the user asks for an image. Do not stop at a prompt unless the user requests prompt text only.
7. Inspect the result against the checklist. On revision, change only the requested variables.

If reference images are supplied, inspect every target image before generation. Never invent unseen identity details when they materially affect likeness; infer only viewpoint-dependent structure such as a rear silhouette from the available front and side references.

## Fixed Style Anchors

Include all five anchors in every generation:

1. Rough cold-pressed watercolor paper with visible tooth.
2. Opaque watercolor or gouache-like layering mixed with translucent washes.
3. A restrained cool palette led by indigo, muted teal, dusty blue, blue-gray, and pale periwinkle.
4. Layered, intimate composition with gentle overlap and decorative rhythm.
5. Quiet, tender, dreamlike, introspective emotion with handmade imperfection.

Describe the work as an original physical painting. Preserve dry-brush marks, uneven pigment deposits, soft blooms, faint watermarks, granulation, slightly imperfect contours, and occasional colored-pencil lines. Avoid a generic digital “watercolor filter.”

## Subject Fidelity

Treat user-specified traits as hard constraints.

- Preserve recognizable facial structure, hairstyle, body proportions, pose, viewpoint, clothing silhouette, accessories, and signature colors.
- Simplify a person into a gentle animation-inspired form without replacing them with a generic anime face.
- Preserve a mascot's defining geometry. For a baozi character, keep the pleated steamed-bun crown and soft dough volume; do not turn it into a round blob, dumpling, or human head.
- Preserve exact object and body-part counts. Show five fingers on a visible human-like hand unless occlusion is clearly intentional.
- Preserve the requested relative scale. If revising “make the baozi smaller,” reduce only the baozi and maintain pose, hand anatomy, framing, lighting, palette, and background.
- For a rear view inferred from front and side photos, use the references for height, build, hair mass, clothing fit, backpack, and color; do not fabricate facial details that are not visible.
- Keep key identity features readable even when foreground plants overlap the body.

## Composition

Use one of these composition modes:

- **Isolated website element:** one clear silhouette, generous safe margin, minimal or no cast shadow, no unintended crop, and controlled decoration. Keep the subject legible at small UI sizes.
- **Character vignette:** half-body or three-quarter-body framing, central or slightly offset subject, layered foliage or small motifs, and limited foreground overlap.
- **Editorial scene or hero:** vertical or wide intimate framing, foreground/midground/background layers, one dominant focal point, and intentional negative space for interface copy when requested.
- **Dense garden:** let flowers, rounded leaves, and slender stems fill most of the frame. Use uneven height and overlap; avoid mirrored or mechanically repeated arrangements.

Create depth through overlapping flat shapes, value changes, temperature shifts, and pigment density. Do not rely on photorealistic perspective, depth of field, or dramatic cinematic light.

## Material and Paper

Use rough, cold-pressed, warm-white watercolor paper. Make its grain visible in light areas and through thinner washes. Combine:

- broad organic shapes;
- opaque gouache-like accents;
- translucent watercolor washes;
- restrained dry-brush edges;
- faint colored-pencil contours;
- natural water blooms and pigment pooling.

Keep edges handmade but intentional. Avoid uniform noise overlays, muddy overworking, smooth airbrush gradients, plastic shine, and excessively crisp vector contours.

For transparent web assets, request a transparent background while keeping pigment granulation and paper-fiber texture within the painted subject. Do not add a rectangular white paper tile unless requested.

## Limited Palette

Use this default family:

- deep indigo `#172A46` and midnight blue `#223553` for deepest shapes;
- muted teal `#4F7778` and blue-green `#648A86` for secondary forms;
- dusty blue `#7894A8` and blue-gray `#9AABB6` for middle values;
- pale periwinkle `#B9C7DF` and warm paper `#F3EBDD` for light areas;
- cobalt blue `#315DA8` as a sparing focal accent;
- warm brown `#76594B`, soft peach `#D8AD94`, and muted yellow `#D2B85C` as controlled counterpoints.

Allow small semantic deviations for identity-critical colors, such as a yellow hoodie or natural skin and hair. Mute them into the same pigment world; do not recolor them blue merely to obey the palette. Avoid neon colors, pure black shadows, and broad areas of maximum saturation.

## Prompt Templates

Write final generation prompts in natural, concrete English unless the active model performs better in another language. Replace every bracketed field; never send placeholders to the generator.

### Character

```text
A poetic hand-painted watercolor character illustration of [identity and action], shown from [viewpoint and crop]. Preserve [identity, hairstyle, build, clothing, accessories, pose, anatomy, and exact counts]. Use a gentle simplified animation-inspired design without genericizing the subject. Compose the figure [placement and overlap], with [supporting motifs] forming an intimate layered rhythm. Paint on rough warm-white cold-pressed watercolor paper using opaque watercolor and gouache-like layers, translucent washes, dry-brush texture, pigment blooms, granulation, and faint colored-pencil contours. Use the baozi.space limited palette of deep indigo, muted teal, dusty blue, blue-gray, pale periwinkle, and controlled identity-critical warm accents. Soft diffuse illumination; quiet, tender, dreamlike, introspective mood. Original physical painting, handmade edges, no polished digital finish. [output mode, aspect ratio, safe area].
```

### Object or Mascot

```text
A small hand-painted watercolor website asset depicting [object or mascot] [action]. Preserve its defining silhouette: [shape constraints, parts, count, scale, and expression]. Keep it readable at small size with a clear outer contour, restrained internal detail, and [transparent / warm paper] background. Use rough cold-pressed watercolor texture, opaque pigment layered with translucent washes, dry-brush edges, subtle granulation, and slight handmade irregularity. Apply deep indigo, muted teal, dusty blue, pale periwinkle, and only the necessary warm accents. Gentle diffused light, charming but restrained, poetic rather than glossy or commercial. [dimensions and padding].
```

### Scene

```text
A poetic Japanese hand-painted watercolor scene of [subject and event] in [setting], composed as [vertical / wide / square] artwork for [website use]. Arrange [foreground], [midground], and [background] with layered flat shapes and gentle overlap. Keep [focal subject] at [relative size and position] and reserve [negative-space location] for interface content. Render on rough cold-pressed watercolor paper with opaque gouache-like layering, translucent washes, visible grain, blooms, pigment pooling, dry-brush marks, and softly imperfect contours. Use a limited cool palette of indigo, muted teal, dusty blue, blue-gray, and periwinkle with [controlled warm accent]. Soft diffuse illumination, quiet dreamlike emotion, no photorealistic depth or cinematic effects. [output specifications].
```

### Image Restyle

```text
Transform the provided image into a poetic, traditionally hand-painted Japanese watercolor illustration. Preserve the subject's recognizable [identity features], exact pose, viewpoint, proportions, clothing silhouette, accessories, object count, and important personal characteristics. Simplify the forms gently without replacing the subject with a generic anime design. Recompose only [requested background or overlap changes]. Render on rough cold-pressed watercolor paper using opaque watercolor, gouache-like layering, translucent washes, dry-brush texture, granulation, natural watermarks, and subtle colored-pencil contours. Use the baozi.space limited cool palette while retaining natural skin, hair, and identity-critical clothing colors. Soft diffuse illumination, quiet and intimate mood, original physical painting rather than a digital filter. [output specifications].
```

## Negative Constraints

Append a concise subset relevant to the request:

```text
photorealistic, photography, 3D render, glossy digital painting, smooth airbrush shading, plastic skin, generic anime face, polished commercial anime key visual, sharp vector outlines, perfectly clean edges, uniform noise texture, neon colors, excessive saturation, pure black shadows, cinematic rim light, dramatic hard shadows, lens effects, depth of field, bokeh, symmetrical repeated flowers, hyper-detailed botanical realism, malformed anatomy, missing fingers, extra fingers, fused fingers, extra limbs, incorrect object count, unintended crop, text, logo, watermark
```

Do not use a negative term that contradicts the desired asset. For example, omit “text” when the requested object intentionally contains lettering.

## Iteration Rules

When revising an existing generation:

1. Restate the requested deltas as a short change list.
2. Lock all non-requested properties explicitly.
3. Use relative and absolute constraints together where useful: “reduce the baozi to about 70% of its current height while keeping its center position.”
4. Correct anatomy and counts explicitly: “one raised hand with five clearly separated fingers.”
5. Do not silently redesign the face, pose, crop, background, color balance, or clothing.
6. If two requested changes conflict, prioritize identity and anatomy, then composition, then decorative detail.
7. Inspect the new result for regression before returning it.

Use this edit clause:

```text
Modify only the following: [delta list]. Keep unchanged: [identity, pose, viewpoint, clothing, palette, texture, lighting, composition, background, crop, and all other approved details].
```

## Output Specifications

Choose specifications from actual placement:

- UI icon or small mascot: square 1024×1024 master, transparent background, 12–18% safe padding.
- Card or inline illustration: 4:3 or 3:2, at least 1600 px on the long edge.
- Portrait editorial art: 4:5 or 3:4, at least 2048 px on the long edge.
- Hero banner: match the implemented container; default to 16:9 or 3:2 with 30–45% intentional copy-safe space.
- Full-bleed paper artwork: warm paper background with grain reaching every edge.
- Cutout asset: transparent background, no rectangular paper patch, no accidental halo, complete silhouette.

Request PNG for transparency or lossless masters. Request WebP/AVIF derivatives only during website integration, not as the sole master. Avoid embedding text in generated artwork; render live HTML text for accessibility unless lettering is itself the illustrated subject.

## Quality Checklist

Before returning a prompt or image, verify:

- all five style anchors are present;
- subject identity and signature geometry remain recognizable;
- pose, viewpoint, clothing, accessories, scale, anatomy, and counts match;
- visible hands have correct fingers;
- paper grain belongs to the painting rather than looking like a digital overlay;
- palette stays restrained while identity-critical colors survive;
- composition fits the target UI placement and safe area;
- no text, watermark, crop, extra object, or glossy digital artifact appears;
- revision requests changed only the named variables.

## baozi.space Invocation Examples

### Small navigation mascot

```text
Use $baozi-watercolor-elements to generate a transparent 1024×1024 watercolor navigation mascot: a small steamed bun with a clearly pleated crown, wearing a muted yellow hoodie and reaching upward with one five-fingered hand. Keep 16% padding and make it readable at 48 px.
```

### Fireworks hero

```text
Use $baozi-watercolor-elements to create a wide baozi.space hero scene of a small baozi character reaching toward soft blue-gold fireworks. Keep the baozi to roughly 18% of the canvas height, preserve five fingers, and reserve the left 40% as quiet copy space.
```

### Personal rear-view illustration

```text
Use $baozi-watercolor-elements with the supplied front and side photos to paint a rear-view character in a yellow hoodie and backpack. Infer only the rear silhouette; preserve build, hair mass, clothing fit, backpack shape, and the established cool watercolor palette.
```

### Existing asset revision

```text
Use $baozi-watercolor-elements to edit the supplied image. Make only the baozi about 25% smaller and correct the raised hand to five distinct fingers. Keep every other approved detail unchanged.
```
