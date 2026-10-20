# Loud Kettle — notes for AI coding agents

One HTML file: markup, inline CSS and inline scripts; GSAP with ScrollTrigger and SplitText, Lenis smooth scroll, all from jsDelivr. No build step, no framework.

## Files
Work from the files: a page read through a link comes back as a summary, and a page rebuilt from it would differ.
```bash
curl -LO https://raw.githubusercontent.com/8bsite/brewery-website-template/main/index.html
curl -LO https://raw.githubusercontent.com/8bsite/brewery-website-template/main/AGENTS.md
curl -LO https://raw.githubusercontent.com/8bsite/brewery-website-template/main/LICENSE
curl -LO https://raw.githubusercontent.com/8bsite/brewery-website-template/main/CREDITS.md
```
In Windows PowerShell type `curl.exe`. Publish `index.html` with LICENSE and CREDITS.md; this file, README.md and `previews/` are not part of the site.

## Do not break
- Keep it one file unless the user asks otherwise; no framework or bundler for copy, colour or photo changes.
- Keep the ids and the `data-8b-section` / `data-8b-motion` attributes. Each section has its styles in `<style data-8b-part="section:<id>">` and its animation, if any, in `<script data-8b-part="scene:<id>">`.
- The scripts find these classes and attributes; when you change a section's markup, keep them or update the script:
  - `section-script:nav`: `.nav__menu` `.menu__close`
  - `section-script:opening`: `.op__screen--1`
  - `scene:opening`: `.op__backdrop` `.op__disc` `.op__orbit` `.op__title` `.op__base` `.op__pint` `.op__chip`
  - `section-script:flights`: `.fl__slots` `.fl__slot` `.fl__chip` `.fl__summary` `.fl__count` `.fl__save` `.fl__status` `.fl__name` `data-label-filled` `data-label-empty` `data-template` `data-empty` `data-full` `data-saved`
  - `section-script:visit`: `.vi__form` `.vi__status` `data-invalid` `data-sent`
  - `section-script:footer`: `.ft__club` `.ft__status` `data-invalid` `data-sent`
  - `scene:tags-swing`: `.ns__card` `.ns__float` `.ns__list`
  - `scene:pour-steps`: `.tap__big` `.tap__card` `.tap__stairs` `.tap__fill`
  - `scene:wheel`: `.bd__rim` `.bd__station`
  - `scene:wave`: `.oh__title` `.oh__row` `.oh__track`
  - `scene:deal`: `.ev__list` `.ev__row`
- Colours, fonts, radii and shadows are CSS variables in the `:root` block (`data-8b-part="tokens"`); change them there and keep body text at 4.5:1 contrast or more.
- Animations run only when the visitor allows motion (`prefers-reduced-motion: no-preference`); the page must stay readable without them.
- A display line with `style="--len:N"` is sized to fill its width: N is its number of characters, spaces included (`pouring` → 7, `Overheard` → 9).
- Keep the header comment and `<meta name="generator">`. Keep the "Design: 8B" footer link unless the site owner asks to remove it.

## Replace before publishing
- Everything marked `data-8b-placeholder` (og-image, favicon, map, phone, email, form, social); remove the attribute once the real value is in. With no real value: no preview image — delete the `og:image` tag and set `twitter:card` to `summary`; no phone, email or address — remove that link or row.
- Book a table buttons in the nav and the phone menu: link to #visit now; point them to your reservation or booking URL (or keep #visit if the form below is your booking).
- Directions link in visit: link to a Google Maps search for the invented address now; point them to the Google Maps link of your real address.
- Instagram and Facebook icons in the footer: link to the networks' home pages now; point them to your own profile URLs.
- **The forms send nothing.** `section-script:visit` and `section-script:footer` check the fields and show a thank-you message without sending. Pick one:
  - Formspree: set `action="https://formspree.io/f/<id>"` on the form; in the script, before the thank-you message, `await fetch(form.action, { method: 'POST', body: new FormData(form), headers: { Accept: 'application/json' } })` and show it only if the response is ok.
  - Netlify Forms (site on Netlify): add `name="contact" data-netlify="true"` and `<input type="hidden" name="form-name" value="contact">`; send with `fetch('/', { method: 'POST', headers: { 'Content-Type': 'application/x-www-form-urlencoded' }, body: new URLSearchParams(new FormData(form)) })`.
  - No form service: remove the `<form>` together with the script that handles it (it would fail without the form) and keep the email link.
