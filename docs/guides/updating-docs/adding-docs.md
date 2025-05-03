# Adding a new documentation page

This is a guide for adding a page to the documentation site.

This guide shows how to use GitHub's web-based editor because its interface should be familiar to anyone who's used a web form and using it does not require installing any software.

## For close collaborators

You can use GitHub's web editor to add a new page of documentation to this site.

### Prerequisites

- You have a [GitHub](https://github.com/) account. [Sign up](https://github.com/signup) is free.
- You have been granted commit access to the [tucsonmesh-docs repository](https://github.com/tucsonmesh/tucsonmesh-docs) by someone in the Mesh admin group.
- You have some familiarity with the Markdown markup language. Reading about its [basic syntax](https://www.markdownguide.org/basic-syntax/) will probably be enough. Don't worry! Markdown was designed to be easily readable and you can probably figure out the syntax from what's already in the file.

### Make sure you're logged into your GitHub account

For the smoothest editing experience, make sure you're logged in to your GitHub account before you start editing pages.

Visit [https://github.com/login](https://github.com/login) in your preferred browser and complete the login flow.

### Navigate to the documentation repository on GitHub

The documentation is just a collection of text files. We use a version control system called [git](https://git-scm.com/) to manage edits and combine edits from multiple people. We use GitHub as the host for this version control system.

Navigate to [https://github.com/tucsonmesh/tucsonmesh-docs](https://github.com/tucsonmesh/tucsonmesh-docs) in your browser. This is where you can view and modify the documentation.

### Navigate to the folder where you want to add a page

The software we use to turn the text files into the documentation site requires that all the files live in the `docs` directory/folder of the repository, so start by clicking on that directory.

Use your browser to explore the folder structure under `docs` to find where you want to create your new documentation page.

Where you choose to create the file will determine its URL on the public site. For example, the current piece of documentation you're reading is at [https://tucsonmesh.github.io/tucsonmesh-docs/guides/updating-docs/adding-docs/](https://tucsonmesh.github.io/tucsonmesh-docs/guides/updating-docs/adding-docs/) that means this file lives in the [`docs/guides/updating-docs`](https://github.com/tucsonmesh/tucsonmesh-docs/tree/main/docs/guides/updating-docs) directory.

You can move this file later, but try to place the file in a directory alongside related documentation.

### Create the file content

In the directory view of the repository on GitHub, click the `Add File` button in the upper-right corner of the screen and click `Create new file` in the menu.

Type out your documentation in the large text area. You may want to turn on line wrapping by clicking on the `Line wrap mode` button in the upper-right corner and choosing `Soft wrap` in the menu.

You can check your Markdown formatting by clicking on the `Preview` tab.

### Save your changes

Once you're done, click the `Commit changes` button to the upper-right of the text editing area.

Enter a `Commit message`. There will be a default, but ideally you'll add something more descriptive. Additionally, you can write an `Extended description`. The description should describe the motivation for your changes rather than summarizing what you changed. Both of these won't be visible to readers of the documentation site, but are useful for other editors to review or understand changes.

Finally, click the `Commit changes` button.

### You're done!

Your changes have been saved, and in a few minutes, the public site will be rebuilt and your changes will be visible.

### Next: add the new documentation to the menu

You've added a page to the documentation site, but you need to also add it to the navigation menus. See [Updating the documentation menu](editing-menu.md) for instructions on how to do this.

## For others

We need to write step-by-step instructions about how people who are not close collaborators can submit updates to the documentation. Generally speaking, this documentation is hosted in a [GitHub repository](https://github.com/tucsonmesh/tucsonmesh-docs). You can [fork the repository](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo), commit the desired changes to your fork and send us a [pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request).
