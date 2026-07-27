# seongmi98.github.io

Personal job-hunting portfolio for **Seongmi Seon (선성미)**, Contract Researcher at Seoul National University (SNU Biosystems Engineering, 생체물성연구실). Built for domestic (Korean) data/AI hiring reviewers to scan in under 3 minutes — not a design showcase.

Live at: <https://seongmi98.github.io>

## Stack

- Single-page static HTML/CSS, no JS framework and no build step (one inline `<script>` for the email-copy button).
- Typography: Pretendard Variable (body/headings) + JetBrains Mono (metrics, dates, tags) — chosen so Korean and Latin text share consistent weight/spacing, and so numeric results read like measurement data.
- Design direction: "계측 리포트" (instrument report) — single 820px column, no animation, spectrum-band accents per project showing the sensor wavelength used.
- `DESIGN.md` documents the earlier NVIDIA-style token set and is kept for history only; it is no longer applied in `index.html`.

## Files

| File | Purpose |
|---|---|
| `index.html` | The entire page (HTML + inline CSS + one small JS snippet) |
| `CONTENT.md` | Source of truth for all site copy — edit this, then port changes into `index.html` |
| `DESIGN.md` | Historical NVIDIA design tokens (unused, kept for reference) |
| `README.md` | This file |
| `.gitignore` | Ignored paths |
| `assets/profile.jpg` | Profile photo used in the header |
| `assets/resume.pdf` | Resume download — **not yet added**, `index.html` links to it in advance |

## Local preview

No build step. Open `index.html` directly in a browser, or serve locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deployment

GitHub Pages serves `index.html` from the `main` branch automatically. To publish changes:

```bash
git add index.html
git commit -m "Update content"
git push
```

The live site refreshes in about 30 seconds.

## Sections

- **Header**: name, role, 3 headline metrics (mIoU, F1, inference speed), resume/email/GitHub actions
- **Intro**: 3–4 line summary
- **Projects**: 4 research projects (object detection benchmarking, semantic segmentation, hyperspectral regression, composite material classification), each with a problem/approach/result breakdown and a sensor-wavelength band
- **Tech Stack**: plain text list, no icons
- **Presentations**: 4 conference talks (KSAM spring/fall, CIGR)
- **Education / Career**: degrees, current position, certification

## Contact

- Email: <ddl05059@naver.com>
- GitHub: <https://github.com/seongmi98>
