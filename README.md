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
| `nv2-banner-detail.png` | 1920 × 108 | `sets banner_detail` |
| `nv2-banner-connecting.png` | 1920 × 1080 | `sets banner_connecting` |
| `nv2-icon.png` | 512 × 512 | not referenced — Discord profile picture |

The FiveM **server icon** is not here. It must be exactly **96 × 96 PNG** and lives on the
server itself as `nueva-vida-v2.png`, next to `server.cfg`.

## `banner_detail` is COMPOSED, not cropped — and this was learned the hard way

FiveM renders `banner_detail` as a very thin, very wide strip: **1920 × 108, about 17.8:1**.

The source artwork is **1693 × 652 (2.60:1)** once its letterbox bars are cropped off. Cropping
that to 17.8:1 discards **85% of the height** and slices straight through the logo.

That is not theoretical. A 1920 × 480 version was tried first, on the strength of a note in the
sibling repo `turftorque-assets` calling that "the shape confirmed to work". **It rendered wrong
on the live listing** — logo cut off top and bottom. Live evidence beat the note.

So the strip is **composed**: icon tile on the left, server name and tagline, a darkened band of
the artwork behind a left-to-right gradient, blue accent bar on the right. That is the same
construction Turf's own detail banner uses, and it is why the text stays readable at 108px tall.

⭐ **If you make new artwork, design the strip separately.** At 17.8:1 there is no room for a tall
logo — small mark at one end, text along the middle, low-contrast background.

`banner_connecting` is a different surface — the loading screen — where 16:9 is correct and the
artwork can be used almost as-is. The two settings take the same kind of URL but are **not**
interchangeable.

## Source artwork

Supplied by bryan as WebP. FiveM cannot use WebP, so everything here is converted to PNG via
Windows Imaging Component (no ImageMagick or ffmpeg on the machine).

⚠️ The supplied banner arrives **letterboxed** — black bars top and bottom. Those are detected by
row-scanning for the first and last non-black rows and cropped **once**, before anything else, so
no derived image inherits them.
