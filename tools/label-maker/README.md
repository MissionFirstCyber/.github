# Kit Label Maker

A single HTML file for designing and printing small thermal labels for Rhombus kits, such as SSD drives and kit cases. No install, no server, no internet connection needed.

## Use it

1. Download `index.html` and open it in Chrome or Edge.
2. Pick a template, type your lines, and check the preview.
3. Click **Print labels**.

Your text, settings and uploaded logo are remembered in that browser.

## Features

- Sized for 2 × 1 in labels by default. Width and height are adjustable.
- Up to 4 lines, each with its own size, bold, and fixed-width font for serial numbers.
- Text shrinks to fit automatically. A warning appears when it still doesn't fit.
- Optional logo and brand name, either across the top or down the left side.
- Upload your official logo (PNG or SVG). It can be converted to pure black and white so it prints crisply.
- Print many labels at once by pasting rows from a spreadsheet. Use `{1}`, `{2}`, `{3}` in a line to insert that column and `{#}` for the row number.
- Printer alignment tools: nudge, edge margin, 90° rotation, and an outline for test prints.

## First-time printer setup

1. In the printer driver settings, add or select a 2 × 1 in (50.8 × 25.4 mm) paper size.
2. In the browser print dialog, set Margins to **None**, Scale to **100%**, and turn off headers and footers.
3. Turn on **Print outline**, print one label, and adjust the nudge values until the box is centered.
4. If text prints sideways or spans two labels, turn on **Rotate 90°**.

## Later: inventory integration

The batch box already takes one row per label with tab-separated columns. An export from the inventory system in that shape can be pasted in directly. A later version could fetch the rows itself.
