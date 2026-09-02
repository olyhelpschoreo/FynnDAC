# Deploying the Dad Advisors Council page to fynnfamily.com/dadcouncil

The page is a **single self-contained HTML file**. No build step, no dependencies,
no framework. The only external requests are Google Fonts.

## What to do

1. Copy the `dadcouncil/` folder from this handoff into the web root of
   fynnfamily.com (the directory Firebase Hosting publishes — usually `public/`):

       public/
         dadcouncil/
           index.html      <- the page

2. Deploy as normal (`firebase deploy --only hosting`).

3. The page is then live at **https://fynnfamily.com/dadcouncil**

That's it. Nothing else needs to change.

## Notes

- **Do not rename the folder.** Two asset paths inside the file are absolute
  (`/dadcouncil/assets/...`), so the folder must be called `dadcouncil`.
- Assets are optional and not yet supplied. When the favicon and hero image
  exist, drop them at `public/dadcouncil/assets/favicon.svg` and
  `public/dadcouncil/assets/hero.jpg`. Until then the page renders fine —
  the hero shows a placeholder box.
- The social share image is referenced at `https://fynnfamily.com/council-og.jpg`
  and does not exist yet, so a texted link shows no preview card.
  Drop a `council-og.jpg` at the web root to fix.
- `<meta name="robots" content="noindex, nofollow">` is deliberately in place
  while the page still has placeholders in it. **Remove that line at launch.**

## Still to be filled in before launch

All in one `CONFIG` block at the bottom of the file:

    CLOSE_DATE   currently "August 14, 2026"  <- in the past, needs the real date
    START_DATE   currently "[DATE]"
    SURVEY_URL   done - points at the Google Form
    VIDEO_URL    empty - Stefan's ~60s video not filmed yet

Change those four values and the whole page updates itself.
