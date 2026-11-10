# Static Site on AWS

Hosting a static website on AWS as a hands-on DevOps project.

The site is a single recipe page built with plain HTML and CSS. The interesting part
is everything around it: the AWS infrastructure that serves it and the process that
deploys it.

**Live site:** <!-- TODO: add URL once deployed -->

## Architecture

<!-- TODO: describe your setup once built, for example:
Browser → CloudFront (HTTPS, caching) → private S3 bucket (via Origin Access Control)
Route 53 for DNS, ACM for the TLS certificate.
-->

## Repository layout

```
site/          Everything that gets deployed (HTML, CSS, fonts, images)
  index.html
  404.html     Custom error page for missing URLs
CLAUDE.md      Project notes for AI-assisted work
```

## Deploying

<!-- TODO: document your deploy steps, for example:
aws s3 sync site/ s3://<bucket-name> --delete
aws cloudfront create-invalidation --distribution-id <id> --paths "/*"
-->

## Running locally

No build step is needed. Serve the `site/` folder with any static server:

```bash
python3 -m http.server --directory site
```

Then open http://localhost:8000.

## What I learned

<!-- TODO: notes on the AWS services, problems you hit and how you solved them -->

## Credits

- The website design comes from the Recipe page challenge by
  [Frontend Mentor](https://www.frontendmentor.io).
- Fonts: [Outfit](https://fonts.google.com/specimen/Outfit) and
  [Young Serif](https://fonts.google.com/specimen/Young+Serif), licensed under the
  SIL Open Font License (license files included in `site/assets/fonts/`).
