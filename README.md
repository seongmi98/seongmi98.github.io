# seongmi98.github.io

Personal academic site for **Seongmi Seon (선성미)**, Contract Researcher at Seoul National University (SNU Biosystems Engineering, 생체물성연구실).

Live at: <https://seongmi98.github.io>

## Stack

- Single-page static HTML/CSS, no JS framework and no build step.
- Typography: Inter (Google Fonts).
- Design system: NVIDIA design language (see [`DESIGN.md`](DESIGN.md), generated via [getdesign](https://www.npmjs.com/package/getdesign)).
- Two-surface architecture: black hero/footer + white body sections, single green accent `#76b900`.

## Files

| File | Purpose |
|---|---|
| `index.html` | The entire page (HTML + inline CSS) |
| `DESIGN.md` | NVIDIA design tokens used as the visual reference |
| `README.md` | This file |
| `.gitignore` | Ignored paths |
| `assets/profile.jpg` | Profile photo used in nav and hero |

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

- **About**: bio, education, core competencies, tools & skills, experience, certifications
- **Projects**: 4 research projects (object detection benchmarking, semantic segmentation, hyperspectral regression, composite material classification)
- **Presentations**: 4 conference talks (KSAM spring/fall, CIGR)

## Contact

- Email: <ddl05059@naver.com>
- GitHub: <https://github.com/seongmi98>
