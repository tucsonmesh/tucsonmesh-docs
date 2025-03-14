# Tucson Mesh Technical Documentation

This is the technical documentation for [Tucson Mesh](https://www.tucsonmesh.net/), a low-cost, community-controlled wireless internet provider in Tucson, Arizona.

This documentation is written as [Markdown](https://en.wikipedia.org/wiki/Markdown) files that are turned into a website using [MKDocs](https://www.mkdocs.org/) with the [Material for MKDocs](https://squidfunk.github.io/mkdocs-material/) theme.

It originally started as a fork of [nycmeshnet/docs](https://github.com/nycmeshnet/docs), and draws inspiration from the organization of its successor, [wiki.nycmesh.net](https://wiki.nycmesh.net/).

## Preqrequisites

- Python 3.8+

## Installing MKDocs

I recommend first installing [pipx](https://pipx.pypa.io/) which allows installing Python command-line utilities in isolated virtual environments.

Then, install MKDocs:

```
pipx install mkdocs
```

and the Material for MKDocs theme:

```
pipx inject mkdocs mkdocs-material
```

## Previewing the site locally

If you're adding or editing Markdown files locally, you can run a local webserver to see your changes:

```
mkdocs serve
```

## Publishing the site to GitHub pages

There is a GitHub action configured in `.github/workflows/ci.yml` that publishes this site to GitHub Pages every time someone pushes to the `main` branch of this repo. It's based on this [recipe](https://squidfunk.github.io/mkdocs-material/publishing-your-site/#with-github-actions) from the Material for MKDocs documentation.

However, if you want to manually publish this site from your computer, you can run:

```
mkdocs gh-deploy --force
```

