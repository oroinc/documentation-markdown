<a id="frontend-pnpm-package-manager"></a>

# PNPM Package Manager

PNPM is a faster and more reliable alternative to NPM, designed to improve build performance and prevent dependency mismatch issues.

#### NOTE
To enforce the use of PNPM across the OroCommerce application, the package.json file already includes a preinstall script to enforce the use of PNPM:

```json
"scripts": {
  "preinstall": "npx only-allow pnpm"
}
```

## Getting Started

To begin using PNPM, follow <a href="https://pnpm.io/installation" target="_blank">the official PNPM installation guide</a>.

For most JavaScript developers, the quickest setup method is to run the following command:

```bash
npm install -g pnpm
```

## Working with PNPM

Install dependencies using PNPM

```bash
pnpm install
```

#### NOTE
If you previously used NPM, make sure to delete the existing node_modules directory from the root of your application.

#### IMPORTANT
PNPM creates a **non-flat** (isolated) node_modules structure using symlinks, exposing only explicitly declared dependencies. This improves build speed and avoids bugs caused by undeclared packages.

For example, if package **A** imports package **B**: import something from ‘B’;, but **B** is not listed in **A**’s dependencies in package.json, the code will fail, even if **B** is present in the repo(node_modules folder). The package *B* must be explicitly declared in **A**’s package.json:

```json
{
    "name": "A",
    "dependencies": {"B": "1.0.0"}
}
```

Add a new package

```bash
pnpm add some-new-package
```

## Common Issues When Migrating from NPM to PNPM

### Lockfile Conflicts

When confusion or errors related to package-lock.json and pnpm-lock.yaml.

Clean the project and reinstall.

```bash
rm package-lock.json
rm -rf node_modules
pnpm install
```

### Missing Dependencies Due to Hoisting Differences

When modules that previously worked under NPM now result in module not found errors, add missing dependencies explicitly:

```bash
pnpm add <package-name>
```

### Local Package Changes Not Reflected

When updating to workspace packages are not recognized in other parts of the monorepo, run the following command:

```bash
pnpm install
pnpm -r build
```

### PhpStorm Saved Script Setup Stop Working

When predefined scripts in PhpStorm (used for building front-end assets) no longer work after switching to PNPM, update or recreate your Run Configuration to use PNPM as shown bellow:

![PNPM config for PHPStorm](img/frontend/pnpm-package-manager/phpstorm-pnpm-config.png)
<!-- Frontend -->
