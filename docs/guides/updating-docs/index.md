# Updating this documentation

This documentation is written as [Markdown](https://en.wikipedia.org/wiki/Markdown) files that are turned into a website using [MKDocs](https://www.mkdocs.org/) with the [Material for MKDocs](https://squidfunk.github.io/mkdocs-material/) theme.

If you just want to make some changes, check out [Editing Tucson Mesh's technical documentation](editing-docs.md).

It's probably helpful to read the [Writing with Markdown](https://www.mkdocs.org/user-guide/writing-your-docs/#writing-with-markdown) section of the [MKDocs User Guide](https://www.mkdocs.org/user-guide/).

You'll have the best experience editing this documentation if you have an understanding of the difference between absolute and relative paths and URLs. [Creating links](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content/Creating_links) from the Mozilla Developer Network [Structuring content with HTML](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content) tutorial has a good description of these concepts.

## Frequently asked questions

### How do I leave comments?

One of the downsides of moving away from using Google Docs is that we lose its nice system for highlighting text that might be unclear or incorrect.

In this new system, the best bet is to just put the comment in the content and highlight it with a special box, called an "admonition".

It's probably most clear to include these at the beginning of the section that reflects unclear or outdated content.

For example this Markdown:

```
!!! info "How can this documentation be improved?"

    - Suggestion 1
    - Suggestion 2
```

Generates this message:

!!! info "How can this documentation be improved?"

    - Suggestion 1
    - Suggestion 2

You can change the icon and formatting by changing the word after the `!!!`.

For example, this Markdown:

```
!!! warning "Content may be out of date"

    We need to check if it's still preferable to use this method.
```

Generates this message:

!!! warning "Content may be out of date"

    We need to check if it's still preferable to use this method.

You can learn more about this feature at [Admonitions](https://squidfunk.github.io/mkdocs-material/reference/admonitions/).

