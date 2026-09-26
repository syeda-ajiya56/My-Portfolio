# Ajiya Shaukat — Personal Portfolio

A responsive personal portfolio website showcasing my work as a Software Engineering student and entry-level full-stack developer.

The portfolio is designed to give recruiters, university reviewers, clients, and other visitors a quick way to understand my background, technical skills, selected projects, experience, and ways to contact me.

**Live site:**
https://ajiya-portfolio-kappa-eight-35.vercel.app/

**GitHub:**
https://github.com/syeda-ajiya56/My-Portfolio

---

## 1. What It Does

This portfolio presents my software engineering work in one place.

Visitors can:

* Learn about my background and technical focus.
* Review my skills and technologies.
* Explore selected software projects.
* View project screenshots, videos, and demonstrations where available.
* Access my GitHub repositories and professional profile.
* Download my resume.
* Contact me through the portfolio contact form.
* Schedule a meeting through my Calendly link.

The site is intended primarily for **recruiters, employers, university reviewers, potential clients, and other people evaluating my software engineering work**.

---

## 2. Main Features

### Personal Introduction

The landing section introduces my background, current focus, and software engineering interests.

### Skills

The portfolio presents the technologies and development areas I have worked with, including frontend, backend, programming languages, databases, APIs, and development tools.

### Project Showcase

Selected projects demonstrate different areas of my experience, including:

* Full-stack web development
* Java desktop development
* SQL Server-based applications
* Python and Flask
* React-based interfaces
* API and chatbot work
* Interactive and visual web experiences

### Project Media

Project cards use screenshots, videos, posters, and other visual assets to make the work easier to evaluate without requiring every visitor to install each project locally.

### Resume

The portfolio provides access to my current resume.

### Contact

The contact section provides a way for visitors to reach me directly.

### Scheduling

A Calendly integration provides an additional way for interested visitors to schedule a conversation.

### Responsive Design

The site is designed to work across desktop and mobile screen sizes.

---

## 3. Technology

The portfolio is intentionally lightweight and uses a simple static-web architecture.

### Core technologies

* HTML5
* CSS3
* JavaScript
* Vercel

### Supporting services

* EmailJS for the contact form
* Calendly for scheduling
* Vercel Analytics for deployment analytics
* GitHub for source control and project hosting

The project does not require a frontend framework or application database.

---

## 4. Architecture

The portfolio uses a simple static architecture:

```text
                        ┌──────────────────────┐
                        │      Visitor         │
                        └──────────┬───────────┘
                                   │
                                   ▼
                        ┌──────────────────────┐
                        │   Vercel Deployment  │
                        └──────────┬───────────┘
                                   │
                                   ▼
                        ┌──────────────────────┐
                        │     index.html      │
                        │  Portfolio content   │
                        └──────────┬───────────┘
                                   │
                                   ▼
                        ┌──────────────────────┐
                        │      style.css      │
                        │  Layout + styling    │
                        └──────────┬───────────┘
                                   │
                  ┌────────────────┼────────────────┐
                  ▼                ▼                ▼
             Project media      Contact         External
             + resume           form            services
                                  │
                                  ▼
                              EmailJS
```

The static architecture keeps the portfolio simple to deploy and maintain.

External services are used only where they provide functionality that does not need to be implemented as part of the static site itself.

---

## 5. Project Structure

The portfolio is intentionally organized as a lightweight static website.

My-Portfolio/
├── index.html
├── style.css
├── README.md
├── HARDENING.md
└── project assets and resume

The main page and styling are kept in `index.html` and `style.css`.
Project media, resume files, and supporting documentation are stored alongside the main site files.

---

## 6. Getting Started

### Prerequisites

A stranger only needs:

* Git
* A modern web browser

No database server or backend service is required to run the core portfolio locally.

### Clone the repository

```bash
git clone https://github.com/syeda-ajiya56/My-Portfolio.git
cd My-Portfolio
```

### Run locally

Because the project is a static website, it can be opened directly in a browser.

For a local development server, one simple option is:

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

The exact development server is not part of the application architecture; it is only used to serve the static files locally.

---

## 7. Usage

After opening the site, a visitor can:

1. Read the introduction.
2. Review the skills section.
3. Browse the featured projects.
4. Open available project demonstrations or repositories.
5. Review the resume.
6. Use the contact form.
7. Use the scheduling option when available.
8. Navigate the site on desktop or mobile.

