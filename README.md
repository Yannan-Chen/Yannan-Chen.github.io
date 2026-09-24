# Yannan-Chen.github.io
 Online version of personal website

The site is built by [Jekyll](https://jekyllrb.com/), which GitHub Pages runs automatically on every push.
**To add or change content you only edit the YAML files in `_data/`** — no HTML needed.

## Where things live

| To change…                                   | Edit                                     |
| -------------------------------------------- | ---------------------------------------- |
| News (News page + latest on home page)       | `_data/news.yml` — add new items at the top |
| Publications (Publications page + home page) | `_data/publications.yml`                 |
| Research projects (Research page + home sidebar thumbnails) | `_data/research.yml`      |
| Interests (Interests page + home page)       | `_data/interests.yml`                    |
| Bio, tagline, "About" box, research summary  | `_data/profile.yml`                      |
| Social icons in the sidebar                  | `_data/social.yml`                       |
| Top bar / side menu pages                    | `_data/navigation.yml`                   |
| Site title, number of news items on home     | `_config.yml`                            |
| CV                                           | replace `CV.pdf`                         |

Each `_data` file has a comment at the top listing its fields. Examples:

```yaml
# _data/news.yml — newest first
- title: "Our paper is out in [Nature](https://www.nature.com/...)!"
  details: "optional second line"
  date: 2025-10-01
```

```yaml
# _data/publications.yml
- authors: "Jane Doe*, Yannan Chen*, et al."
  year: 2025
  title: "Paper title"
  url: "https://doi.org/..."
  journal: "Journal Name"
  details: "12 (3): 456"
  show_on_home: true
```

YAML tips: indentation matters (use spaces, not tabs), and wrap text in `"quotes"` —
especially if it contains a colon. Use `'single quotes'` around text that itself contains `"`.

## How it is put together

- `_layouts/default.html` — the page skeleton (head, scripts) shared by every page
- `_includes/` — shared pieces: `header.html`, `menu.html`, `sidebar.html` (home only),
  `news-list.html`, `publication-list.html`, `interests-list.html`
- `index.html`, `news.html`, … — each page only contains its own content; the
  `---` block at the top picks the layout, the tab title, and whether to show the sidebar
- `assets/`, `images/` — styles, scripts and pictures (HTML5 UP "Future Imperfect" theme)

## Previewing locally (optional)

Requires Ruby (on Windows: [RubyInstaller](https://rubyinstaller.org/) with DevKit).

```bash
bundle install
bundle exec jekyll serve
```

Then open http://localhost:4001. After pushing, check the repository's **Actions** tab
("pages build and deployment") — if a build fails, the previous version of the site stays online.
