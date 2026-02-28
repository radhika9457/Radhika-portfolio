# Gallery layout guide: group span and image filtered span

How to choose **group span** and **image filtered span** classes in the My Work gallery.

---

## 1. Two ways to place images

### A. Standalone image (no group)

Use a single `<a>` as a **direct child** of `<div class="gallery">`:

```html
<a href="..." class="image filtered span-2-5" data-position="center" data-title="...">
  <img src="..." alt="..." />
</a>
```

- Takes **one column** in the gallery (fixed width, about 20rem on desktop).
- Good for: one big image per row, or a single image between groups.
- You can use any **span-X** on the link; on desktop the width is still one column. Use **span-2-5** or **span-3** for consistency and for small-screen behavior if the template uses it.

### B. Group of images (wrapped in a group)

Use a **wrapper** so several images share one column and sit in a **row**:

```html
<div class="group span-3">
  <a href="..." class="image filtered span-1-5" data-position="center" data-title="..."><img src="..." alt="..." /></a>
  <a href="..." class="image filtered span-1-5" data-position="bottom" data-title="..."><img src="..." alt="..." /></a>
</div>
```

- The **group** takes **one column** (same as one standalone image).
- Inside the group, each **image filtered span-X** gets a **percentage width**.
- Use a group when you want **2 or more images side by side** in that one column.

---

## 2. When to use a group

| Use a group | Use standalone |
|------------|----------------|
| 2+ images that should sit in one row (e.g. 2 halves, 3 thirds) | One image per column |
| You want to mix sizes in one row (e.g. one 50% + one 50%, or 33% + 66%) | One large hero image per row |

**Group:** `<div class="group span-3">` … `</div>`  
- Always use **span-3** on the group in this template (full width of the column).  
- The **children** of the group use the **image filtered span-X** classes to set their widths.

---

## 3. How to choose **image filtered span-X** (inside a group)

The gallery grid is **12 columns**. Span numbers are in “twelfths”:

| Class       | Width (inside group) | Use for                          |
|------------|----------------------|-----------------------------------|
| span-1     | ~33%                 | 3 equal images in one row         |
| span-1-25  | ~42%                 | Slightly wider than a third      |
| **span-1-5**  | **50%**             | **2 equal images in one row**    |
| span-1-75  | ~58%                 | One a bit wider than half        |
| span-2     | ~67%                 | One wide, one narrow              |
| span-2-25  | ~75%                 | 3/4 + 1/4                        |
| **span-2-5**  | **~83%**            | **One large, one small**         |
| span-2-75  | ~92%                 | One almost full width            |
| **span-3**    | **100%**            | **Single image full width of group** |

**Rule of thumb:** the **numbers in the class** add up to how many “columns” the image uses out of 12:

- **span-1-5** = 1.5 → 6/12 → **50%** (two per row)
- **span-2-5** = 2.5 → 10/12 → **~83%** (one big, one small)
- **span-3** = 3 → 12/12 → **100%** (full width of group)

**Inside one group, the span-X of the children should add up to 12** if you want one full row (e.g. two **span-1-5** = 6+6 = 12, or **span-2-5** + **span-1-5** ≈ 10+2 = 12).

---

## 4. data-position (crop/focus)

Use **data-position** on the **same** `<a>` as **image filtered span-X** to control how the image is cropped (e.g. face or product in center):

- `data-position="center"` – focus center
- `data-position="top"` / `"bottom"` – focus top/bottom
- `data-position="left"` / `"right"`
- `data-position="top left"` / `"bottom right"` etc.

---

## 5. Quick examples

**Row of 3 equal images:**

```html
<div class="group span-3">
  <a href="..." class="image filtered span-1" data-position="center" data-title="..."><img src="..." alt="..." /></a>
  <a href="..." class="image filtered span-1" data-position="center" data-title="..."><img src="..." alt="..." /></a>
  <a href="..." class="image filtered span-1" data-position="center" data-title="..."><img src="..." alt="..." /></a>
</div>
```

**Row of 2 equal images:**

```html
<div class="group span-3">
  <a href="..." class="image filtered span-1-5" data-position="center" data-title="..."><img src="..." alt="..." /></a>
  <a href="..." class="image filtered span-1-5" data-position="center" data-title="..."><img src="..." alt="..." /></a>
</div>
```

**One big + one small in a row:**

```html
<div class="group span-3">
  <a href="..." class="image filtered span-2-5" data-position="top" data-title="..."><img src="..." alt="..." /></a>
  <a href="..." class="image filtered span-1-5" data-position="center" data-title="..."><img src="..." alt="..." /></a>
</div>
```

**Single full-width image in a row (no group):**

```html
<a href="..." class="image filtered span-3" data-position="bottom" data-title="..."><img src="..." alt="..." /></a>
```

---

## 6. Summary

| What you want              | Markup |
|----------------------------|--------|
| One image, one column      | `<a class="image filtered span-2-5" ...>` (direct under `.gallery`) |
| Several images in one row  | `<div class="group span-3">` with `<a class="image filtered span-X">` inside |
| 2 equal in a row           | Group + two `span-1-5` |
| 3 equal in a row           | Group + three `span-1` |
| One big + one small        | Group + `span-2-5` + `span-1-5` (or similar) |
| One full-width in group    | Group + one `span-3` |

Always keep **image** and **filtered** on the link; change **span-X** to control size (especially inside a **group span-3**).
