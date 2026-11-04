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

1. Calibrate the printer to the 2 × 1 roll. On most thermal printers, hold the feed button for 2–3 seconds until it feeds a few labels and beeps. Check the printer's manual.
2. In the printer driver, set the paper size to **Width 2 in, Height 1 in**. Width means across the print head.
3. In the browser print dialog, set Margins to **None**, Scale to **100%** or Default, and turn off headers and footers.
4. Click **Print test label**. "TOP" should read normally across one label, with tick marks at the middle of each edge. Adjust the nudge values to center it.
5. Leave **Rotate 90°** off unless the test label still prints sideways after the steps above.

### Troubleshooting

| What you see | Likely cause | Fix |
| --- | --- | --- |
| Each print uses two labels and the text is sideways | The driver paper size is 1 × 2 in, or Rotate 90° is on | Set the paper to Width 2, Height 1, and turn Rotate 90° off |
| Prints start partway into a label | The printer hasn't learned the gaps between labels | Calibrate the printer (step 1) |
| Content shifted to one side | Normal printer offset | Use the nudge values |
| Print is faint | Low darkness setting | Raise darkness or density in the driver |

## Later: inventory integration

The batch box already takes one row per label with tab-separated columns. An export from the inventory system in that shape can be pasted in directly. A later version could fetch the rows itself.