The portfolio is designed so that a reviewer can understand the main information without needing to install the individual projects showcased on the site.

---

## 8. Production Hardening and Evaluation

The portfolio was reviewed and hardened as part of the development process.

The work included:

* Responsive behavior checks.
* Accessibility review.
* Performance improvements.
* SEO improvements.
* Project media optimization.
* Conversion of large GIF-based project media to more efficient video/poster assets where appropriate.
* Verification of the contact form.
* Verification of the production deployment.
* Addition of deployment analytics.
* Review of project links and portfolio content.

The detailed hardening record is maintained separately:

**[HARDENING.md](./HARDENING.md)**

### Lighthouse results

The portfolio reached the following recorded Lighthouse results during the hardening process:

* **Performance:** 49 → 83
* **Accessibility:** 100
* **SEO:** 92

These results reflect the recorded audit during the development/hardening process and can vary between runs because Lighthouse results depend on the testing environment and network conditions.

---

## 9. Limitations

The portfolio is intentionally a lightweight personal website, so it has several limitations.

### Static architecture

The core site does not use a database or application backend. This keeps deployment simple but limits functionality that would require persistent user data.

### External services

Some functionality depends on third-party services, including EmailJS, Calendly, and Vercel.

If an external service is unavailable or changes its configuration, the related functionality may be affected.

### Individual project deployment

Some projects showcased in the portfolio are not directly deployed as web applications because they depend on technologies such as desktop environments or SQL Server databases.

For those projects, the portfolio provides supporting information, media, and repository links instead of pretending that every project has a live web deployment.

### Analytics

Analytics depends on the deployment platform and its associated service. Analytics data is not part of the portfolio's core functionality.

---

## 10. AI Transparency

AI tools, including Claude and ChatGPT, were used as development and review partners during parts of the portfolio work.

AI assistance was used for tasks such as brainstorming, debugging support, documentation assistance, code-review discussion, and improving implementation ideas.

I remained responsible for the final implementation and personally checked the resulting website through local testing, production deployment checks, responsive testing, accessibility/performance review, and verification of the site's actual functionality.

The AI tools did not replace the testing and verification process.

---

## 11. Deployment

The portfolio is deployed as a static website using Vercel.

Production deployment allows the project to be accessed without installing the development environment.

**Live Portfolio:**
https://ajiya-portfolio-kappa-eight-35.vercel.app/

The source code is available publicly on GitHub:

https://github.com/syeda-ajiya56/My-Portfolio

---

## 12. Demo

**FL-09 Demo Video:**
*To be added after recording.*

The demo will show the live portfolio running end-to-end and will explain:

* The purpose of the portfolio.
* The main user journey.
* One important design decision.
* The production/hardening work.
* One current limitation.
* Where AI assistance was used during development.

---

## 13. Design Decision

One important design decision was to keep the portfolio as a lightweight static website rather than introducing a frontend framework or backend solely for the portfolio itself.

This keeps the site's deployment and maintenance requirements small while allowing it to focus on its main purpose: presenting my work clearly and providing visitors with direct access to projects, professional information, and contact options.

The decision also means that more complex functionality can remain inside the individual projects rather than making the portfolio itself unnecessarily complex.

---

## 14. Future Improvements

Possible future improvements include:

* Adding more detailed case studies for selected projects.
* Continuing to improve performance as the project media grows.
* Adding richer project filtering or categorization.
* Expanding accessibility testing as new content is added.
* Adding more measurable project outcomes to case studies.
* Continuing to improve the portfolio's presentation as new projects are completed.

---

## 15. Author

**Ajiya Shaukat**

Software Engineering Student & Full-Stack Developer

* GitHub: https://github.com/syeda-ajiya56
* LinkedIn: https://www.linkedin.com/in/ajiya-shaukat-8ab604348/
* Email: available through the portfolio contact section
* Scheduling: available through the portfolio

---

## FL-09 Submission Checklist

* [x] Project overview
* [x] Intended audience
* [x] Setup instructions
* [x] Usage examples
* [x] Architecture sketch
* [x] AI transparency statement
* [x] Deployment information
* [x] Limitations
* [ ] V2 evaluation results verified
* [ ] 3–5 minute live demo
* [ ] Demo video link added
* [ ] Posted to showcase thread
