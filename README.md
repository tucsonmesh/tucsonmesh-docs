# Tucson Mesh Technical Documentation

This is the technical documentation for [Tucson Mesh](https://www.tucsonmesh.net/), a low-cost, community-controlled wireless internet provider in Tucson, Arizona.

This documentation is written as [Markdown](https://en.wikipedia.org/wiki/Markdown) files that are turned into a website using [MKDocs](https://www.mkdocs.org/) with the [Material for MKDocs](https://squidfunk.github.io/mkdocs-material/) theme.

It originally started as a fork of [nycmeshnet/docs](https://github.com/nycmeshnet/docs), and draws inspiration from the organization of its successor, [wiki.nycmesh.net](https://wiki.nycmesh.net/).

## How do I make edits?

If the page you want to change already exists, the easiest way is actually do navigate to it on the [deployed website](https://tucsonmesh.github.io/tucsonmesh-docs) and click the edit button (piece of paper with a pencil) in the top right corner.

That will bring you to the corresponding source file in this repository where you can quickly edit and save ("commit") your changes. After this, the website will "rebuild" automatically publish your changes.

Below, we have more detailed instructions for people who want to be able to run the "build the website" steps on their local laptop and iterate more quickly on large numbers of edits.

## Preqrequisites

- Python 3.8+

## Installing MKDocs

### Python-based Installation Instructions

I recommend first installing [pipx](https://pipx.pypa.io/) which allows installing Python command-line utilities in isolated virtual environments.

Then, install MKDocs:

```
pipx install mkdocs
```

and the Material for MKDocs theme:

```
pipx inject mkdocs mkdocs-material
```

### DNF-based Installation Instructions

If you are on a dnf-based distribution (i.e. Fedora) and would like to leverage the version of mkdocs included with your package manager, the required dependencies can be installed with:

```bash
dnf install mkdocs mkdocs-material
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

