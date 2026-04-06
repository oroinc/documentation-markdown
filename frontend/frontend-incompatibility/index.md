<!-- meta: description = Overview of known frontend incompatibilities in OroCommerce 7.0, including module migrations, native promises, scheduler usage, and validation rules, with guidance for developers on how to update their projects. -->

# Frontend Incompatibilities in 7.0

As part of the OroCommerce v7.0 LTS release, several frontend areas introduce
breaking or incompatible changes that may affect existing customizations.
This document provides an overview of these incompatibilities, explains why they occur,
and offers migration examples to help developers update their projects smoothly.

#### KNOWN INCOMPATIBILITIES
# Known Incompatibilities

- Variations in migration from **CommonJS** and **AMD** modules to modern **ES Modules (ESM)**
- Using native promises instead of `jQuery deferred`
- Using <a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/scheduler" target="_blank">Window: scheduler property</a>
- Registering validation rules for `jquery.validate`

<h2>Table of Contents</h2>

* [Migrating AMD/CJS to ES Modules](migrating-modules.md)
* [Using Native Promises Instead of jQuery Deferred](promises.md)

<!-- Frontend -->
