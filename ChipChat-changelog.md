# ChipChat Changelog

## v0.06
- Designer Collection is no longer its own section. Say "DC" plus the code (e.g. "DC 4 1" or "DC 41") and the card is filed automatically: DC 1-1, 1-2, 2-1, 3-1, 4-1 go to Whites; DC 4-2 and 5-2 go to Neutrals. Cards show as "DC 4-1" in the order. Gray has none.
- A DC code that isn't on that list pops up the clarification box.
- Any old Designer Collection cards already in a saved order are moved into Whites/Neutrals.

## v0.05
- Whites, Neutrals and Grays: the first number goes up to 12, the second number only 1-8 (same as Core). So "123" can only mean 12-3, and far fewer entries trigger the "could be read two ways" pop-up. Saved sections are updated automatically.
- Designer Collection stays free-form until the section list is final.

## v0.04
- Added Whites (W), Neutrals (B) and Grays (G) sections. They use a single letter and take numbers up to 12 for both the first and second number.
- Added Designer Collection (DC) as a free-form section: each number you say after "DC" is kept as its own code (e.g. DC3, DC12). The code format is a placeholder until confirmed.
- Each section now has its own "1st max" and "2nd max" limits (Core = 8, W/B/G = 12), editable on the Add Section page. The parser uses them to split run-together digits (e.g. "W 123" becomes W12-3).
- New clarification pop-up: anything the app can't read, doesn't fit a section's limits, or could be read two ways (e.g. "W 112" = 1-12 or 11-2) shows what it read, why, and lets you correct it and re-add or skip. Everything else in the dictation is still added.
- Single-letter abbreviations are matched strictly so they don't misfire. The iOS autocorrect fix ("iOS" for "OS") still works for two-letter codes.
- Existing saved orders and sections carry over; the new sections are added to the front of the list.
- File name is now index.html.

## v0.03
- Rebuilt navigation around a single page picker at the top: "Order Page" (store number, dictation box, Add to order, Copy order, Download .txt, Start new order), one page per color section, and an "Add Section" page for managing sections.
- Order Page now shows a compact "Order so far" flash list at the bottom — every card currently in the order, grouped by section, so you can catch a dictation error without flipping to that section's page.
- This replaces the old single long scrolling page and resolves the earlier request to keep the entry controls from getting buried under a growing card list.

## v0.02
- Fixed a persistence bug: entered cards weren't actually surviving app closes or timeouts once hosted on GitHub Pages, because the save mechanism only worked inside Claude's own preview. Switched to standard browser storage (localStorage) so cards now stick around until you download the order or start a new one — even if the app times out or closes mid-count.
- Section colors are now derived from the color itself instead of an arbitrary cycle — each family (Red, Orange, Yellow, Green, Blue, Purple) has its own hue, and each tone (Pure, Muted, Shaded, Neutral) adjusts how vivid, dark, or grayed-down that hue looks. So Red Pure reads as a clean red, Red Muted as a dulled red, Red Shaded as a deep red, Red Neutral as a grayish red — same logic across all six families.
- Every card in the list now shows a colored left edge matching its section, visible even after scrolling past the section header.

## v0.01
- Renamed app to ChipChat
- Scope narrowed to Core Palette (Red–Purple, 24 sections)
- Dictation now parses as a letter/number stream — codes and section names resolve correctly even without pauses or punctuation
- Lenient abbreviation matching added to catch dictation autocorrect (e.g. "iOS" for "OS")
- Added Store # field (session only, does not persist)
- Added "Download .txt" — exported file is named with store number and today's date
- App icon added
