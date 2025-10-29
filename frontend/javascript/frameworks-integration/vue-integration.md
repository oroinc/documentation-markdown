<a id="dev-doc-vue-integration"></a>

# Integrate Vue 3

Make sure that you place all JS modules in the bundle’s public folder. If the bundle does not exist, create one following the instruction in the [Create a Bundle](../../../backend/extension/create-bundle.md#dev-cookbook-framework-how-to-create-new-bundle) topic.

Keep in mind that if you create a new bundle or fail to create symlinks when installing the application, you need to run the following command `bin/console assets:install --symlink`. For more information, please see [OroAssetBundle](../../../bundles/platform/AssetBundle/index.md#bundle-docs-platform-asset-bundle) documentation.

## Declarative Rendering

The example below illustrates creating a simple component, such as the one shown in the screenshot, using the standard Vue 3 approach.

![Vue demo](img/frontend/frontend-architecture/frameworks/vue-demo.png)
1. Install dependencies. Navigate to the root folder and modify the `composer.json` (or `dev.json` if you use the developer mode) file with the code below. After updating the composer config file, execute the `composer install` command.
   ```json
   "extra": {
       "npm": {
           "vue": "^3.2.20"
       }
   }
   ```

   #### NOTE
   To learn how to add dependencies to Composer, see [Managing NPM dependencies with Composer](../composer-js-dependencies.md#dev-doc-frontend-composer-js-dependencies).
2. Create a template for the Vue component.
   *src/{YourBundleName}/Resources/public/js/vue/App.html*
   ```none
   <template v-if="editMode">
       <form class="grid">
           <div class="grid__row">
               <label for="name">Title</label>
               <input type="text" id="name" class="input" name="title" v-model="title">
           </div>
           <div class="grid__row">
               <label for="content">Content</label>
               <textarea class="input" id="content" name="content" v-model="content"></textarea>
           </div>
           <div class="grid__row">
               <button type="submit" class="btn btn-primary" @click.prevent="exitEditMode">Update</button>
           </div>
       </form>
   </template>

   <template v-else>
       <h1>{{ title }}</h1>
       <p>{{ content }}</p>

       <button class="btn edit-mode" @click.prevent="enterEditMode">Edit</button>
   </template>
   ```

   #### IMPORTANT
   In all code examples, the bundle’s name is set to `AcmeBundle`. When copying, remember to correct the name of the bundle in the paths according to your bundle.
3. Create a Vue component and copy the code below:
   *src/{YourBundleName}/Resources/public/js/vue/App.js*
   ```javascript
   import template from 'text-loader!./App.html';

   const App = {
       props: {
           initialTitle: {
               type: String,
               required: true
           },
           initialContent: {
               type: String,
               required: true
           }
       },

       template,

       data() {
           return {
               title: this.initialTitle,
               content: this.initialContent,
               editMode: false
           }
       },

       methods: {
           enterEditMode() {
               this.editMode = true;
           },

           exitEditMode() {
               this.editMode = false;
           }
       }
   }

   export default App;
   ```
4. To provide a runtime rendering template, create an alias for the Vue import. Since Vue is not the base framework for Oro, enable Page Component to start the Vue application, which will ensure proper integration into the Oro application lifecycle. Next, add the path for page component to `dynamic-imports:`, create a file, and insert the code below:
   *src/{YourBundleName}/Resources/views/layouts/{theme}/config/jsmodules.yml*
   ```yaml
   aliases:
       vue: vue/dist/vue.esm-bundler
   app-modules:
       - oroui/js/app/modules/vue-module
   dynamic-imports:
       acmevueapp:
           - oroui/js/app/components/vue-app-component
           - acmevueapp/js/vue-app/App
   ```
5. To build the application after changes, run the `pnpm run build` command. To rebuild the application automatically, run the `pnpm run watch` command.
6. In the Twig template, define where our Vue app will be displayed with a specific Page component using the `data-page-component-vue-app` shortcut. Copy and paste the code below:
   *src/{YourBundleName}/Resources/views/layout.html.twig*
   ```html+jinja
   {% block _vue_app_block_widget %}
       {% set attr = layout_attr_defaults(attr, {
           'data-page-component-vue-app': {
               vueApp: 'acmevueapp/js/vue-app/App',
               initialTitle: 'Vue demo',
               initialContent: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.'
           }
       }) %}

       <div {{ block('block_attributes') }}>
           {{ block_widget(block) }}
       </div>
   {% endblock %}
   ```
7. Register your new widget and append it to the page container in layout. Create a file for this. For more information on the layout update, see the [Layout](../../storefront/layouts/index.md#dev-doc-frontend-layouts-layout) topic.
   *src/{YourBundleName}/Resources/views/layouts/{theme}/layout.yml*
   ```yaml
   layout:
       actions:
           - '@setBlockTheme':
                 themes: 'layout.html.twig'
        
           - '@add':
                 id: vue_app_block
                 parentId: page_container
                 prepend: true
                 blockType: block
   ```

## Single File Components

Vue makes it possible to use one file for the component. For more information, see the official <a href="https://v3.vuejs.org/guide/single-file-component.html#introduction" target="_blank">Single File Components</a> documentation.

The webpack config does not support the `vue-loader` out-of-the-box. You need to modify the `webpack.config.js` file at the root of your application.

The example below implements the same functionality discussed above but uses the Single File Component in Vue3.

![Vue SFC demo](img/frontend/frontend-architecture/frameworks/vue-sfc-demo.png)
1. Install the `vue-loader` by running the command `pnpm install vue-loader@next -D`.
2. Open your `webpack.config.js` and replace the code with the one below:
   ```javascript
   const { VueLoaderPlugin } = require('vue-loader');
   const OroConfig = require('@oroinc/oro-webpack-config-builder');

   OroConfig
       .enableLayoutThemes()
       .setPublicPath('public/')
       .setCachePath('var/cache');

   module.exports = () => {
       const webpackConfigs = OroConfig.getWebpackConfig()();

       webpackConfigs.forEach(webpackConfig => {
           webpackConfig.module.rules = [
               {
                   test: /\.vue$/,
                   loader: 'vue-loader'
               },
               ...webpackConfig.module.rules
           ];

           webpackConfig.plugins = [
               ...webpackConfig.plugins,
               new VueLoaderPlugin()
           ];
       });

       return webpackConfigs;
   }
   ```

1. Create a Vue component and copy the code below:
   *src/{YourBundleName}/Resources/public/js/vue/App.vue*
   ```none
   <template>
       <template v-if="editMode">
           <form class="grid">
               <div class="grid__row">
                   <label for="name">Title</label>
                   <input type="text" id="name" class="input" name="title" v-model="title">
               </div>
               <div class="grid__row">
                   <label for="content">Content</label>
                   <textarea class="input" id="content" name="content" v-model="content"></textarea>
               </div>
               <div class="grid__row">
                   <button type="submit" class="btn btn-primary" @click.prevent="exitEditMode">Update</button>
               </div>
           </form>
       </template>

       <template v-else>
           <h1>{{ title }}</h1>
           <p>{{ content }}</p>

           <button class="btn edit-mode" @click.prevent="enterEditMode">Edit</button>
       </template>
   </template>

   <script>
   export default {
       props: {
           initialTitle: {
               type: String,
               required: true
           },
           initialContent: {
               type: String,
               required: true
           }
       },

       data() {
           return {
               title: this.initialTitle,
               content: this.initialContent,
               editMode: false
           }
       },

       methods: {
           enterEditMode() {
               this.editMode = true;
           },

           exitEditMode() {
               this.editMode = false;
           }
       }
   }
   </script>
   ```
2. To provide a runtime rendering template, create an alias for the Vue import. Since Vue is not the base framework for Oro, enable Page Component to start the Vue application, which will ensure proper integration into the Oro application lifecycle. Next, add the path for page component to `dynamic-imports:`, create a file, and insert the code below:
   *src/{YourBundleName}/Resources/views/layouts/{theme}/config/jsmodules.yml*
   ```none
   app-modules:
       - oroui/js/app/modules/vue-module
   dynamic-imports:
       acmevuesfcapp:
           - oroui/js/app/components/vue-app-component
           - acmevuesfcapp/js/vue-app/App.vue
   ```
3. To build the application after changes, run the `pnpm run build` command.  To rebuild the application automatically, run the `pnpm run watch` command.
4. Once the page component with Vue instance is created, declare it in the template of the required page. Copy and paste the code below:
   *src/{YourBundleName}/Resources/views/layout.html.twig*
   ```html+jinja
   {% block _vue_sfc_app_block_widget %}
       {% set attr = layout_attr_defaults(attr, {
           'data-page-component-vue-app': {
               vueApp: 'acmevuesfcapp/js/vue-app/App.vue',
               initialTitle: 'Vue SFC demo',
               initialContent: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.'
           }
       }) %}

       <div {{ block('block_attributes') }}>
           {{ block_widget(block) }}
       </div>
   {% endblock %}
   ```
5. Register your new widget and append it to the page container in the layout. Create a file for this. For more information on the layout update, see the [Layout](../../storefront/layouts/index.md#dev-doc-frontend-layouts-layout) topic.
   *src/{YourBundleName}/Resources/views/layouts/{theme}/layout.yml*
   ```yaml
   layout:
       actions:
           - '@setBlockTheme':
                 themes: 'layout.html.twig'
        
           - '@add':
                 id: vue_sfc_app_block
                 parentId: page_container
                 prepend: true
                 blockType: block
   ```

<!-- Frontend -->
