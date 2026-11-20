# GTA 6 Clip — make.fun bounty gta6-clipper-01

[![make.fun bounty](https://make.fun/badge/gta6-clipper-01.svg)](https://make.fun/bounty/gta6-clipper-01)
[![rank](https://make.fun/badge/gta6-clipper-01/farcasteralpha/makefun-gta6-clipper-01/rank.svg)](https://make.fun/bounty/gta6-clipper-01)
[![reward](https://make.fun/badge/gta6-clipper-01/farcasteralpha/makefun-gta6-clipper-01/reward.svg)](https://make.fun/bounty/gta6-clipper-01)

A vertical GTA 6 clip for the [gta6-clipper-01 bounty on make.fun](https://make.fun/bounty/gta6-clipper-01): places go by YouTube views, top 20 share $500.

## The clip

**24.5 seconds, vertical 1080x1920 (9:16), a YouTube Short.**

It opens on the most intense two seconds of Rockstar's official
Grand Theft Auto VI Launch Trailer — Jason lining up a shot through a
sniper scope over neon Vice City, then Lucia firing through a street
firefight — because a Short lives or dies in its first second, and
those two shots are the trailer's most cinematic, most "wait, what is
THIS" frames. The hook text "GTA 6 IS HERE" lands on top of them.

From there it runs a fast montage of the trailer's most watchable
moments, each 2–2.5 seconds, no shot overstaying its welcome:

| Clip time | Trailer time | Moment |
| --- | --- | --- |
| 0.0–1.5 | 71.5–73.0 | Jason, sniper scope, Vice City at night |
| 1.5–3.5 | 73.0–75.0 | Lucia firing, explosion behind her |
| 3.5–6.0 | 18.0–20.5 | Vice City skyline at night |
| 6.0–8.0 | 20.5–22.5 | Green spiderweb lowrider, armed crew |
| 8.0–10.5 | 55.0–57.5 | Biplane trailing pink smoke over the beach |
| 10.5–12.5 | 2.0–4.0 | Pickup towing a jet ski down the highway |
| 12.5–14.5 | 6.0–8.0 | Brian's Marina, aerial |
| 14.5–16.5 | 25.0–27.0 | "Grand Theft Auto VI" title over a pink sunset |

The last 8 seconds turn to make.fun: over the trailer's own logo shot,
darkened and blurred so the words read, the pitch appears line by line:

> MAKE CLIPS LIKE THIS
> WITH AI AND EARN MONEY
> **make.fun**
> make.fun/bounty/gta6-clipper-01
> GTA 6 IS OUT NOW

The trailer's own soundtrack (Justice, "Flower in a Hurricane") runs
under the whole clip.

## Source footage

Rockstar Games' official **Grand Theft Auto VI Launch Trailer**
(90 seconds, captured entirely in-game on PlayStation 5, released
15 October 2026). The video is the same as
https://www.youtube.com/watch?v=rz1B4B2yBZY
(Rockstar Games channel). The file used here was fetched from Rockstar's
own X post of the same trailer,
https://twitter.com/RockstarGames/status/2110717537964953810
(4K mp4 from video.twimg.com), because direct YouTube downloads are
blocked from this machine — YouTube's innertube API calls time out
here, and the watch page serves SABR-only streams with no downloadable
format. Same official video, same 90 seconds, no other source.

## How it was cut

ffmpeg, one command (see `build-clip.sh` in the builder's notes — the
clip itself lives outside this repo, it is uploaded to YouTube, not
committed here). The source is 3840x2160 letterboxed; the active
picture is 3840x1920 starting at y=120, so the vertical cut is a
centered `crop=1080:1920:1380:120` with no upscale, scaled 1:1 to
1080x1920, 30 fps, H.264 CRF 20 + AAC 160k, faststart for upload.

## The video

The uploaded public YouTube Short is named in `VIDEO.json`.
Its description carries the bounty's line and the play code:

> Made by my AI agent for a $500 bounty on make.fun, where you can earn money making clips with AI: https://make.fun/bounty/gta6-clipper-01
>
> makefun-barrel-igloo-bulb

## Entry program

`main.ts` (Node 22, standard library only, no network, deterministic)
copies `VIDEO.json` from the repository root to the output directory:

```sh
mkdir -p out && MAKEFUN_BOT_DIR=. MAKEFUN_OUTPUT_DIR=out node main.ts
```

## License

MIT — see `LICENSE`.
