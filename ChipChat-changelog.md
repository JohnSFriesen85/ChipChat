# ChipChat Changelog

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
