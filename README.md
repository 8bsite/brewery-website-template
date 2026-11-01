# Free HTML brewery website template with scroll animations and no libraries

Brewery website template: a free one-page site for a craft brewery or taproom, with a five-beer tap list, a four-slot flight builder, a brew day on a turning wheel, dated events and a booking request form. The look is cream tags and condensed capitals on near-black, one colour per beer. Its scroll motion runs on CSS with no JavaScript libraries, in one HTML file with an AGENTS.md for Claude Code, Cursor or Codex.

[![License: MIT](https://img.shields.io/badge/license-MIT-blue)](LICENSE) ![one HTML file: no build](https://img.shields.io/badge/one%20HTML%20file-no%20build-orange) ![dependencies: none](https://img.shields.io/badge/dependencies-none-brightgreen)

**[Live demo](https://8bsite.github.io/brewery-website-template/)** · **[Use this template](https://github.com/new?template_name=brewery-website-template&template_owner=8bsite)** · **[Download ZIP](https://github.com/8bsite/brewery-website-template/archive/refs/heads/main.zip)** · **[Template page on 8b.com](https://8b.com/templates/loud-kettle/)**

<a href="https://8bsite.github.io/brewery-website-template/"><img src="previews/desktop.png" alt="Brewery website template: first screen on a desktop" width="76.1%"></a> <a href="https://8bsite.github.io/brewery-website-template/"><img src="previews/phone.png" alt="Brewery website template: first screen on a phone" width="21.9%"></a>

<p align="center"><a href="https://8bsite.github.io/brewery-website-template/"><img src="previews/scroll.gif" alt="Brewery website template: scrolling through the first sections" width="40%"></a><br><sub>Scroll animation</sub></p>

## Use it with Claude Code, Cursor or Codex

Download the four files into your project folder (`curl.exe` in Windows PowerShell):

```bash
curl -LO https://raw.githubusercontent.com/8bsite/brewery-website-template/main/index.html
curl -LO https://raw.githubusercontent.com/8bsite/brewery-website-template/main/AGENTS.md
curl -LO https://raw.githubusercontent.com/8bsite/brewery-website-template/main/LICENSE
curl -LO https://raw.githubusercontent.com/8bsite/brewery-website-template/main/CREDITS.md
```

Then fill in the angle brackets and give your agent this prompt:

```text
Read AGENTS.md, then edit index.html. Make it the site for <my brewery: name, city, address, beers with style, strength and prices, hours, dog, kids and food rules, dated events, how groups book>. Replace first the name, the five beers and their colours, the hours, which appear in two places, and the events. Set each big display word's length number to its new character count. Motion is CSS scroll-driven animation plus the inline motion kit: keep the gate script, the section ids, the data-8b-section and data-8b-motion attributes and five tap cards, steps and tickets; add no animation library. Never invent prices, hours, addresses, licences, reviews or contacts; ask me.
```

If you vibe code the site, this brewery website template for Claude Code, Cursor or Codex lets the agent start with the tap list: five beers, each with a style, a strength, pint and half prices and a colour. Name, city and address come next. The opening hours sit in two places, the taproom card and the hours list, and a beer name also appears in the hero label, the flight buttons, the events and the quotes, so search the whole file. Leave the section ids, the listed classes and the motion attributes alone. Ask the owner for dog, kids and food rules, capacity, event dates and how groups book. Never invent licences, prices or quotes.

No agent? Click **[Use this template](https://github.com/new?template_name=brewery-website-template&template_owner=8bsite)**, edit `index.html` on GitHub and turn on **Settings > Pages**.

## Sections and motion

- **Navigation**: top bar: two-line wordmark, section links, Book a table button; phone menu overlay.
- **The kettle's loud. The beer's louder.**: two-screen hero: headline, product photo on a brand-colour disc with three orbiting photos, then a manifesto sentence on the brand colour (demo: a pint and ingredients). On load the headline lines wipe up, the disc swells and three round photos start to orbit the pint on a loop; on scroll the amber disc floods the screen, the pint lifts away and photo chips pop into the text.
- **Four things that never go in the kettle**: column of four hanging tag-cards (principles or features) among floating round photos. Tied to scroll, the four tag-cards drop in turn and swing to rest while round photos float up at two speeds.
- **What's pouring**: giant outlined word over five product cards in a staircase, each in its own colour (demo: the beers on tap). On desktop the five cards step down the staircase as you scroll, each filling with colour like a poured glass.
- **Build a flight of four. $14**: interactive picker: choose four items into round slots, then save (demo: a beer flight). The heading rises line by line; a tapped beer goes into the next empty round slot, which fills with its colour from the bottom; tap a slot to clear it.
- **From grain to glass**: five numbered process steps that turn on a big wheel as you scroll (demo: brew day from grain to glass). Held on screen while you scroll, the five numbered steps sit on a huge dashed wheel that turns one step at a time as you scroll.
- **The tram shed**: the venue: heading, lead, one wide and two small photos, three fact cards (demo: hours, dogs, food truck). The title rises line by line, and the three fact cards swing down on an elastic hinge as they arrive.
- **Overheard**: testimonials: giant outlined word and a slow scrolling row of six quotes on tag-cards. The outlined word's letters ripple in a wave that flattens as it scrolls up; the quote cards below roll sideways, pausing on hover or keyboard focus.
- **Ask the bar**: questions and answers (native &lt;details&gt;), sticky heading on desktop. The heading rises line by line on arrival and stays beside the questions on desktop as you read.
- **Loud nights**: list of dated events as ticket rows: date stub, title, text, price and time. Tied to scroll, the ticket rows start stacked and tilted on the first one and deal out into a list.
- **Come thirsty**: contact: photo of the venue, address, hours, phone and email cards, and a booking request form (placeholders). The Come thirsty heading rises line by line and the three fact cards swing down on their hinges.
- **Footer**: width-filling outlined wordmark, links, newsletter signup, social icons, copyright and the Design: 8B credit.

## Design

![#120c07](https://img.shields.io/badge/-%23120c07-120c07?style=flat-square) near-black brown background  
![#f5e4c7](https://img.shields.io/badge/-%23f5e4c7-f5e4c7?style=flat-square) cream text, tags, buttons, date stubs  
![#2a221a](https://img.shields.io/badge/-%232a221a-2a221a?style=flat-square) dark brown flight panel and stout card  
![#e3a43c](https://img.shields.io/badge/-%23e3a43c-e3a43c?style=flat-square) amber hero disc, IPA card, button hover  
![#f15a26](https://img.shields.io/badge/-%23f15a26-f15a26?style=flat-square) orange pale ale card  
![#c21d24](https://img.shields.io/badge/-%23c21d24-c21d24?style=flat-square) red ale card  
![#f19656](https://img.shields.io/badge/-%23f19656-f19656?style=flat-square) peach sour card  
![#b4a387](https://img.shields.io/badge/-%23b4a387-b4a387?style=flat-square) muted tan secondary text

**Bricolage Grotesque**: headings, tags, buttons: extra-bold, condensed, uppercase, some outlined. **Onest**: body and small tracked labels (Google Fonts). Cream tag labels with a punched hole at each end sit over hairline-bordered panels on a near-black ground. Photos are cut into circles and tall pills, giant outlined words fill the width, beer cards step down a staircase on wide screens, and events read as tickets.

## Questions

**Does the flight builder take orders or save anything?**  
No. Six beer buttons fill four round slots, and the Save button switches on once all four are full. Pressing it only writes a line on the page that lists the four beers for the guest to show at the bar; nothing is stored, sent or paid for. The six buttons are a separate list from the five tap cards, so edit both.

**Do the booking form and the newsletter signup send anything?**  
No. Both check their fields, show a thank-you or error line and send nothing. Connect Formspree or Netlify Forms, or remove the form together with its script and keep the email link. The thank-you line promises a call within a day, yet the booking form has no phone field, so add one or change the promise. Forms come up in [the pre-launch questions for vibe coders](https://8b.com/templates/vibe-coding/) too.

**Does this version need GSAP, Lenis or another library?**  
No. The scroll motion is CSS scroll-driven animations, and a short inline kit measures the page and smooths the mouse wheel. Nothing changes for the visitor, and the page downloads less than half the code: about 30 KB gzipped in one file against 77 KB. An agent keeps the gate script, the kit, the section ids, the data-8b-section and data-8b-motion attributes and the classes AGENTS.md lists.

## Is it the right base?

Choose this base when the brewery sells a place as much as a product: taps, house rules, dated nights out and groups booking a room. This is the light build: the same look and scroll behaviour with no animation library and no script from a CDN, about 30 KB of code gzipped in one file against 77 KB for the GSAP version. A kitchen-led venue should start from the [restaurant](https://8b.com/templates/ombrelle/) template. It stops at the click: no shop, cart, ticket checkout, table availability or age notice, and Book a table only scrolls to the visit section.

## Before you publish

- Replace what is marked `data-8b-placeholder` (social preview image, favicon, map, phone, email, form, social) and the invented demo facts; [AGENTS.md](AGENTS.md) lists them.
- The form sends nothing yet: connect it to Formspree or Netlify Forms, or remove it.

## Tech

No JavaScript libraries: CSS scroll-driven animations and a small inline motion script with its own smooth wheel scrolling, 115 KB, no build step. Chrome and Edge 111+, Safari 16.2+, Firefox 113+ (it uses color-mix(), cascade layers, small/dynamic viewport units). Without scroll-driven animations (Firefox today) the scroll motion and the smooth wheel are off and each section shows its finished layout, while any load-in or looping animation still plays; with "reduce motion" on, the page is complete and nothing moves on its own (hover effects stay).

A GSAP build of the same page is [`index.gsap.html`](index.gsap.html): GSAP 3.13.0, ScrollTrigger, SplitText, Lenis 1.3.27 from jsDelivr, 98 KB; its scroll motion also plays in Firefox. Use one of the two files.

## License

MIT, see [LICENSE](LICENSE). Photos, fonts and libraries keep their own licences: [CREDITS.md](CREDITS.md). More free templates: [8b.com/templates](https://8b.com/templates/) · [github.com/8bsite](https://github.com/8bsite).
