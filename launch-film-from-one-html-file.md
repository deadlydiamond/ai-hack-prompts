# A 94 second launch film from one HTML file

No editor was opened. One HTML file of 436 lines, 14 script lines read by a local voice model, every cut snapped to a 112 BPM beat grid, 11 phone recordings inside a CSS phone, 2,838 frames rendered in 62 seconds.

Read the full hack, with context and what it is good for: https://www.omerbinsaleem.com/hacks/launch-film-from-one-html-file/

## Steps

1. Brand folder first: fonts, logo, patterns and one music track, pulled from the brand drive. Nothing invented.
2. Fourteen script lines, one real use case each, numbers written as words so the voice reads them right, commas where it should breathe.
3. Kokoro reads every line into its own wav at speed 0.92, with 0.6 s between lines.
4. Librosa finds the beat of the track (112 BPM). Every line start and every cut snaps to that grid.
5. Eleven phone recordings cut silent, shown inside a CSS phone. Fourteen scenes animated with GSAP on transforms and opacity only, scrubbable both ways.
6. Lint to zero errors, render, then a 12-frame contact sheet to check every scene before sending it.

## Prompt to copy

```text
Build a 90 second launch film for our app as a HyperFrames composition (1920x1080, 30 fps). Brand: everything in brand/, follow brand.md exactly. Footage: the screen recordings in clips/, inside a CSS phone frame. Script: script.txt, one line per scene, numbers as words, do not change the lines. Voice: Kokoro, one wav per line, speed 0.92, 0.6 s gaps. Music: brand/track.wav at 0.16 under the voice; detect its BPM with librosa and snap every line start and cut to the grid. GSAP on transforms and opacity only, seek-safe. Finish with: check at 0 errors, render, and a 12 frame contact sheet.
```

Tag: Video · about 3 minutes · published 2026-10-22
