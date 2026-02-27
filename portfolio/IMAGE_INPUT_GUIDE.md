# Portfolio Image Input Guide

Use the file **portfolio_images_input.csv** in Excel (or any spreadsheet) to define where each image appears on your portfolio. A developer or script can use this to update the website without editing code.

---

## How to use

1. Open **portfolio_images_input.csv** in Microsoft Excel (or Google Sheets).
2. Fill one row per image. Do not remove the header row (first row).
3. Save the file (Excel can save as .xlsx if you prefer).
4. Share the file with your developer or run the update script (if available).

---

## Column reference

| Column | Required | Description | Example values |
|--------|----------|-------------|----------------|
| **Section** | Yes | Where on the page the image goes | `Banner`, `About`, `Education`, `Experience`, `Gallery` |
| **Input Image Path** | Yes | Path to the image file (from portfolio folder) | `images/pic01.jpg`, `images/work/My Post.png` |
| **Position** | Yes | Placement in that section | `left`, `right`, `center` |
| **Width** | No | Display width | `auto`, `50%`, `400px` |
| **Height** | No | Display height | `100%`, `300px`, leave empty for auto |
| **Max Width (px)** | No | Maximum width in pixels | `420`, `800`, leave empty for no limit |
| **Max Height (px)** | No | Maximum height in pixels | `600`, `800`, leave empty for no limit |
| **Object Fit** | No | How image fills the space | `cover` (crop to fill), `contain` (fit inside), `fill` |
| **Alt Text** | Recommended | Short description (accessibility & SEO) | `Grand Opening poster design` |
| **Title** | Recommended | Short project title or description; shown when user selects/clicks the image (e.g. in gallery lightbox or as tooltip) | `Restaurant Grand Opening – Food & venue Instagram story` |
| **Order** | For Gallery | Order of appearance (1, 2, 3…) | `1`, `2`, `3` |
| **Gallery Slot** | For Gallery | Slot number in the gallery grid (1–9) | `1` to `9` |
| **Notes** | No | Your own notes (ignored by script) | `Update in December` |

---

## Section values

- **Banner** — Big hero image next to “Hello, I’m Radhika Agrawal”.
- **About** — Image in the “About Me” spotlight section.
- **Education** — Image in the Education section (if used).
- **Experience** — Image on the right in the Experience section (e.g. partial right with plain background).
- **Gallery** — One of the 9 gallery items; use **Gallery Slot** 1–9 and **Order** for order.

---

## Title column

- **Title** is the short text that appears when a visitor selects an image: in the **gallery**, it is shown below the image in the lightbox; for **Banner**, **About**, and **Experience** images, it appears as a hover tooltip. Use it to describe what the project is or the image content (e.g. client, campaign, or type of work).

---

## Tips

- **Paths:** Use paths relative to the portfolio folder, e.g. `images/work/Your File.jpg`. For files with spaces or special characters, keep the exact filename.
- **Gallery:** Each row with Section = `Gallery` should have a different **Gallery Slot** (1–9). **Order** can be the same as slot or your preferred order.
- **Sizes:** Leave Width/Height empty to use the section’s default. Use Max Width / Max Height to limit size (e.g. Experience image: Max Width 420).
- **Object Fit:** `cover` = fill area, may crop. `contain` = whole image visible, may show empty space.
