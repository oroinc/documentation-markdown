<a id="index-0"></a>

<a id="custom-oro-application"></a>

<a id="dev-cookbook-create-custom-oro-application"></a>

# Custom Oro Application

No two businesses are alike. This motto is part of Oro’s product philosophy, which is why flexibility is a
fundamental principle driving its architecture. Whatever you plan to build, you can create a custom application
with minimal functions, starting from the <a href="https://github.com/oroinc/orocommerce-application" target="_blank">OroCommerce</a> application as a baseline.

## Application Repository and Installation

Before you start a new project, set up a version control system. The easiest way is to
<a href="https://docs.github.com/en/get-started/quickstart/fork-a-repo" target="_blank">fork application repository</a> of <a href="https://github.com/oroinc/orocommerce-application" target="_blank">OroCommerce</a> on GitHub.

Once the code repository is ready, follow the [installation](../setup/installation.md#installation) instructions.

#### NOTE
A newly created application repository should be used instead of the <a href="https://github.com/oroinc/orocommerce-application.git" target="_blank">https://github.com/oroinc/orocommerce-application.git</a>

Once your application is up and running, use development mode to work on customizations. To warm up the
application cache in development mode, run:

```none
php bin/console cache:clear --env=dev
```

To access the application in development mode, add index_dev.php to the base URL
(example: `http://orocommerce.example.com/index_dev.php`).

<a id="application-custom-code"></a>

## Application Custom Code

Oro application structure is based on <a href="https://github.com/symfony/symfony-standard/tree/2.8" target="_blank">Symfony Standard Edition</a>, and we highly recommend following
<a href="https://symfony.com/doc/6.4/best_practices/index.html" target="_blank">Symfony Best Practices</a> for any custom application you build on top of OroCommerce.

The root folder of your application contains an src folder. Use it as the working directory for your
custom project, and put your custom code there.

Like in Symfony applications, all custom code in the Oro application is organized in bundles — modules that
group application functionality (see <a href="https://symfony.com/doc/6.4/bundles.html" target="_blank">Symfony Bundle System</a> for best practices of module structure and design).

#### NOTE
Please note that the Oro application has several [differences](differences.md#book-differences) compared to
Symfony Standard Edition.

To create a custom application, follow these typical steps:

1. [Create a bundle](../extension/create-bundle.md#how-to-create-new-bundle).
2. Introduce [new entity](../entities/index.md#dev-entities) types that represent your business data structure and add related features.
3. [Customize](customization/index.md#architecture-customization-customize) existing functionality ([menu](../navigation/index.md#doc-create-and-customize-app-menu), [workflow](../entities-data-management/workflows/index.md#dev-doc-workflows), [extend entities](../entities/extend-entities/index.md#book-entities-extended-entities), etc.).

## Application Deployment

Oro applications are open source and can be deployed to on-premise environments. Deployment methods vary depending on organization requirements and infrastructure. You can design your own deployment process, but make sure you follow the recommendations below:

1. Follow the advice outlined in the <a href="https://symfony.com/doc/6.4/deployment.html" target="_blank">Symfony Application Deployment</a> documentation.
2. Lock all dependencies with <a href="https://getcomposer.org/doc/01-basic-usage.md#composer-lock-the-lock-file" target="_blank">composer.lock</a> before taking the code to production.
3. Warm up the application cache in production mode.
4. Disable access to index_dev.php.
5. Configure crontab and run web socket server.

Oro applications are scalable.

#### NOTE
As an alternative to on-premise deployment, you can deploy your application to <a href="/cloud">OroCloud</a>, provided you create it following the recommendations [above](#application-custom-code). Get in touch with us for more information.

## Related Articles

* [Bundle-less Structure](bundle-less-structure.md#dev-backend-architecture-bundle-less-structure)

<!-- Frontend -->
