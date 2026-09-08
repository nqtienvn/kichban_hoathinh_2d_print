---
name: video-quang-cao-v3
description: "Use when the user wants Vietnamese batch prompts and matching storytelling narration for AI product ads in the approved V3 animated explainer style, with a chosen video duration, yellow character, zoom, magnified details, and changing layouts. Also use for requests to reuse the HARUCO V3 prompt style for another product."
---

# Video quảng cáo V3

Produce Vietnamese batch video prompts and matching conversational narration from a product image, its actual benefits, and a chosen finished duration. Prioritize an engaging, product-specific story that gives the viewer a reason to keep watching, alongside the user's approved V3 motion grammar. This skill prepares production material; text prompts alone are not rendered videos or recorded voice.

## Intake and references

Read [references/nhịp-v3.md](references/nhip-v3.md) and [the ten approved prompts](references/haruco-v3-approved.txt) before writing prompts. The HARUCO example supplies style, not facts about a new product.

Extract the exact product/model, visible design, benefits, and target duration T from the user's brief. Ask only for consequential missing input. If T is missing, offer 30/45/60/90 seconds or a custom duration; continue examining product materials while awaiting the choice. Use 60 seconds when the user asks you to choose. Do not silently interpret a scene count as seconds.

Default configuration, overridden by the user's explicit choices:
- Source clip length L = 6 seconds; aspect ratio 16:9.
- The batch tool already sets the background: prompt text contains **no background description**, including reminders to keep it unchanged.
- Yellow bald muscular character, outlined nose, no mouth, black 2D outlines, gray shorts/wristbands. Eyes may open, blink, squint, or close naturally according to the script and emotion; when open, they are solid white without pupils. Closed eyes use black eyelid lines. Preserve character identity while allowing these expressions. Reuse [assets/nhan-vat-v3.png](assets/nhan-vat-v3.png) if no replacement character is supplied; its open-eye pose is not a fixed animation constraint.
- Props and explanatory graphics are white; the product retains its actual colors, shape, attachments, and proportions.
- Narration is separate; video prompts request no generated speech or lettering. Preserve existing product branding; add readable overlays during editing.

Inspect available product images. Distinguish supplied benefits from verified evidence. Resolve mismatched model numbers before assigning a feature. For health claims, consult authoritative sources for the exact product and retain qualified wording; no invented cure, internal healing animation, heat, vibration, specifications, offer, testimonial, or seller commitment. Missing product imagery does not block a text draft; label appearance assumptions and request the image needed for a faithful visual reference.

## Build the batch

1. Set N = ceil(T/L). Allocate N edit durations d_i > 0, each <= L, whose sum is T. Start with T/N, then adjust for narration and beat complexity. See the duration reference for rounding and short-video handling.
2. Select one audience situation and one central product value grounded in the supplied facts. Privately draft three distinct opening angles, choose the strongest, and deliver one finished story without making the user choose drafts. Follow the storytelling guidance in the reference: immediate visual/spoken hook → small question or tension → timely reveal through a supported product detail/action → practical relevance → a natural next step that resolves or recalls the opening. Scale this arc to N; for a single short clip, compress it to one action and its resolution. Longer videos add distinct supported use situations, not repeated claims or a longer introduction.
3. Write conversational Vietnamese with concrete actions, varied sentence lengths, and meaningful pauses. Pair each short narration sentence with one visual idea. Each scene advances the story through new information, an action, or an answer; remove narration that merely lists features or repeats what the viewer already knows. Spoken nouns and verbs determine what moves and what is magnified. Refer to the concrete product part instead of generic 'show the benefit'.
4. Write each prompt as: **2D + L + ratio + compact identity lock → 2–3 timed physical/layout beats → brief integrity/audio constraint**. Aim for roughly 65–100 Vietnamese space-separated tokens, comparable to V3. Put the main payoff before the planned cut d_i, allowing a short moving tail. Camera movement accompanies visible joint/object action. Describe scaling/repositioning of layers, not anatomical or product morphing. Choose eye expressions to suit each beat; the archived examples' 'mắt trắng mở' wording does not require constantly open eyes in new prompts.
5. Define adjacent scene handoffs in the timing table. Each prompt must still establish its own opening state; separate batch generations do not share memory or guarantee continuity from 'continue previous scene'.

## Deliver and check

Save UTF-8 deliverables in the current workspace's user-output directory:
- `01_PROMPT_DAN_HANG_LOAT.txt`: exactly N paragraphs, one physical line each, separated by exactly one blank line. No numbering, headings, code fences, voice text, or setup notes inside this file.
- `02_LOI_DOC_LIEN_MACH.txt`: clean spoken text for ElevenLabs/Vbee, no stage directions.
- `03_KICH_BAN_VA_NHIP_DUNG.md`: per scene, timeline start/end, source length, planned trim, narration, timed action/zoom, story purpose (question, reveal, demonstration, or resolution), and next-scene handoff. Mark timings as estimates until checked against actual audio.
- `04_CACH_DUNG.md`: chosen T/L/N/ratio, image inputs, generation order, trimming, and material assumptions. Copy the character image alongside if useful.

If the user asks for prompts only, return the batch and a one-line duration note without extra artifacts. For requested image creation, use the available image-generation capability; inspect references first. Keep product recognition faithful and label unverified details. Do not generate new character art unnecessarily.

Check N, paragraph separators, sum of durations, payoff-before-cut, voice/image meaning, continuous articulated movement, and varied compositions. Also review the opening's specificity, each scene's new contribution, delivery of the promised reveal, natural read-aloud flow, and the ending's connection to the story; rewrite weak beats before delivery. Rewrite repetitive 'hold product + zoom' scenes. Treat engagement as a creative objective, not a guaranteed retention or sales result. If audio generation is available and requested, create and measure it before final cuts/subtitles; otherwise deliver the script and state audio is not generated. Do not reuse HARUCO's old voice timings or promise a 100% voice match.
