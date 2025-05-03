# Frequently asked questions

## How do I leave comments?

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

