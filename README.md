# Erica Nelson-Brown | Cybersecurity Portfolio

A responsive, accessible portfolio built with semantic HTML and CSS. It presents cybersecurity learning projects, technical foundations, and a clear career focus.

**Live site:** https://nelsonbrownerica-collab.github.io/ideal-giggle/  
**Repository:** https://github.com/nelsonbrownerica-collab/ideal-giggle

## Portfolio focus

- Security operations and SOC Analyst I readiness
- SIEM concepts, log analysis, and alert triage
- Incident analysis and response documentation
- Network analysis and vulnerability assessment fundamentals
- Cloud security learning, including AWS concepts
- Technical documentation and evidence-based reporting

## Repository structure

| Path | Purpose |
| --- | --- |
| `index.html` | Home page and portfolio overview |
| `about.html` | Professional background and career focus |
| `skills.html` | Technical foundations and transferable skills |
| `projects.html` | Existing project links and planned project ideas |
| `portfolio.html` | Visual portfolio gallery |
| `contact.html` | Professional contact links |
| `style.css` | Shared responsive design system |
| `docs/project-template.md` | Reusable format for documenting future projects |
| `docs/project-roadmap.md` | Suggested learning and portfolio sequence |

## Project integrity

Portfolio entries link to learning reports, coursework, and lab journals. Unless explicitly identified otherwise, they represent training or simulated environments—not paid cybersecurity employment, production incident response, or work performed for an employer.

Planned projects are labeled as planned. They should only be presented as completed after the work has been performed and evidence has been added.

## Add a new project

1. Complete the lab in an authorized training environment.
2. Save sanitized screenshots, sample commands, queries, and relevant outputs.
3. Write a report using [the project template](docs/project-template.md).
4. Remove secrets, personal data, tokens, IP addresses that should not be public, and any employer/client information.
5. Add a project card to `projects.html` with an accurate status and a link to the report.
6. Test all links and review the page on mobile and desktop.

## Run locally

This is a static site. No package manager or build step is required. Open `index.html` in a browser, or run a local static server from the repository root:

```bash
python -m http.server 8000
```

Then visit `http://localhost:8000`.

## Accessibility and maintenance

The site includes semantic landmarks, a skip link, responsive layouts, visible keyboard focus, descriptive image alternatives, and reduced-motion support. Keep project claims evidence-based and update the footer year when needed.

## Contact

- Email: ericanelsonbrown@gmail.com
- LinkedIn: https://www.linkedin.com/in/erica-nelson-brown
