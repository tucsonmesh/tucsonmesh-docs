# Updating the documentation menu

This is a guide for editing the navigation menu that currently appears on the left-hand side of the documentation site. You can use it to add a new documentation page you've created to the navigation menu.

This guide shows how to use GitHub's web-based editor because its interface should be familiar to anyone who's used a web form and using it does not require installing any software.

## For close collaborators

You can use GitHub's web editor to update the documentation site menu.

### Prerequisites

- You have a [GitHub](https://github.com/) account. [Sign up](https://github.com/signup) is free.
- You have been granted commit access to the [tucsonmesh-docs repository](https://github.com/tucsonmesh/tucsonmesh-docs) by someone in the Mesh admin group.
- You have some understanding of *absolute* and *relative* *paths* in a computer's file system or URLS. [Creating links](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content/Creating_links) from the Mozilla Developer Network [Structuring content with HTML](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content) tutorial has a good description of these concepts.

In addition, it might be helpful if

- You have a basic understanding of the concept of structured data text files. The menu configuration is in a [YAML](https://en.wikipedia.org/wiki/YAML) file. If you've ever worked with JSON, or even CSV files, you probably have enough familiarity to be fine. The bottom line is that special characters and indentation matter!
- You've glanced at the [Configure Pages and Navigation](https://www.mkdocs.org/user-guide/writing-your-docs/#configure-pages-and-navigation) section of the MKDocs user guide. Recall that MKDocs is the open source software we use to convert the Markdown-formatted text files you edit into the documentation website.

### Make a note of the relative path of the file for the documentation page

In order to add a page to the navigation menu, you'll need to know its *path* relative to the *docs* directory.

This is different than its path in the URL of the documentation site, but knowing that can help.

For example, if you wanted to add a navigation menu item for the file that lives at `docs/guides/updating-docs/adding-docs.md`, then the path you'll need to remember for later is `guides/updating-docs/adding-docs.md`. That is, omit the leading `docs/`.

The Markdown file is published at [https://tucsonmesh.github.io/tucsonmesh-docs/guides/updating-docs/adding-docs/](https://tucsonmesh.github.io/tucsonmesh-docs/guides/updating-docs/adding-docs/) and you can also see how the path you need to remember, `guides/updating-docs/adding-docs.md` is reflected in the URL path.


### Make sure you're logged into your GitHub account

For the smoothest editing experience, make sure you're logged in to your GitHub account before you start editing pages.

Visit [https://github.com/login](https://github.com/login) in your preferred browser and complete the login flow.

### Open the configuration file in the GitHub editor

Navigate to the [tucsonmesh-docs repository](https://github.com/tucsonmesh/tucsonmesh-docs) repository.

In the file listing, click on the entry for the configuration file: [`mkdocs.yml`](https://github.com/tucsonmesh/tucsonmesh-docs/blob/main/mkdocs.yml).

Click on the `Edit this file` icon in the upper-right corner of the area that shows the file contents. It looks like a pencil.

### Add or move the navigation menu entry

The configuration file `mkdocs.yml` includes a number of settings beyond just site navigation. You want to look for the `nav` key in the file.

You should see how the entries under the `nav` key correspond to the structure of the menu on the published site.

Menu items are denoted with a `-`. The order of menu items in the configuration, from top to bottom, determines the order they show up in the menu of the published site.

Levels of the menu are defined by indenting two spaces further to the right than the menu parent item.

Add the entry for the path you identified earlier to the desired section of the menu configuration, or cut it from one section and paste it into another.

For example, if I wanted to add the file `guides/updating-docs/adding-docs.md` to the `Updating this documentation` section of the menu, I would insert it like this:

```
nav:
  - Home: index.md
  - Guides:
    - guides/installation/index.md
    - guides/site-survey/index.md
    - Router Configuration:
      - guides/configuring-routers/index.md
      - guides/configuring-routers/litebeam.md
      - guides/configuring-routers/omnitik.md
      - guides/configuring-routers/sxtsq.md
      - guides/configuring-routers/archer-a6.md
    - guides/ladder-safety.md
    - guides/routeros-tips.md
    - Updating this documentation:
      - guides/updating-docs/index.md
      - guides/updating-docs/editing-docs.md
      - guides/updating-docs/adding-docs.md
      - guides/updating-docs/faq.md
```

Note that adding an entry for the file path will automatically show that file's title in the published menu.

If you want to make the entry different than the title, you can prepend the path with the alternate label and a colon. For example:

```
nav:
  - Home: index.md
  - Guides:
    - guides/installation/index.md
    - guides/site-survey/index.md
    - Router Configuration:
      - guides/configuring-routers/index.md
      - guides/configuring-routers/litebeam.md
      - guides/configuring-routers/omnitik.md
      - guides/configuring-routers/sxtsq.md
      - guides/configuring-routers/archer-a6.md
    - guides/ladder-safety.md
    - guides/routeros-tips.md
    - Updating this documentation:
      - guides/updating-docs/index.md
      - guides/updating-docs/editing-docs.md
      - Add a page: guides/updating-docs/adding-docs.md
      - guides/updating-docs/faq.md
```

### Save your changes

Once you're done, click the `Commit changes` button to the upper-right of the text editing area.

Enter a `Commit message`. There will be a default, but ideally you'll add something more descriptive. Additionally, you can write an `Extended description`. The description should describe the motivation for your changes rather than summarizing what you changed. Both of these won't be visible to readers of the documentation site, but are useful for other editors to review or understand changes.

Finally, click the `Commit changes` button.

### You're done!

Your changes have been saved, and in a few minutes, the public site will be rebuilt and your changes will be visible.


## For others

We need to write step-by-step instructions about how people who are not close collaborators can submit updates to the documentation. Generally speaking, this documentation is hosted in a [GitHub repository](https://github.com/tucsonmesh/tucsonmesh-docs). You can [fork the repository](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo), commit the desired changes to your fork and send us a [pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request).
