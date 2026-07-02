---
description: "A practical setup guide for GitBook-branded colors, logos, banners, and navigation tests."
icon: palette
---

# Branding and navigation

Use this site to test how branding changes affect readability and navigation. The current test pass applies GitBook corporate colors, landing-page banners, and logo treatment to both the Home space and the Orbitly Docs section.

<img src="../.gitbook/assets/gitbook-mark.svg" alt="GitBook" data-size="line">

{% hint style="info" %}
Keep brand elements functional: they should help users recognize the site, scan the page, and trust the content without making the docs feel like a marketing page.
{% endhint %}

## Applied GitBook palette

| Token | Hex | Usage |
| --- | --- | --- |
| Orange | `#F25B3A` | Primary accent, calls to action, highlight shapes |
| Dark base | `#1C1917` | Dark-mode logo treatment and high-contrast banner background |
| Grey 1 | `#262930` | Dark surfaces and code-adjacent contrast |
| Grey 2 | `#57534D` | Secondary text and neutral borders |
| Grey 3 | `#79716B` | Muted labels and dividers |
| Grey 4 | `#EFEEED` | Light surface backgrounds |
| Grey 5 | `#FAFAF9` | Main light background |

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
| Home | `.gitbook/assets/gitbook-home-banner.svg` | Introduces the sandbox with a lighter GitBook visual style. |
| Orbitly Docs | `.gitbook/assets/gitbook-orbitly-banner.svg` | Gives the imported product docs a stronger GitBook-branded first impression. |

## Navigation checks

Good navigation should make the next action obvious. Keep top-level sections broad and use pages for specific tasks.

<details>
<summary>Common navigation smell</summary>

If every page is nested under the homepage, the site is mirroring the file system instead of the reader's mental model. Promote important pages into clear groups.
</details>