- Invented demo facts (ask the user for the real ones; do not make up prices, dates or addresses):
  - Name, place and founding year: "Loud Kettle Brewing Co. · Strip District, Pittsburgh · since 2019" (opening sign-off line), Pittsburgh in the page title and meta description.
  - Address: "The Old Tram Shed, 412 Foundry Lane, Pittsburgh, PA 15222" (visit, the Directions link's map search) and "© 2026 Loud Kettle Brewing Co. · 412 Foundry Lane, Pittsburgh" (footer). Invented.
  - Phone and email, already replaced with placeholders: (412) 000-0000 and hello@loudkettle.example (visit).
  - Opening hours: Mon–Thu 3–11 pm, Friday 3 pm–1 am, Saturday 12 pm–1 am, Sunday 12–9 pm (visit); "Open seven days", "from 3 pm on weekdays and noon at weekends" (taproom).
  - The beers, styles and strengths: Porch Crusher pale ale 5.2%, Static Haze hazy IPA 6.8%, Red Siren Irish red 5.6%, Peach Feedback peach sour 4.9%, Night Shift oatmeal stout 7.4% (on-tap, flights, and Static Haze also in the opening label "Now pouring · Tap 04"), Tram Shed Lager helles 4.6% (flights only).
  - Prices: pints $7 and $8, halves $4 and $5 (on-tap); a flight of four five-ounce pours for $14 (flights); event prices Free, $10 and $18 (events).
  - Brewery size and process: "seven barrels at a time", "forty feet from the tank" (opening, brew-day), grain milled at six in the morning, "four hundred pounds of grain", a ninety-minute boil with three hop additions, two weeks of fermentation, lagers six weeks near freezing, hazy beers three days, hops used inside the month, "two hundred pounds of Georgia peaches per batch", stout poured on nitro, "nothing is bottled" (no-shortcuts, on-tap, brew-day).
  - Local claims: spent grain goes to a pig farm up the Allegheny (no-shortcuts); tanks named after retired tram drivers (brew-day); ciders from an orchard in Butler County (faq).
  - The venue: an old tram shed, forty feet of bar, sixteen taps, tables from the depot's floorboards (opening, taproom); the back room seats forty, the whole place a hundred and sixty (faq, the visit form's guests options 10–20 / 20–40 / the whole shed).
  - House rules and services: dogs welcome inside and on the patio, kids until 8 pm with an adult, house root beer, a food truck every night (tacos Tuesday to Thursday, smash burgers Friday to Sunday), bring your own food, 32 oz crowlers and growler fills, a gluten-reduced pale and two dry ciders (taproom, faq).
  - Response promises: "we'll call you within a day" (faq, the visit form's data-sent message); the newsletter "one email a month", "the odd free pint", "the first email lands on the next release day" (footer).
  - Testimonials: six invented people quoted with first names and details — Dana, Marcus, Priya, Joe ("retired tram driver", "drove the 47 out of this shed for thirty years"), Lena ("quiz champion"), Sam ("bartender"), and "printed here with permission and a free pint" (overheard).
  - Events: five dated events, Thu 15, Sat 17, Fri 23, Sun 25 and Sat 31 October, with times 7 pm, 12 pm, 8 pm, 11 am, 7 pm; a band name "The Allegheny Rattlers"; promises such as "the winners drink free", "four-packs until they're gone, one per person", "a flight is included", a costume prize (events).
  - Copyright year 2026 and the company name in the footer.
- `<title>`, the meta description and the og tags; photos (Unsplash, see CREDITS.md) when the user has their own.

## Notes
- The outlined display words (the first headline line, POURING, OVERHEARD, the footer wordmark) fill their letters with the page's dark ground to hide overlapping contours: keep them on the dark ground, or change the fill colour together with the background.
- Each beer's colour comes from a CSS variable (--color-4 … --color-7 and --color-3), and each flight swatch takes a colour variable too, not always the same one as the beer's card: after a recolour, check that each card and its swatch still match.
- The booking form, the flight picker and the newsletter form only show a message on the page; nothing is sent until you connect them.
- Without JavaScript or with reduced motion, the brew-day wheel is a plain row of steps and the tap list a static staircase: complete, but without the wheel.
- There is no age check or responsible-drinking notice; add one if your local rules require it.
- The copy mixes "nothing is bottled" (brew-day) with cans, crowlers and growlers (events, faq): align it with how you really sell.

## Common edits
- Rebrand: search the old name (`Loud Kettle`) in any letter case and replace every match; change the favicon letter and colours in `<link rel="icon">`.
- Photos: replace `src` and delete `srcset` and `sizes` (they list Unsplash sizes), keep `width`/`height` to the new photo's ratio, update `alt` and CREDITS.md.
- Remove a section: delete its markup, its `section:<id>` and `scene-style:<id>` styles, its `scene:<id>` and `section-script:<id>` scripts, and links to `#<id>`.
- Native scroll instead of smooth scroll: delete the Lenis block in `page-init` and the Lenis `<script>` tag.

## Check and publish
- Open the page at 375 and 1440 px, with reduced motion on, with the console open.
- Search `data-8b-placeholder` and the old name: nothing should be left but class names.
