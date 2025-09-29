<a id="index-0"></a>

<a id="custom-oro-application"></a>

<a id="dev-cookbook-create-custom-oro-application"></a>

# Custom Oro Application

No two businesses are alike. This motto is part of Oro products philosophy and this is why flexibility is one of
the key principles that drive architecture in Oro. Depending on what you are planning to build, you can
create your custom application with minimum functions starting either with <a href="https://github.com/oroinc/platform-application" target="_blank">OroPlatform</a>, or <a href="https://github.com/oroinc/crm-application" target="_blank">OroCRM</a>, or
<a href="https://github.com/oroinc/orocommerce-application" target="_blank">OroCommerce</a> application as a baseline. No matter what is your starting point, there is no difference
in the customization process.

## Application Repository and Installation

Before you start working on a new project, it is important to have version control system in place.
The easiest way to start is to <a href="https://docs.github.com/en/get-started/quickstart/fork-a-repo" target="_blank">fork application repository</a> of <a href="https://github.com/oroinc/platform-application" target="_blank">OroPlatform</a>, <a href="https://github.com/oroinc/crm-application" target="_blank">OroCRM</a> or <a href="https://github.com/oroinc/orocommerce-application" target="_blank">OroCommerce</a> on GitHub.

Once code repository is ready, please follow [installation](../setup/installation.md#installation) instructions.

#### NOTE
Newly created application repository should be used instead of the <a href="https://github.com/orocrm/crm-application.git" target="_blank">https://github.com/orocrm/crm-application.git</a>

When your application is up and running, you can use development mode to work on customizations. In order to warm up the
application cache in development mode please run:

```none
php bin/console cache:clear --env=dev
```

To access application in development mode, add index_dev.php to the base URL
(example: `http://orocrm.example.com/index_dev.php`).

<a id="application-custom-code"></a>

## Application Custom Code

Oro application structure is based on <a href="https://github.com/symfony/symfony-standard/tree/2.8" target="_blank">Symfony Standard Edition</a> and we highly recommend to follow
<a href="https://symfony.com/doc/4.4/best_practices/index.html" target="_blank">Symfony Best Practices</a> for any custom application that you build on top of OroPlatform, OroCRM, or OroCommerce.

In the root folder of your application, there is an src folder. Use it as a working directory
for your custom project and put your custom code there. Like in Symfony applications, all custom code in Oro application
is organized in bundles - modules that group application functionality (see <a href="https://symfony.com/doc/4.4/bundles.html" target="_blank">Symfony Bundle System</a> for best practice
of module structure and design).

#### NOTE
Please note that Oro application has several [differences](differences.md#book-differences) compared to
Symfony Standard Edition.

Typically, to create a custom application you may follow the common steps:

1. [Create a bundle](../extension/create-bundle.md#how-to-create-new-bundle)
2. Introduce [new entity](../entities/index.md#dev-entities) types that represent your business data structure and add
   related features
3. [Customize](customization/index.md#architecture-customization-customize) existing functionality
   ([menu](../navigation/index.md#doc-create-and-customize-app-menu), [workflow](../entities-data-management/workflows/index.md#dev-doc-workflows),
   [extend entities](../entities/extend-entities/index.md#book-entities-extended-entities) etc.)

## Application Deployment

Oro applications are open source and may be deployed to the on-premise environments. Deployment method could be
different depending on organization requirements and infrastructure. You can design your custom deployment process,
noting the following recommendations:

1. Take into account recommendations in <a href="https://symfony.com/doc/4.4/deployment.html" target="_blank">Symfony Application Deployment</a> documentation
2. Lock all dependencies with <a href="https://getcomposer.org/doc/01-basic-usage.md#composer-lock-the-lock-file" target="_blank">composer.lock</a> before taking the code to production
3. Warm up the application cache in production mode
4. Disable access to index_dev.php
5. Configure crontab and run web socket server

Oro applications are scalable.

#### NOTE
As an alternative to the on-premise deployment, when you created your application following recommendations
[above](#application-custom-code), you can put your application into <a href="/cloud">OroCloud</a>. Please contact us to
get more information.

<!-- Frontend -->
