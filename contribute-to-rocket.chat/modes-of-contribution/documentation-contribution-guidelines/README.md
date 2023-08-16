---
description: Here's everything you need to start contributing to Rocket.Chat documentation.
---

# Documentation Contribution Guidelines

Thank you for your interest in contributing to Rocket.Chat documentation. Here's a quick guide:

1. **Finding a Task**: Locate an issue you'd like to work on from our issues list for [user documentation](https://github.com/RocketChat/docs/issues) or [developer documentation](https://github.com/RocketChat/developer-docs/issues) and comment with your interest. We'll add an **In Progress** label.
2. **Using a Gitbook Workspace**: Set up a Gitbook workspace and follow these steps:
   * Fork the [user docs](https://github.com/RocketChat/docs) or [developers docs](https://github.com/RocketChat/developer-docs) repository.
   * [Create a space](https://docs.gitbook.com/getting-started/content-structure/what-is-a-space#create-a-spacehttps://docs.gitbook.com/getting-started/content-structure/what-is-a-space#create-a-space) on GitBook, and activate the [GitHub Integration](https://docs.gitbook.com/product-tour/git-sync) on your fork.
   * Make your changes on Gitbook.
   * Create a PR on GitHub after sync.
3. **Local Environment Setup**: Set up your local environment using this guide.
   * Install any code editor of your choice, [VSCode ](https://code.visualstudio.com/)is the recommended
   * Launch VSCode and install the [Auto-Open Markdown Preview](https://marketplace.visualstudio.com/items?itemName=hnw.vscode-auto-open-markdown-preview) and [markdownlint ](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)extensions. This will help with automatically formatting your changes and prompts for any errors.
   * Fork and clone the [user docs](https://github.com/RocketChat/docs) or [developers docs](https://github.com/RocketChat/developer-docs) repository
   * Open the project in VSCode and start making your changes
4. **Creating a New Pull Request (PR)**: PRs should follow the following naming convention:
   * When adding new documentation, add _New Documentation\*\*:\*\*_ before the title. E.g. `New Documentation: Authentication Guide`
   * When fixing documentation, add _Fix Documentation:_ before the title. E.g. `Fix Documentation: Authentication Guide`
   * When updating documentation, add _Update Documentation\*\*:\*\*_ before the title. E.g. `Update Documentation: Authentication Guide`
   * If your PR closes an issue, indicate so with "Closes #ISSUE\_NUMBER".
5. **Creating Drafts**: If you can't complete full documentation for a new feature, create a draft as a single file PR with the necessary information.
6. **Testing Changes**: You can test your changes:
   * Using Live Preview Locally: The [Auto-Open Markdown Preview](https://marketplace.visualstudio.com/items?itemName=hnw.vscode-auto-open-markdown-preview) installed on VSCode can help automatically preview directly in your editor.
   * Using GitBook: Simply fork our docs repository, [create a space](https://docs.gitbook.com/getting-started/content-structure/what-is-a-space#create-a-spacehttps://docs.gitbook.com/getting-started/content-structure/what-is-a-space#create-a-space) on GitBook, and activate the [GitHub Integration](https://docs.gitbook.com/integrations/git-sync) on your fork. This gives you a means of previewing your changes before submitting a PR.

{% hint style="info" %}
For further guidelines on contributing to Rocket.Chat documentation, visit [markdown-style-guide.md](markdown-style-guide.md "mention") and [documentation-template.md](documentation-template.md "mention")
{% endhint %}
