# Prose patterns

Evidence: [M] measured in a study · [W] Wikipedia AI-cleanup editors ·
[F] folk/practitioner, weaker. Weight hits accordingly.

## Vocabulary
- [M] delves (25x), showcasing (9x), underscores (9x); also potential,
  findings, crucial, additionally, comprehensive, enhancing, exhibited,
  insights, notably, particularly, pivotal, intricate, realm, meticulous
  (Kobak et al., 14M PubMed abstracts)
- [M] commendable (10x), meticulous (35x), intricate (11x), innovative,
  notable, versatile (Liang et al., ICLR reviews)
- [W] by model era. GPT-4: boasts, bolstered, delve, enduring, garner,
  interplay, landscape, tapestry, testament, valuable, vibrant. GPT-4o: align
  with, enhance, fostering, highlighting, showcasing. GPT-5: emphasizing,
  enhance, highlighting, showcasing. Grok: causal, empirical, correlate.
- [F] leverage, utilize, facilitate, embark, multifaceted, holistic, seamless,
  robust, elevate, unlock, unleash, harness, navigate (metaphor), game-changer

## Grammar and syntax
- [M] present participle tails ("…, highlighting its role") at 2-5x the human
  rate (Reinhart et al., PNAS 2025)
- [M] nominalizations ("the reduction of", "consumption patterns") at 1.5-2x
- [M] fewer hedges, questions, personal asides, and engagement markers:
  flat, impersonal, expository (Jiang & Hyland 2025). The fix is adding the
  author's stance, not adding "may potentially".
- [M] few typos, uniform sentence length (low burstiness)
- [W] copula avoidance: serves as, stands as, marks, represents, boasts,
  features, functions as
- [W]/[M] negative parallelism: "not just X, but Y", "it's not X, it's Y",
  "no X, no Y, just Z" (up to 6.3x, Antislop)
- [W] rule of three used reflexively
- [W] vague links: "in connection with", "associated with"

## Punctuation
- [M] em dashes: GPT-4.1 ~10.6, Claude ~8-9, Gemini ~3.5, Llama ~0 per 1k
  words vs about 3.2 for humans. A high rate is a tell for some models only.
- [W] curly quotes where the platform uses straight ones

## Content and framing [W]
- Inflated significance: stands as a testament, plays a pivotal/crucial role,
  underscores its importance, reflects broader trends, setting the stage,
  marks a shift, evolving landscape, indelible mark, enduring legacy
- Shallow -ing analysis: highlighting / ensuring / reflecting / fostering /
  contributing to / valuable insights / resonates with
- Promotional tone: vibrant, rich, nestled, in the heart of, renowned,
  groundbreaking, diverse array, commitment to
- Vague attribution: experts argue, industry reports, observers note
- Formulaic ending: "Despite its X, it faces challenges", "Future outlook"
- [F] openers: "In today's fast-paced world", "Have you ever wondered";
  closers: "In conclusion", "Ultimately", "The future is bright"
- [F] generic examples: "Sarah, a marketing manager", "Company X";
  invented statistics ("studies show 73%")

## Fiction [M] (Antislop, ICLR 2026)
- Names: Elara (85,000x), Kael, Lyra-type fantasy names
- Words: unsettlingly, shimmered, stammered, flickered, murmured, whispered
- Phrases: heart hammered against ribs, voice trembling slightly, voice
  devoid of emotion, felt a profound sense of, voice barely above a whisper,
  took a deep breath
- Structure: tidy single-track plots, explained themes, no moral ambiguity

## Formatting [W]
- Title Case Headings; headings that contain only headings
- Bold on every bullet lead-in ("**Clarity:** …")
- Bullets where the ideas need prose to connect them
- Emoji as bullets; tables where prose would do; horizontal rules everywhere
- Raw markdown (`**`, `##`) pasted into places that don't render it

## Residue [W] (delete on sight)
- Chat: "Certainly!", "I hope this helps", "Let me know if", "Great question"
- Cutoff: "as of my last update", "my knowledge"
- Placeholders: [Your Name], [insert …], [Company]
- Citation debris: oaicite, contentReference, turn0search0,
  attributableIndex, utm_source=chatgpt.com, [cite: 1], grok_card,
  ppl-ai-file-upload, 【】 brackets
- Fabricated citations: dead DOIs and ISBNs, book cites with no page numbers
