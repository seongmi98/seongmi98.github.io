# seongmi98.github.io

Personal job-hunting portfolio for **Seongmi Seon (선성미)**, Contract Researcher at Seoul National University (SNU Biosystems Engineering, 생체물성연구실).

Live at: <https://seongmi98.github.io>

## Stack

- Multi-page static site built on the **Ronin** Bootstrap/jQuery template (Colorlib, CC BY 3.0). No build step — vendor assets are the pre-built CSS/JS shipped with the template.
- Typography: Ronin's own fonts (Heebo for headings, Roboto for body) plus JetBrains Mono for metrics/dates/tags, loaded via Google Fonts.
- All of the template's placeholder content (donation/volunteer counters, fake service offerings, client testimonials, blog, newsletter signup) has been removed; only real content remains.
- `css/custom.css` holds every real-content addition (spectral-band gradient visuals in place of stock photos, résumé-style definition lists, award/talk badges, the contact page's info block) — kept separate from the vendor `css/style.css` so template updates don't clobber it.
- `DESIGN.md` documents an earlier, unrelated single-page design and is kept for history only.

## Pages

| File | Purpose |
|---|---|
| `index.html` | Home — hero, intro + headline metrics, tech stack summary, project previews |
| `about-us.html` | About — full intro, detailed tech stack, education/career/certification, awards, presentations |
| `portfolio.html` | Portfolio — filterable grid of all 4 research projects |
| `project-detection.html` | Object detection model comparison & robot deployment |
| `project-segmentation.html` | Aerial RGB semantic segmentation |
| `project-hyperspectral.html` | Hyperspectral non-destructive moisture regression |
| `project-composite.html` | Hyperspectral composite-material classification (team project) |
| `contact.html` | Contact — email/GitHub/resume links (no map, no form — see below) |
| `resume.html` | Standalone print/PDF résumé page, unrelated styling, unchanged |
| `CONTENT.md` | Source of truth for all site copy |
| `css/custom.css` | Real-content styles layered on top of Ronin's `style.css` |

Removed from the original Ronin template (no real content to fill them, and GitHub Pages can't run the PHP contact form): `services.html`, `blog.html`, `single-blog.html`, `elements.html`, `portfolio-details.html` (replaced by the 4 project pages above), `contact_process.php`.

## Local preview

No build step. Serve the folder locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deployment

GitHub Pages serves the site from the `main` branch automatically. To publish changes:

```bash
git add -A
git commit -m "Update content"
git push
```

The live site refreshes in about 30 seconds.

## Contact

- Email: <ddl05059@naver.com>
- GitHub: <https://github.com/seongmi98>
