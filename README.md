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

## Publishing the site to GitHub pages

```
mkdocs gh-deploy --force
```

