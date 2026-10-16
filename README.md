# Free HTML brewery website template with GSAP scroll animations — Loud Kettle

**Website for a craft brewery and taproom: beers on tap, events and table booking: a free HTML template in one file, with GSAP scroll animations, no build step, MIT license. Made by [8B](https://8b.com/), the AI website builder.**

[![License: MIT](https://img.shields.io/badge/license-MIT-blue)](LICENSE) ![one HTML file: no build](https://img.shields.io/badge/one%20HTML%20file-no%20build-orange) ![GSAP: ScrollTrigger](https://img.shields.io/badge/GSAP-ScrollTrigger-88ce02)

**[Live demo](https://8bsite.github.io/brewery-website-template/)** · **[Use this template](https://github.com/new?template_name=brewery-website-template&template_owner=8bsite)** · **[Download ZIP](https://github.com/8bsite/brewery-website-template/archive/refs/heads/main.zip)**

<a href="https://8bsite.github.io/brewery-website-template/"><img src="previews/desktop.png" alt="Loud Kettle, a free HTML template: first screen on a desktop" width="76.1%"></a> <a href="https://8bsite.github.io/brewery-website-template/"><img src="previews/phone.png" alt="Loud Kettle, a free HTML template: first screen on a phone" width="21.9%"></a>

<p align="center"><a href="https://8bsite.github.io/brewery-website-template/"><img src="previews/scroll.gif" alt="Loud Kettle, a free HTML template: scrolling through the first sections on a desktop" width="40%"></a><br><sub>Scroll animation</sub></p>

A one-page site for a small craft brewery with a taproom in an old tram shed: the tap list, a flight builder, brew day, events and a booking form. Near-black ground, cream tags and loud condensed capitals; an amber disc behind the hero pint floods the second screen, the beer cards fill with colour like glasses as they step down, and the brew-day steps turn on a wheel as you scroll.

Good for: craft brewery or brewpub; taproom, beer bar or cider house; distillery, winery or coffee roaster with a tasting room; any small venue with a menu of products, events and bookings.

## Use it with an AI coding agent

Download the files into your project (in Windows PowerShell type `curl.exe`):

```bash
curl -LO https://raw.githubusercontent.com/8bsite/brewery-website-template/main/index.html
curl -LO https://raw.githubusercontent.com/8bsite/brewery-website-template/main/AGENTS.md
curl -LO https://raw.githubusercontent.com/8bsite/brewery-website-template/main/LICENSE
curl -LO https://raw.githubusercontent.com/8bsite/brewery-website-template/main/CREDITS.md
```

Then give your agent this prompt:

```text
Read AGENTS.md, then edit index.html. Use this template as the base for a site for <your brewery, taproom or bar: name, city, what's on tap with styles and prices, opening hours, address, events, how to book>. Keep the layout, the motion and the single-file format; replace the brand name, copy, beers, prices, hours, events, quotes, photos, links and contacts, and recolour it through the CSS variables if needed.
```

Give the agent the downloaded file, not a link: from a link it would rebuild a different page. No agent? Click **[Use this template](https://github.com/new?template_name=brewery-website-template&template_owner=8bsite)**, edit `index.html` and turn on **Settings → Pages**.

## What's on the page

- **Navigation** — top bar: two-line wordmark, section links, Book a table button; phone menu overlay
- **The kettle's loud. The beer's louder.** — two-screen hero: headline, product photo on a brand-colour disc with three orbiting photos, then a manifesto sentence on the brand colour (demo: a pint and ingredients)
- **Four things that never go in the kettle** — column of four hanging tag-cards (principles or features) among floating round photos
- **What's pouring** — giant outlined word over five product cards in a staircase, each in its own colour (demo: the beers on tap)
- **Build a flight of four. $14** — interactive picker: choose four items into round slots, then save (demo: a beer flight)
- **From grain to glass** — five numbered process steps that turn on a big wheel as you scroll (demo: brew day from grain to glass)
- **The tram shed** — the venue: heading, lead, one wide and two small photos, three fact cards (demo: hours, dogs, food truck)
- **Overheard** — testimonials: giant outlined word and a slow scrolling row of six quotes on tag-cards
- **Ask the bar** — questions and answers (native &lt;details&gt;), sticky heading on desktop
- **Loud nights** — list of dated events as ticket rows: date stub, title, text, price and time
- **Come thirsty** — contact: photo of the venue, address, hours, phone and email cards, and a booking request form (placeholders)
- **Footer** — width-filling outlined wordmark, links, newsletter signup, social icons, copyright and the Design: 8B credit

## Design

Palette: ![#120c07](https://img.shields.io/badge/-%23120c07-120c07?style=flat-square) ![#f5e4c7](https://img.shields.io/badge/-%23f5e4c7-f5e4c7?style=flat-square) ![#2a221a](https://img.shields.io/badge/-%232a221a-2a221a?style=flat-square) ![#e3a43c](https://img.shields.io/badge/-%23e3a43c-e3a43c?style=flat-square) ![#f15a26](https://img.shields.io/badge/-%23f15a26-f15a26?style=flat-square) ![#c21d24](https://img.shields.io/badge/-%23c21d24-c21d24?style=flat-square) ![#f19656](https://img.shields.io/badge/-%23f19656-f19656?style=flat-square) ![#b4a387](https://img.shields.io/badge/-%23b4a387-b4a387?style=flat-square)  
Fonts: Bricolage Grotesque, Onest (Google Fonts). Change both through the CSS variables in the `:root` block at the top of `<head>`. A big display line with `style="--len:N"` fills its width: set N to its new number of characters.

- The outlined display words (the first headline line, POURING, OVERHEARD, the footer wordmark) fill their letters with the page's dark ground to hide overlapping contours: keep them on the dark ground, or change the fill colour together with the background.
- Each beer's colour comes from a CSS variable (--color-4 … --color-7 and --color-3): the same variables colour the on-tap cards and the flight swatches, so a recolour stays consistent.

## Before you publish

- Replace everything marked `data-8b-placeholder` (social preview image, favicon, map, phone, email, form, social) and the invented demo facts: prices, dates, address. [AGENTS.md](AGENTS.md) lists them.
- The form sends nothing yet: connect it to Formspree or Netlify Forms, or remove it.

## Tech

GSAP 3.13.0, ScrollTrigger, SplitText, Lenis 1.3.27 from jsDelivr, 96 KB, no build step. Chrome and Edge 111+, Safari 16.2+, Firefox 113+ (it uses color-mix(), cascade layers, small/dynamic viewport units). With "reduce motion" on, the page is complete and still.

## License

MIT, see [LICENSE](LICENSE); the "Design: 8B" footer link is welcome, not required. Photos, fonts and libraries keep their own licences: [CREDITS.md](CREDITS.md). More free templates: [github.com/8bsite](https://github.com/8bsite).
