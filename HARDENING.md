# Portfolio Hardening

## 1. Break Testing

The contact form was tested under the following conditions. All four cases reached the EmailJS success state, which is a known limitation — see Known Limitations (§6) for details.

| Test | Result |
|---|---|
| Empty form submission | Reached success state |
| Garbage / invalid email address | Reached success state |
| Very long / garbage input in all fields | Reached success state |
| Rapid double submission | Reached success state |

These results indicate that the current form lacks sufficient client-side validation and server-side rate limiting. The submissions reaching the success state is not a pass — it is a gap that should be addressed in a future hardening pass.

---

## 2. Browser Testing

Tested in Chrome desktop.

| Page / Feature | Result |
|---|---|
| Home | Working |
| Projects section | Working |
| GitHub links | Working |
| LinkedIn link | Working |
| Calendly link | Working |
| Contact form | Working |

---

## 3. Mobile Testing

Tested at 375 px viewport width.

| Area | Result |
|---|---|
| Home | Working |
| Navbar (hamburger) | Working |
| Projects section | Working |
| External links | Working |
| Contact form | Working |
| Horizontal scrolling | None observed |
| Layout issues | None observed |

---

## 4. SEO

The following metadata was added or verified in `index.html`:

- Page `<title>` — added / verified
- `<meta name="description">` — present
- Open Graph: `og:title`, `og:description`, `og:image`, `og:type` — present
- Open Graph: `og:url` — added
- Twitter card metadata (`twitter:card`, `twitter:title`, `twitter:description`, `twitter:image`) — present
- Canonical URL (`<link rel="canonical">`) — added

**Lighthouse SEO score improved from 92 → 100.**

---

## 5. Performance

### Before optimisation

| Metric | Score / Value |
|---|---|
| Performance | 49 |
| Accessibility | 100 |
| Best Practices | 100 |
| SEO | 92 |
| Total network payload | ~49.5 MB |
| Main issue | Very large animated GIF project assets |

### After optimisation

| Metric | Score / Value |
|---|---|
| Performance | 83 |
| Accessibility | 100 |
| Best Practices | 100 |
| SEO | 100 |

### What was done

The four large animated GIF project previews (os.gif, phoenix.gif, python game.gif, teckstock.gif) were converted to optimised WebM (VP9) and MP4 (H.264) video assets, scaled to 800 px wide at 15 fps. Poster JPEG images (first frame) were extracted for each to serve as the pre-load placeholder and non-video fallback. The HTML was updated to use `<video autoplay loop muted playsinline loading="lazy">` elements with both sources and an `<img>` fallback inside each `<video>` tag.

museum.gif was kept as-is (0.7 MB) and had `loading="lazy"` and `decoding="async"` added to its `<img>` tag.

The original GIF files were retained in the project directory and were not deleted.

---

## 6. Known Limitations

The following issues are observed but **not yet fixed**:

- **Font Awesome unused CSS** — approximately 18 KiB of potential savings from unused icon styles being loaded.
- **Main-thread work** — approximately 5.0 seconds of total main-thread blocking time reported by Lighthouse.
- **Long tasks** — 14 long main-thread tasks identified; the longest is approximately 575 ms.
- **Contact form validation gap** — the form currently accepts empty, invalid, and excessively long submissions and can reach the EmailJS success state without meaningful validation. Stronger client-side validation, input length limits, and server-side rate limiting are needed in a future hardening pass.

---

## 7. Fixes Completed

- Added canonical URL (`<link rel="canonical">`)
- Added Open Graph URL (`og:url` meta tag)
- Added and verified full SEO metadata (title, description, Open Graph, Twitter card)
- Converted four large animated GIF project previews to optimised WebM + MP4 video assets with poster images
- Added `loading="lazy"` and `decoding="async"` to project card media elements where appropriate
- Added explicit `width` and `height` attributes to project card media to reduce layout shifts
- Extended CSS hover/scale rules to cover `<video>` elements alongside `<img>` elements
- Verified optimised media on the live deployment

---

## 8. Hardening Review

- **Reviewer / mentor name:** _(to be completed)_
- **Review date:** _(to be completed)_
- **Review method:** _(to be completed — e.g. live walkthrough, code review, Lighthouse audit)_

### Reviewer findings and verification

| Item | Finding |
|---|---|
| Resume link | Verified working; the resume PDF exists at the expected path. |
| GitHub, LinkedIn, and Calendly links | Verified working. |
| Header navigation | Verified working. |
| Mobile navigation and layout | Verified working at 375 px with no horizontal scrolling. |
| Contact form | Existing EmailJS contact form is working. The reviewer's observation that the form was missing does not match the current implementation, so no replacement form was added. |
| Virtual Museum media | museum.gif is currently used and is approximately 762 KB per Lighthouse. It already uses lazy loading and async decoding. No major performance fix was required for this asset. |

### Must-fix findings

_(to be completed)_

### Actions taken

_(to be completed)_
