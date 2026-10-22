# 3 print CSS traps that broke my PDFs

Our PDF preview took 11 seconds and still did not match the screen. Printing the same HTML the editor renders, with headless Chromium, took it to 2.5 s cold and a 30 ms render. Three print-CSS traps cost a round each.

Read the full hack, with context and what it is good for: https://www.omerbinsaleem.com/hacks/print-css-traps/

## Steps

1. Stop rebuilding the document in a report engine. Print the same HTML the editor already renders, with headless Chromium, so screen and PDF cannot drift.
2. Trap 1: flex and grid containers never fragment across pages. Section bodies must be blocks.
3. Trap 2: overflow: hidden turns a table into an unbreakable scroll container. overflow: clip breaks fine across pages.
4. Trap 3: a gap that lands on a page break. A margin is dropped cleanly; padding leaves an empty bordered box on the next page. Use margins between sections.
5. Measure cold and warm separately. Most of the cold time is fonts and images, not the render.

## Prompt to copy

```text
Audit this HTML template for printing with headless Chromium. Flag every flex or grid container whose content may span a page (make the body a block), every overflow: hidden on a table or long list (use overflow: clip), and every padding that sits between sections (use margin). Then list what the page fetches on a cold render (fonts, logos, images) and how to inline or preload each.
```

Tag: Frontend · about 3 minutes · published 2026-10-21
