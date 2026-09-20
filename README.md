# Nueva Vida RP V2 — public assets

Public image assets for the Nueva Vida RP V2 FiveM server listing.

`server.cfg` fetches these over `raw.githubusercontent.com`, which is why the repo is public
and why the filenames are load-bearing.

⛔ **Do not rename, move or delete anything here.** The server points at these raw URLs by
exact path. A rename breaks the listing silently — nothing appears in the console, the banner
simply stops loading. To change artwork, replace a file in place and keep its name.

## What is in use

| File | Dimensions | `server.cfg` |
|---|---|---|
| `nv2-banner-wide.png` | 1920 × 480 | `sets banner_detail` |
| `nv2-banner-connecting.png` | 1920 × 1080 | `sets banner_connecting` |
| `nv2-banner-detail.png` | 1865 × 108 | not referenced — alternate strip, see below |
| `nv2-icon.png` | 512 × 512 | not referenced — Discord profile picture |

The FiveM **server icon** is not here. It must be exactly **96 × 96 PNG** and lives on the
server itself as `nueva-vida-v2.png`, next to `server.cfg`.

## Why `banner_detail` uses the 1920 × 480 file

FiveM renders `banner_detail` as a short, wide strip, so a 16:9 image gets sliced through the
middle. The sibling repo `turftorque-assets` records **1920 × 480 as the shape confirmed to
work**, while Turf itself currently points at a 1865 × 108 file whose rendering has not been
re-verified since that server's rename.

Given the choice between a confirmed shape and an unconfirmed one, V2 uses the confirmed
**1920 × 480**. `nv2-banner-detail.png` (1865 × 108) is kept as a ready alternative if the
thinner strip turns out to look better on the live listing — that is a judgement that needs
eyes on the real page, not a guess.

`banner_connecting` is a different surface — the loading screen — where 16:9 is correct. The
two settings take the same kind of URL but are **not** interchangeable.

## Source artwork

Supplied by bryan as WebP: a 1142 × 1167 square logo and a 1145 × 456 wide banner. FiveM
cannot use WebP, so everything here was converted to PNG.

- `nv2-banner-wide` / `nv2-banner-connecting` — fill-cropped from the wide source so the
  logo stays centred rather than squashed.
- `nv2-banner-detail` — **composed**, not cropped: logo tile left, name and tagline, the
  source's truck band behind a dark left-to-right gradient, blue accent bar right. A plain
  crop put the artwork's own wordmark behind the overlaid text and read as duplicated.
- `nv2-icon` — centre-cropped from 1142 × 1167 to square before scaling, so nothing is
  distorted.
