# Static Site on AWS

A DevOps learning project: host a static website on AWS. The website itself is a
finished recipe page (HTML and CSS only). The focus of this project is the
hosting, infrastructure and deployment around it.

Repo: https://github.com/Brianasingwire/simple-omelette-recipe

## Goals

- Host the site on AWS. <!-- TODO: e.g. private S3 bucket + CloudFront (OAC), custom domain via Route 53, HTTPS via ACM -->
- Learn the AWS services involved by setting them up hands-on.
- <!-- TODO: add your own goals, e.g. infrastructure as code (Terraform/CloudFormation), CI/CD with GitHub Actions, cost monitoring -->

## Project structure

```
site/              Deploy root: only these files are served
  index.html       The recipe page
  404.html         Custom error page
  css/styles.css   Single stylesheet for both pages
  assets/          Fonts (self-hosted, with their OFL license files) and images
README.md          Project overview, architecture, deploy steps, credits
```

## Conventions

- **No build step, no JavaScript.** The site is plain HTML and CSS; deploy `site/` as is.
- **Deploy the contents of `site/`** to the root of the bucket/origin, so `index.html` is served at `/`.
- **Paths:** `index.html` uses relative paths. `404.html` uses root-absolute paths
  (`/css/styles.css`) because it can be served at any missing URL. Keep it that way.
- **Error pages:** 403 and 404 responses should serve `/404.html` with a **404** status,
  not a redirect to `index.html` (this is not a single-page app).
- **Styles:** colors and fonts are CSS custom properties at the top of `styles.css`.
  Layout is mobile-first with one breakpoint at `48rem`.
- **File names are lowercase.** S3 keys are case-sensitive, so keep references matching exactly.
- Keep anything that should not be public (design files, notes, IaC, credentials) outside `site/`.

## Working with Claude

- Brian is doing the AWS hosting hands-on to learn it. For hosting and infrastructure,
  explain concepts, review configs and help debug rather than doing it end to end,
  unless asked.
- Never commit AWS credentials, access keys or `.tfstate` files.

## Credits

The recipe page design is a [Frontend Mentor](https://www.frontendmentor.io) challenge.
