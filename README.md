# Zionhilt Portfolio

Personal portfolio of **Oni Oluwafemi Dare** — Full-Stack & Security Systems Engineer.
A single-file, no-build-step website with a dark terminal aesthetic, keyframe animations, and a layout that adapts from small phones to wide desktops.

## Preview

Open `portfolio.html` in any modern browser. No install, no bundler, no dependencies.

To serve it locally instead:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000/portfolio.html
```

## What's on the page

| Section | What it shows |
| --- | --- |
| Hero | Terminal-style boot animation, headline, headshot card, social links |
| About | Bio, quick facts, **Download CV** button |
| Services | Hardware engineering, web and software development, cybersecurity analysis and facilitation |
| Skills | Grouped by languages, backend, frontend, security and OSINT, tools |
| Projects | Cards with highlights, tech tags, and GitHub links |
| Published work | Book feature: *Sniffing Techniques on Mobile Hacking via Wireless* |
| Journey | Vertical timeline of education, roles, and builds |
| Contact | Copy-to-clipboard rows, plus a form that opens the visitor's mail client |

## Project structure

```
.
├── portfolio.html                  # the whole site: HTML, CSS and JS in one file
├── assets/
│   └── doc/
│       └── Oni-Oluwafemi-Dare-CV.pdf   # target of the "Download CV" button
├── portfolio.jsx                   # earlier React + Tailwind draft (not kept in sync)
└── README.md
```

`portfolio.html` is the maintained version. `portfolio.jsx` is the first draft and does not include the later changes (About, Services, Book, real content).

## Customising

All editable content sits at the top of the `<script>` tag in `portfolio.html`.

| What to change | Where |
| --- | --- |
| Email, phone, GitHub, LinkedIn, X/Twitter | `profile` object |
| CV file | `profile.resume` (path relative to the HTML file) |
| Book link | `profile.book` — until it is set, the button shows "Link coming soon" |
| Headshot | `PHOTO` constant (a base64 data URI); replace it with your own image data or a file path |
| Terminal intro lines | `bootLines` |
| Skill groups | `skillGroups` |
| Projects (highlights, tags, repo and demo links) | `projects` |
| Services | `services` |
| Timeline | `timeline` |

Project cards currently link to the GitHub profile. Replace each project's `github:` value with the exact repository URL, and fill in `demo:` where a live demo exists.

Colours and fonts are CSS variables in the `:root` block at the top of the `<style>` tag (`--accent`, `--bg`, `--surface`, and so on).

## Updating the CV

1. Export the new CV as a PDF.
2. Save it in `assets/doc/`.
3. Point `profile.resume` at the new file name.

## Deploying

The site is static, so any static host works:

- **GitHub Pages:** push the folder, rename `portfolio.html` to `index.html`, and enable Pages on the branch.
- **Netlify / Vercel / Cloudflare Pages:** drag the folder in, or connect the repo. No build command is needed.

Keep the `assets/` folder next to the HTML file so the CV link keeps working.

## Details worth knowing

- **Responsive:** fluid type and spacing via `clamp()`, with breakpoints for tablets and very small phones.
- **Motion:** CSS keyframes and scroll-triggered reveals. Users who set *reduce motion* in their OS get near-instant transitions.
- **Fonts:** Inter and JetBrains Mono load from Google Fonts and fall back to system fonts when offline.
- **Contact form:** there is no backend. Submitting builds a `mailto:` link, so the visitor's mail app sends the message.
- **Privacy:** the CV and page list a phone number and email address. Check both before publishing.

## Author

**Oni Oluwafemi Dare** (Zionhilt)

- GitHub: https://github.com/Zion44719
- LinkedIn: https://www.linkedin.com/in/oluwafemi-d-oni-a28061151/
