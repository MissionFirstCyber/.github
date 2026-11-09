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

## Saving your own templates

1. Set up a label the way you want it: wording, sizes, layout, branding and spacing.
2. Under **Template & size**, type a name such as "New kit SSD" and click **Save template**.
3. To use it later, pick it from the **Start from** list under "My templates", or click **Load** next to it.

- **Update** replaces a saved template with the current design.
- **Delete** removes it.
- Saving with a name that already exists asks before replacing it.

A template stores the line text and formatting, layout, branding settings, spacing and label size. It does not store the logo image, batch rows, or printer adjustments such as nudge and rotate, so one calibration works for every template.

### Keeping templates when the browser forgets

Templates and settings are saved in the browser automatically. Some Chrome setups erase that data whenever Chrome closes, either through a setting or a company policy. The setting is at `chrome://settings/content/siteData`.

To make your templates permanent, click **Download page with my templates**. It saves a copy of this page named `kit-label-maker.html` with your templates, logo and printer adjustments built into the file. Open that file from now on. If the browser has lost its saved data, the page loads everything from the file instead.

The page shows a warning when it has changes that are not in the file yet. After adding or changing templates, download the page again and replace your old copy.

**Back up templates & logo** and **Restore from backup** do the same job with a separate data file. They are useful for merging templates into a page that already has others. **Reset everything** keeps your saved templates.

## First-time printer setup

1. Calibrate the printer to the 2 × 1 roll. On most thermal printers, hold the feed button for 2–3 seconds until it feeds a few labels and beeps. Check the printer's manual.
2. In the printer driver, set the paper size to **Width 2 in, Height 1 in**. Width means across the print head.
3. In the browser print dialog, set Margins to **None**, Scale to **100%** or Default, and turn off headers and footers.
4. Click **Print test label**. "TOP" should read normally across one label, with tick marks at the middle of each edge. Adjust the nudge values to center it.
5. Leave **Rotate 90°** off unless the test label still prints sideways after the steps above.

### Settings that work: Jadens JD-168 on Windows

Open Printing Preferences, then the **Stock** tab:

- **Default Paper:** a custom size of 2.00 in wide by 1.00 in high.
- **Paper Type:** the labels-with-gaps option, not Continuous.
- **Gap:** the measured gap between labels, about 3 mm on most 2 × 1 rolls. It only needs to be close because the sensor finds the real gap.
- **Post-Print Action:** Tear Off. If the gap still stops short of the tear bar, add a few millimetres in **Feed**.
- **Appear:** "After job" keeps a batch together as one strip. "After each page" moves every label to the tear bar.

After changing the paper type, recalibrate the printer as described in its manual.

### Troubleshooting

| What you see | Likely cause | Fix |
| --- | --- | --- |
| Each print uses two labels and the text is sideways | The driver paper size is 1 × 2 in, or Rotate 90° is on | Set the paper to Width 2, Height 1, and turn Rotate 90° off |
| Prints start partway into a label | The printer hasn't learned the gaps between labels | Calibrate the printer (step 1) |
| Content shifted to one side | Normal printer offset | Use the nudge values |
| Labels slowly drift, or a print starts over the gap | Driver media type is set to Continuous | Set the paper type to labels with gaps and calibrate |
| Printed label stops just short of the tear bar | No tear-off feed after printing | Set the post-print action to Tear Off, then fine-tune the feed offset |
| Print is faint | Low darkness setting | Raise darkness or density in the driver |

## Later: inventory integration

The batch box already takes one row per label with tab-separated columns. An export from the inventory system in that shape can be pasted in directly. A later version could fetch the rows itself.
