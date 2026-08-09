# Changelog

## Version 1.0.0 — August 9, 2026

First public release of the Skin by hippO coming-soon page.

### Added

**Visual design**
- Coming-soon page built to the hippocraticOath brand guidelines: Cream background, Dark Blue text, Hippo Purple accents, and the hippo logomark as the central illustration.
- Self-hosted Petrona and Quicksand webfonts, so type renders correctly without a third-party font request.
- Primary logo lockup in the header, with the hippo mark and wordmark as separate elements so each can be animated independently.

**Animation**
- Opening sequence: a full-screen field of hippos clears outward from the header, leaving the logo hippo as the only one standing, then the wordmark, headline, and illustration arrive in turn.
- Headline cross-fades from "Healthy skin starts here." to "Coming soon." and back.
- The hippo blinks once per cycle, cued to the sequence rather than a free-running clock.
- The sequence replays on a loop while the page sits idle, and stops permanently as soon as a visitor interacts.
- Accent hippos in the brand purple are scattered through the opening field, placed on unique rows and columns and held clear of the centre logo.

**Notify Me form**
- Email signup that reveals itself on hover, tap, or focus, sliding the hippo aside to make room.
- Submissions post to a Google Sheet through Apps Script, with Formspree supported as an alternative endpoint.
- Successful signups show a confirmation message in place of the field, and the headline returns to "Healthy skin starts here."
- Hidden honeypot field to catch automated submissions.

**Social sharing and metadata**
- Open Graph and Twitter Card tags with a 1200×630 share image, so links preview correctly across platforms.

**Favicons**
- Full icon set: `favicon.ico`, 16px and 32px PNGs, an SVG icon, and an Apple touch icon.

**Deployment**
- Static site with a `vercel.json` config, including long-lived cache headers for the self-hosted fonts. No build step required.
- Vercel Web Analytics, added as two script tags with no package install or build step.

### Improved

**Mobile**
- The hippo is cropped to its front half on small screens and anchored to its nose, so the artwork reads at phone widths.
- The illustration bleeds off the left edge while keeping its margin on the right.
- The email field and button stack into full-width rows with 44px tap targets, and the field text centres to match the button.
- The opening sequence runs slower on mobile than on desktop.
- Layout adapts to short screens by height rather than by device, so landscape and small laptops are handled.

**Technical**
- Design controls consolidated into a single documented block of CSS variables covering layout, spacing, sizing, and every animation timing, with the JavaScript reading its values from the same source.
- Opening field renders from one shared background image instead of hundreds of inlined copies of the artwork.

### Fixed

- Page no longer flashes white or reflows the headline on load: base colours are declared up front, fonts preload, and a metric-matched fallback holds the headline's position until Petrona arrives.
- Hippo fades in cleanly instead of appearing for a frame before the animation starts.
- Illustration no longer overflows its container or clips the hippo's nose on mobile.
- Footer and illustration no longer dip out of view when the sequence replays.
- Blink fires on every loop rather than only on first load.
- Accent hippo count is always odd, as intended, even when the grid is too small to place them all.
