---
description: "A practical setup guide for Orbitly-branded colors, logos, banners, and navigation tests."
icon: palette
---

# Branding and navigation

Use this site to test how branding changes affect readability and navigation. The current test pass applies Orbitly colors, landing-page banners, and logo treatment to both the Home space and the Orbitly Docs section.

<img src="../.gitbook/assets/orbitly-wordmark.svg" alt="Orbitly" data-size="line">

{% hint style="info" %}
Keep brand elements functional: they should help users recognize the site, scan the page, and trust the content without making the docs feel like a marketing page.
{% endhint %}

## Applied Orbitly palette

| Token | Hex | Usage |
| --- | --- | --- |
| Orbit blue | `#2563EB` | Primary accent, links, buttons, and product emphasis |
| Signal cyan | `#22D3EE` | Orbital lines, secondary highlights, and interactive accents |
| Launch amber | `#F59E0B` | Milestones, successful moments, and key badges |
| Orbit ink | `#111827` | High-contrast text and dark banner backgrounds |
| Cloud | `#F8FAFC` | Main light surfaces |
| Soft sky | `#E0F2FE` | Subtle branded backgrounds |

## Branding checks

| Area | What to test |
| --- | --- |
| Logo | Scales uniformly, stays legible, and has enough surrounding space. |
| Primary color | Links, buttons, and accents are easy to see. |
| Favicon | Recognizable in browser tabs and share previews. |
| Banners | Support the page message without hiding the title or nav. |
| Font | Comfortable for long-form reading. |
| Header links | Few enough to scan quickly. |

## Banner placement

| Space | Banner asset | Purpose |
| --- | --- | --- |
| Home | `.gitbook/assets/orbitly-home-banner.svg` | Introduces the sandbox with a light Orbitly visual style. |
| Orbitly Docs | `.gitbook/assets/orbitly-docs-banner.svg` | Gives the product docs a stronger Orbitly-branded first impression. |

## Navigation checks

Good navigation should make the next action obvious. Keep top-level sections broad and use pages for specific tasks.

<details>
<summary>Common navigation smell</summary>

If every page is nested under the homepage, the site is mirroring the file system instead of the reader's mental model. Promote important pages into clear groups.
</details>
