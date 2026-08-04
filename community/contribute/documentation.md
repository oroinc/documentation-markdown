<a id="documentation-standards"></a>

# Contribute to Documentation

You are welcome to contribute to the documentation.

The documentation source files are maintained in the <a href="https://github.com/oroinc/documentation" target="_blank">dedicated github repository</a>.

This guide explains the documentation contribution workflow. Detailed guidance on contributing to and writing documentation is available in the following files located in the root of the `documentation` directory of the repository:

* <a href="https://github.com/oroinc/documentation/blob/master/CONTRIBUTING.md" target="_blank">CONTRIBUTING.md</a> — Documentation repository structure, contribution workflow, file naming conventions, and documentation organization.
* <a href="https://github.com/oroinc/documentation/blob/master/STYLE-GUIDE.md" target="_blank">STYLE-GUIDE.md</a> — Writing style, terminology, UI formatting, screenshots, capitalization, links, and editorial conventions.
* <a href="https://github.com/oroinc/documentation/blob/master/RST-SYNTAX.md" target="_blank">RST-SYNTAX.md</a> — reStructuredText syntax, directives, metadata, images, tables, notes, references, and other markup used throughout the documentation.
* <a href="https://github.com/oroinc/documentation/blob/master/BUILD.md" target="_blank">BUILD.md</a> — Docker and local builds, multi-version and Markdown output, and a fast syntax check of individual files.

## Before You Begin

The use of the documentation is subject to the <a href="https://github.com/oroinc/documentation/blob/5.1/LICENSE" target="_blank">CC-BY-NC-SA 4.0</a> license.

Sign the <a href="https://www.oroinc.com/orocommerce/contributor-license-agreement" target="_blank">Contributor License Agreement</a> (CLA) before you submit a pull request. The CLA must be signed for any code or documentation changes to be accepted.

Before making changes, review the guidance in <a href="https://github.com/oroinc/documentation/blob/master/CONTRIBUTING.md" target="_blank">CONTRIBUTING.md</a>, <a href="https://github.com/oroinc/documentation/blob/master/STYLE-GUIDE.md" target="_blank">STYLE-GUIDE.md</a>, <a href="https://github.com/oroinc/documentation/blob/master/RST-SYNTAX.md" target="_blank">RST-SYNTAX.md</a>, and <a href="https://github.com/oroinc/documentation/blob/master/BUILD.md" target="_blank">BUILD.md</a>.

## Fork Documentation Project

If you are making a small change, use the **Edit this file** button in the GitHub UI. It creates a fork of the <a href="https://github.com/oroinc/documentation" target="_blank">Oro documentation</a> repository and lets you create and submit a pull request with your modifications once you are done editing.

For large volumes of updates, fixes, and enhancements, use the following process:

1. <a href="https://docs.github.com/en/get-started/quickstart/fork-a-repo" target="_blank">Fork</a> the documentation repository.
2. <a href="https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository" target="_blank">Clone</a> your forked repository.
3. Update your local copy of the documentation following the guidance in <a href="https://github.com/oroinc/documentation/blob/master/CONTRIBUTING.md" target="_blank">CONTRIBUTING.md</a>, <a href="https://github.com/oroinc/documentation/blob/master/STYLE-GUIDE.md" target="_blank">STYLE-GUIDE.md</a>, and <a href="https://github.com/oroinc/documentation/blob/master/RST-SYNTAX.md" target="_blank">RST-SYNTAX.md</a>.
4. Build and test the documentation before submitting a pull request to make sure you have not introduced any layout or formatting issues.
   - Set up a local build environment by installing <a href="https://www.docker.com/" target="_blank">Docker</a>.
   - Run the following command to generate the documentation in `./_build/html` and create a Docker image:
     ```bash
     docker bake --load
     ```

     #### HINT
     This command builds the branch you are working on, which is what you need to check your changes.

     See <a href="https://github.com/oroinc/documentation/blob/master/BUILD.md" target="_blank">BUILD.md</a> for local builds without Docker, a fast syntax check of individual files, and the options used to build the whole documentation website.

## Submit Documentation Updates

When your changes are ready, create a pull request in the <a href="https://github.com/oroinc/documentation" target="_blank">Oro documentation</a> repository with changes from your forked repository. See [Code Version Control](code-version-control.md#code-version-control) for more information on using the repository.

If your pull request contains more than one commit, keep the history linear and give each commit a clear, descriptive message that explains what it changes. Rebase your branch on the base branch instead of merging the base branch into it, and squash intermediate commits such as “fix” or “review comments” into the commit they belong to.

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
