# AGENTS.md: brewery website template

Website for a craft brewery and taproom: beers on tap, events and table booking. One file, `index.html`, with inline CSS and scripts (GSAP, ScrollTrigger, Lenis from jsDelivr); no build step, and none is needed for copy, colour or photo edits.

## Files
Edit these files, not a page fetched by URL (that arrives as a summary).
```bash
curl -LO https://raw.githubusercontent.com/8bsite/brewery-website-template/main/index.html
curl -LO https://raw.githubusercontent.com/8bsite/brewery-website-template/main/AGENTS.md
curl -LO https://raw.githubusercontent.com/8bsite/brewery-website-template/main/LICENSE
curl -LO https://raw.githubusercontent.com/8bsite/brewery-website-template/main/CREDITS.md
```
Upload `index.html`, LICENSE and CREDITS.md; not this file, README.md or `previews/`.

## Keep
- Every `id`, `data-8b-section`, `data-8b-motion` and `data-8b-part` (`section:<id>` styles, `scene:<id>` animation).
- Selectors the scripts use:
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
- `style="--len:N"` = characters in that display line, spaces included: `pouring` is 7, `Overheard` is 9, `Loud Kettle` is 11.
- The outlined display words (the first headline line, POURING, OVERHEARD, the footer wordmark) fill their letters with the page's dark ground to hide overlapping contours: keep them on the dark ground, or change the fill colour together with the background.
- Each beer's colour comes from a CSS variable (--color-4 … --color-7 and --color-3), and each flight swatch takes a colour variable too, not always the same one as the beer's card: after a recolour, check that each card and its swatch still match.
- Colours and fonts are variables in `:root` (`data-8b-part="tokens"`): `--color-1` #120c07 (near-black brown background), `--color-2` #f5e4c7 (cream text, tags, buttons, date stubs), `--color-3` #2a221a (dark brown flight panel and stout card), `--color-4` #e3a43c (amber hero disc, IPA card, button hover), `--color-5` #f15a26 (orange pale ale card), `--color-6` #c21d24 (red ale card), `--color-7` #f19656 (peach sour card), `--color-8` #b4a387 (muted tan secondary text); body text needs 4.5:1 contrast.
- With reduced motion the page must read in full.
- Keep the header comment and `<meta name="generator">`. Keep the "Design: 8B" footer link unless the site owner asks to remove it.

## Replace
- `data-8b-placeholder` (og-image, favicon, map, phone, email, form, social): real value in, attribute out; no value, remove the row (no image: drop `og:image`, set `twitter:card` to `summary`).
- Book a table buttons in the nav and the phone menu: now #visit; owner's target: your reservation or booking URL (or keep #visit if the form below is your booking).
- Directions link in visit: now a Google Maps search for the invented address; owner's target: the Google Maps link of your real address.
- Instagram and Facebook icons in the footer: now the networks' home pages; owner's target: your own profile URLs.
- The form in `#visit` (fields `name`, `email`, `date`, `guests`, `notes`) sends nothing; `section-script:visit` validates it and shows the thank-you text. Formspree: `action="https://formspree.io/f/<id>"` and `fetch` POST `new FormData(form)` first. Netlify: `data-netlify="true"` and a hidden `form-name`. Or delete it and the script.
- The form in `#footer` (fields `email`) sends nothing; `section-script:footer` validates it and shows the thank-you text. Formspree: `action="https://formspree.io/f/<id>"` and `fetch` POST `new FormData(form)` first. Netlify: `data-netlify="true"` and a hidden `form-name`. Or delete it and the script.
- The name Loud Kettle (any letter case); the favicon letter and colours in `<link rel="icon">`.
- Photos (24, Unsplash: opening 6, no-shortcuts 4, on-tap 5, brew-day 5, taproom 3, visit 1): `src`, no `srcset`/`sizes`, `width`/`height` to the ratio, `alt`, CREDITS.md.
- `<title>`, meta description, og tags.

## Ask the owner for
All demo text, never to be invented:
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

## Known limits
- The booking form, the flight picker and the newsletter form only show a message on the page; nothing is sent until you connect them.
- Without JavaScript or with reduced motion, the brew-day wheel is a plain row of steps and the tap list a static staircase: complete, but without the wheel.
- There is no age check or responsible-drinking notice; add one if your local rules require it.
- The copy mixes "nothing is bottled" (brew-day) with cans, crowlers and growlers (events, faq): align it with how you really sell.

## Check
375 and 1440 px, reduced motion on, console clean; `data-8b-placeholder` and Loud Kettle left only in class names.
