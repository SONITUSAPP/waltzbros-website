# Waltz Brothers website: working guide

This repo is the Waltz Brothers demo website. This file is public, so it holds no pitch notes, prices or business estimates.

## How publishing works
- Vercel project `waltzbros-website` (team sonitusapps-projects, project id `prj_1NvmxK4HlTcrn73MnkjlDDUsw63l`) is linked to this repo.
- Every push to `main` goes live at https://waltzbros-website.vercel.app in about 30 seconds. No build step: plain static files served from the repo root.
- To change the site: edit, commit, `git push origin main`. Never use the Vercel inline-upload or chunked-loader workarounds; they caused hour-long sessions and broken deploys.

## Files
- `index.html`: the whole site in one file (about 400 KB): public website plus demo tabs (Owner Dashboard, Marketing & Ads, Visitor Intel, Employee Portal, Careers, Competitor Intel).
- `images/`: hero.jpg, hist1-4.jpg (1939 history photos), lathe1-2.jpg, p01-p37.jpg (part catalog).
- `email/teaser-1..6.jpg`: screenshots used by the HTML teaser email, hosted here so they load in email clients.

## Editing tips for index.html
- It's large. Use grep to find the section (`id="sec-about"`, `view-vis`, `view-own`, and so on), then edit just that spot. Don't rewrite the file.
- Images use `data-wb="key"` plus a real `src="images/key.jpg"`. Keep both. An empty `src=""` triggers the onerror handler and hides the photo as a grey box.
- After editing, check locally: `python3 -m http.server`, then load it in Playwright (the intro splash needs about 6.5 seconds, then click "ENTER WALTZ BROTHERS").

## Do not touch
- The old project `project-trgx7` (https://project-trgx7.vercel.app) and its `/presentation/` video pages (index, v1-v5). The owner said to leave them exactly as they are. They are not in this repo.

## Rules
- AI tools are internal only for Waltz employees. The real public site must show traditional precision and heritage messaging only. This repo is a demo that shows both sides.
- ITAR: controlled technical data (drawings, specs, anything export-controlled) never goes into the AI or this repo. The system routes the conversation, not the content. It must run on US-hosted, access-controlled infrastructure and work inside CMMC and NIST obligations.
- waltzbros.com is the company's main site. Nothing here should affect it.
