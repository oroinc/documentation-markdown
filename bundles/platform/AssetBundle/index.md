<a id="bundle-docs-platform-asset-bundle"></a>

# OroAssetBundle

<a href="https://github.com/oroinc/platform/tree/master/src/Oro/Bundle/AssetBundle" target="_blank">OroAssetBundle</a> adds the possibility to install project assets using webpack.

## Architecture

Under the hood oro:assets:build command runs webpack to build assets.

The application contains webpack.config.js file that generates webpack configuration using webpack-config-builder.

Webpack *entry points* with a list of files are loaded from assets.yml files from all enabled Symfony bundles according to the bundles’ load priority.

To see the list of loaded bundles ordered by the priority, run:

```bash
php bin/console debug:container --parameter=kernel.bundles --format=json
```

#### NOTE
Entry point is a group of assets that are loaded together; usually they are merged into a single file.

## OroAssetBundle in Use

### Build Assets

First, run the `php bin/console assets:install --symlink` command  to symlink all assets’ source files to public/bundles/ directory.

Next, run the [php bin/console oro:assets:build](commands.md#bundle-docs-platform-asset-bundle-commands) command to build assets with the webpack. During the first run, it installs npm dependencies required for the build.

<a id="bundle-docs-platform-asset-bundle-load-css-from-bundle"></a>

### Load SCSS or CSS Files from the Bundle

Create an assets.yml file that contains an entry point list with the files to load.

```yaml
css:                                                    # Entry point name.
    inputs:                                             # List of files to load for `css` entry point
        - 'bundles/app/css/scss/main.scss'
    # You do not need to provide output for this entry point, it is already defined in
    # vendor/oro/platform/src/Oro/Bundle/UIBundle/Resources/config/oro/assets.yml
checkout:                                               # Another entry point name
    inputs:                                             # List of files to load for `checkout` entry point
        - 'bundles/app/scss/checkout_page_styles.scss'
    auto_rtl_inputs:                                    # List of wildcard file masks for inputs that has to be processed with RTL plugin
        - 'bundles/app/**'
    output: 'css/checkout-styles.css'                   # Output file path inside public/ directory for the `checkout` entry point
```

#### Location of assets.yml

| Management Console   | [BUNDLE_NAME]/Resources/config/oro/assets.yml                        |
|----------------------|----------------------------------------------------------------------|
| Storefront           | [BUNDLE_NAME]/Resources/views/layouts/[THEME_NAME]/config/assets.yml |

#### Default Entry Points and Output File Names

| Location           | Entry Point Name   | Output File                        |
|--------------------|--------------------|------------------------------------|
| Management Console | css                | build/css/oro/oro.css              |
| Storefront         | styles             | layout/[THEME_NAME]/css/styles.css |

#### NOTE
SCSS is the recommended format, CSS format is deprecated by sass-loader npm module.

#### Twig Functions

- `oro_external_link` — Returns a link to an external asset resource stored in the “oro_asset.external_resources” configuration. For more details, see: [Subresource Integrity](https://developer.mozilla.org/en-US/docs/Web/Security/Subresource_Integrity).

**Example:**

```twig
<script async src="{{ oro_external_link('oro_google_analytics') }}"></script>
```

Expected output:

```html
<script async src="https://www.google-analytics.com/analytics.js" rel="dns-prefetch">
```

- `oro_integrity` — provides Subresource Integrity hash for local asset resources.

**Example:**

```twig
<script src="{{ '/build/default/app.js' }}" {{ oro_integrity('/build/default/app.js') }}></script>
```

Expected output:

```html
<script src="/build/default/app.js?v=e61610e4" integrity="sha384-DAILU17u6emSxfVg8atEESVcx0aMd5gHIbhmP9vx2BlXfdWSaQeRrRdVoXhnOwAQ" crossorigin="anonymous"></script>
```

### Load JS modules from the Bundle

JS modules are defined within jsmodules.yml configuration files.

#### Location of jsmodules.yml

| Management Console   | [BUNDLE_NAME]/Resources/config/oro/jsmodules.yml                        |
|----------------------|-------------------------------------------------------------------------|
| Storefront           | [BUNDLE_NAME]/Resources/views/layouts/[THEME_NAME]/config/jsmodules.yml |

Detailed information about JS modules configuration is available in the [JS Modules](../../../backend/configuration/yaml/jsmodules.md#reference-format-jsmodules) topic.

## Configuration Reference

AssetBundle defines the configuration for NodeJs and PNPM executable.

All these options are configured under the oro_asset key in your application configuration.

```yaml
# displays the default config values defined by Oro
 php bin/console config:dump-reference oro_asset
# displays the actual config values used by your application
 php bin/console debug:config oro_asset
```

### Configuration

### nodejs_path

**type: \`string\` required, default: found dynamically**

Path to NodeJs executable.

### pnpm_path

**type: \`string\` required, default: found dynamically**

Path to PNPM executable.

### build_timeout

**type: \`integer\` required, default: \`null\`**

Assets build timeout in seconds, null to disable the timeout.

### pnpm_install_timeout

**type: \`integer\` required, default: \`null\`**

PNPM installation timeout in seconds, null to disable the timeout.

## Troubleshooting

**Error: Node Sass does not yet support your current environment**

After the update of NodeJs you might experience an error because node modules were built on the old NodeJs version that is not compatible with the new one.

To fix the error, remove the existing node modules and re-build the assets:

```none
rm -rf ./node_modules
php bin/console cache:clear
php bin/console oro:assets:build
```

**JS engine not found**

Appears when configuration in the cache is broken.

To fix the error, remove an application cache and warm it up:

```none
rm -rf var/cache/*
php bin/console cache:warmup
```

**PNPM not found**

Appears after migration to PNPM.

To fix the error, install pnpm, remove the existing node modules and re-build the assets:

```none
npm install -g pnpm
rm -rf ./node_modules
php bin/console cache:clear
php bin/console oro:assets:build
```

**Error: “output” for “assets” group in theme “oro” is not defined**

Please follow <a href="https://github.com/oroinc/platform/blob/master/CHANGELOG.md#assetbundle-1" target="_blank">upgrade documentation</a> to update assets.yml files according to new requirements.

**ERROR in Entry module not found: Error: Can’t resolve ‘./src’**

Make sure the `webpack.config.js` file exists in the project root, and the command has permissions to read it.

#### BUSINESS TIP
## Business Tip

B2B marketplaces are the rising trend in eCommerce. Discover the benefits of a <a href="https://oroinc.com/oromarketplace/b2b-marketplace/" target="_blank">B2B marketplace</a>, and what marketplace features you need to succeed.

<!-- Frontend -->
