# Lugano editorial system

The homepage keeps the approved ivory engraving as its visual source of truth. Starting with the verification ledger, the rest of the homepage moves into a midnight technical environment: quiet, inspectable, and deliberately more focused than the panorama above it. The hero artwork and headline remain unchanged; the location caption is omitted. The verification heading is centered above a compact, 52rem ledger with all ten checks.

## Tokens

| Purpose | Value |
| --- | --- |
| Hero ivory | `#fcf2df` |
| Midnight | `#091625` |
| Raised midnight | `#0d1e34` |
| Elevated card | `#13283f` |
| Primary type | `#fcf2df` |
| Body type | `#b6c5d7` |
| Soft blue accent | `#91b8ed` |

Use Instrument Serif for high-level claims and IBM Plex Sans for body copy. JetBrains Mono is reserved for labels, numbers, metadata, and proof-like details.

## Surface rhythm

- The verification ledger begins the dark continuation directly after the ivory hero.
- Homepage and application chapters alternate midnight and raised-midnight surfaces so the reading path stays clear across the full page.
- Cards use `#13283f`, thin soft-blue rules, and modest elevation. Do not reintroduce glass effects, neon glows, broad gradient fills, or oversized rounded cards.
- Use-case engravings remain unfiltered ivory media panels inside their dark cards.
- Scrambled-character canvas effects remain visible on card hover and keyboard focus, with the existing reduced-motion behavior.
- Maintain 16px or larger body copy, generous chapter spacing, and clear keyboard focus outlines.

## Artwork

- Hero engraving: `/assets/lugano-engraving-v1.webp`, with `/assets/lugano-engraving-v1-mobile.webp` for the narrow crop.
- Use-case engravings: `/assets/lugano-enterprise-engraving.webp`, `/assets/lugano-sovereign-engraving.webp`, and `/assets/lugano-regulated-engraving.webp`.
- Keep these assets unfiltered. Their cobalt, ivory, and engraving detail are the intended palette; only the small card-image hover scale is retained.
- The hero panorama is static; its water animation, pointer parallax, and animation control have been removed.

All four illustrations were created with the built-in image-generation tool. The native outputs are 1672 × 941. The hero keeps that resolution; the mobile variant and 1000px use-case assets are optimized WebP derivatives.

| Illustration | Site asset | Exact generation prompt |
| --- | --- | --- |
| Lugano panorama | [Hero](../../assets/lugano-engraving-v1.webp) | [Prompt](imagegen-prompt.txt) |
| Enterprise | [Engraving](../../assets/lugano-enterprise-engraving.webp) | [Prompt](lugano-enterprise-prompt.txt) |
| Government and defense | [Engraving](../../assets/lugano-sovereign-engraving.webp) | [Prompt](lugano-sovereign-prompt.txt) |
| Regulated industries | [Engraving](../../assets/lugano-regulated-engraving.webp) | [Prompt](lugano-regulated-prompt.txt) |

## Implementation map

`lugano-design-system.css` is loaded after `homepage-sections.css`. It leaves `.lgx-hero-editorial` hero-owned and uses `#lugano-proof-ledger` as the first dark continuation surface.

It uses semantic IDs/classes instead of section position: `#privacy`, `#architecture`, `#platform`, `#cta`, `#use-cases`, `#private-agents`, and `#private-models`. The shared ivory `#root nav` rules cover both the homepage and the hash-routed application view, including its mobile menu. The homepage/application footer closes in midnight; `logo-mark.svg` itself is a solid cobalt three-block mark on a 10% cobalt square.

The same stylesheet is linked after the existing styles in `/docs/`, `/privacy/`, `/terms/`, and `/security/`; this dark continuation is scoped to the homepage/application surfaces and does not retheme those document and policy bodies.

`/deck/` is an immediate DocSend redirect and has no local presentation shell to theme.
