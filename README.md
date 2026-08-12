# Card School

A Pokemon TCG primer covering the Wizards of the Coast era, 1999 to 2003, plus the Japanese origin that predates it. Single-page site that teaches the sets, the print-run variations [1st Edition, Shadowless, Unlimited, and Japan's No Rarity], the chase cards, and how Wizards lost the licence.

Sister project to Watch School. Same shape, different subject.

## Stack

Single static `index.html`. No build step, no dependencies. Light and dark themes, filterable set timeline, CSS-drawn card mockups for the print-run switcher.

## Run locally

Open `index.html` in a browser, or serve the folder:

```
python3 -m http.server 8000
```

## Card images

The eight grail cards load from `images.pokemontcg.io`, the Pokemon TCG API's public image CDN. That keeps the repo text-only and the images sharp.

`assets/` holds the same eight cards downsized as a local fallback. Five came from Crystamber's scan library [base 4 and 2, teamrocket 83 and 4, neogenesis 9], three from the CDN. If the CDN ever breaks, swap the eight `src` attributes from `https://images.pokemontcg.io/<set>/<num>.png` to `assets/cN.jpg` and the page keeps working offline.

The Japanese cards in the origin section have no images. Pikachu Illustrator and the Trophy Pikachus are not in the Pokemon TCG API, which carries English sets only, so those are presented as stat tiles instead of card art.

## Deploy

Hosted on Vercel as the `pokemon-wotc-era` project - https://pokemon-wotc-era.vercel.app

Deployed via the Vercel MCP tool, not the CLI. The stored CLI token under `~/Library/Application Support/com.vercel.cli` is expired - run `vercel login` if you want CLI deploys back. `.vercel/` is gitignored.

Deployment protection is on by default, so the URL asks for a Vercel login. Turn it off in project settings to make it public.

Note: this project sits in Nelsen's personal Vercel scope, while Watch School is under the team account.

## Sources

Set names, dates and card counts follow Bulbapedia's English expansion list. The $550,000 Charizard is the Heritage Auctions sale from December 2025. The $16.49M Pikachu Illustrator is the Goldin sale from February 2026, reported by CNN. Japanese launch date [20 October 1996, Media Factory] per collector references on the No Rarity print run.
