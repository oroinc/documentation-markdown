<a id="documentation-standards"></a>

# Contribute to Documentation

Documentation source files are maintained in the <a href="https://github.com/oroinc/documentation" target="_blank">dedicated github repository</a>.

You are welcome to contribute to the documentation.

This guide explains the documentation contribution workflow. Detailed guidance on contributing to and writing documentation is available in the following files located in the root of the `documentation` directory of the repository:

* <a href="https://github.com/oroinc/documentation/blob/master/CONTRIBUTING.md" target="_blank">CONTRIBUTING.md</a> — Documentation repository structure, contribution workflow, file naming conventions, and documentation organization.
* <a href="https://github.com/oroinc/documentation/blob/master/STYLE-GUIDE.md" target="_blank">STYLE-GUIDE.md</a> — Writing style, terminology, UI formatting, screenshots, capitalization, links, and editorial conventions.
* <a href="https://github.com/oroinc/documentation/blob/master/RST-SYNTAX.md" target="_blank">RST-SYNTAX.md</a> — reStructuredText syntax, directives, metadata, images, tables, notes, references, and other markup used throughout the documentation.

## Before You Begin

The use of the documentation is subject to the <a href="https://github.com/oroinc/documentation/blob/7.0/LICENSE" target="_blank">CC-BY-NC-SA 4.0</a> license.

Before submitting your documentation changes in a pull request, please sign our <a href="https://oroinc.com/b2b-ecommerce/contributor-license-agreement/" target="_blank">Contributor License Agreement</a> (CLA). The CLA must be signed for any code or documentation changes to be accepted.

Before making changes, review the guidance in <a href="https://github.com/oroinc/documentation/blob/master/CONTRIBUTING.md" target="_blank">CONTRIBUTING.md</a>, <a href="https://github.com/oroinc/documentation/blob/master/STYLE-GUIDE.md" target="_blank">STYLE-GUIDE.md</a>, and <a href="https://github.com/oroinc/documentation/blob/master/RST-SYNTAX.md" target="_blank">RST-SYNTAX.md</a>.

## Fork Documentation Project

If you are just making a small change, you can use the **Edit this file** button directly in the GitHub UI. It will automatically create a fork of our <a href="https://github.com/oroinc/documentation" target="_blank">Oro documentation</a> repository and allow for the creation and submission of a new pull request with your modifications once you are done editing.

For large volumes of updates, fixes, and enhancements, please use the following process:

1. <a href="https://docs.github.com/en/get-started/quickstart/fork-a-repo" target="_blank">Fork</a> the documentation repository.
2. <a href="https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository" target="_blank">Clone</a> your forked repository.
3. Update your local copy of the documentation following the guidance in <a href="https://github.com/oroinc/documentation/blob/master/CONTRIBUTING.md" target="_blank">CONTRIBUTING.md</a>, <a href="https://github.com/oroinc/documentation/blob/master/STYLE-GUIDE.md" target="_blank">STYLE-GUIDE.md</a>, and <a href="https://github.com/oroinc/documentation/blob/master/RST-SYNTAX.md" target="_blank">RST-SYNTAX.md</a>.
4. Build and test the documentation before submitting a pull request to be sure you have not accidentally introduced any layout or formatting issues.
   - Set up a local build environment by installing <a href="https://www.docker.com/" target="_blank">Docker</a>.
   - Run the following command to generate the documentation in `./_build/html` and create a Docker image:
     ```bash
     docker bake --load
     ```

     #### HINT
     By default, this command builds only the current branch. To build documentation as it appears on the website, including version selection in the index, set the appropriate variables `MAINTENANCE_BRANCHES=5.1|6.0|6.1|7.0|master`. To generate the documentation in **Markdown** format instead of HTML, set the `BUILDER="markdown"` variable.

## Submit Documentation Updates

Once you are ready, create a pull request in the <a href="https://github.com/oroinc/documentation" target="_blank">Oro documentation</a> repository with changes from your forked repository. See [Code Version Control](code-version-control.md#code-version-control) for more information on using the repository.

After documentation review, your changes will be merged into the Oro documentation and published on the documentation website.

#### BUSINESS TIP
## Business Tip

Looking for more information on the difference between B2C and <a href="https://oroinc.com/b2b-ecommerce/what-is-b2b-ecommerce/" target="_blank">B2B eCommerce</a>? Our in-depth guide covers this and more.

**See Also**

* [Version Control](code-version-control.md#code-version-control)
* [Code Style](code-style.md#doc-community-code-style)
* [Set Up a Development Environment](../../backend/setup/dev-environment/index.md#doc-dev-env-best-practices)
* [Contribute to Translations](code-ui-translations.md#doc-community-ui-translations)
* [Report an Issue](../report-issues/code.md#doc-community-issue-report)
* [Report a Security Issue](../report-issues/security.md#reporting-security-issues)
* [Contact Community](../index.md#doc-community-contact-community)
* [Release Process](../release-process.md#doc-community-release)

<!-- Frontend -->
