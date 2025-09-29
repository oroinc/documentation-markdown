<!-- meta: description = Fundamentals of the OroCommerce, OroCRM, and OroPlatform applications architecture for the backend developers -->

<a id="architecture-guide"></a>

# Application Architecture

## What is Oro Application

Oro application is a PHP web application that uses the Symfony framework. It provides the following benefits:

* **Runs on any OS**, although Linux is recommended. See [system requirements](../setup/system-requirements/index.md#system-requirements) for more information.
* **Scalable** - Oro application can be easily scaled up and down to meet your company needs (message queue, indexes, search).
* **Extendable** - Oro application can be extended via the packages from the <a href="https://extensions.oroinc.com/oroplatform/" target="_blank">Oro Extensions Store</a> designed by Oro, Oro partners, or the Oro community. Also, you can design your own packages to implement additional functionality.
* **Customizable** - The Oro application inherits most of the development techniques enabled by the Symfony framework and extends them. It helps quickly customize the Oro application for any business needs.

With these out-of-the-box benefits, developers can focus on implementing their unique business logic and build Oro-based applications in less time.

### Oro Licensing

Community versions of OroCRM and OroCommerce are distributed under the <a href="http://opensource.org/licenses/OSL-3.0" target="_blank">OSL-3.0</a> license. The community edition of OroPlatform is distributed under the <a href="https://opensource.org/licenses/MIT" target="_blank">MIT</a> license. Enterprise editions of OroCRM, OroCommerce, and OroPlatform are distributed under a custom End User License Agreement.

<a id="architecture-overview"></a>

## Architecture Overview

* [Technology Stack](tech-stack/index.md)
  * [Client Side](tech-stack/index.md#client-side)
    * [Web Browser](tech-stack/index.md#web-browser)
    * [API Client](tech-stack/index.md#api-client)
  * [Server Side](tech-stack/index.md#server-side)
    * [Oro PHP Application](tech-stack/index.md#oro-php-application)
    * [Web Server and PHP](tech-stack/index.md#web-server-and-php)
    * [Database and RDBMS](tech-stack/index.md#database-and-rdbms)
    * [File Storage](tech-stack/index.md#file-storage)
    * [Session Storage](tech-stack/index.md#session-storage)
    * [Message Queue](tech-stack/index.md#message-queue)
    * [Search Engine](tech-stack/index.md#search-engine)
    * [Notes on Deployment Options](tech-stack/index.md#notes-on-deployment-options)
* [Application Structure](structure/index.md)
  * [Source Code Repositories](structure/index.md#source-code-repositories)
  * [Distribution Model](structure/index.md#distribution-model)
  * [File System Structure](structure/index.md#file-system-structure)
    * [Oro PHP Application File System Structure](structure/index.md#oro-php-application-file-system-structure)
    * [Oro Package File System Structure](structure/index.md#oro-package-file-system-structure)
* [Application Framework](framework/index.md)
  * [How It Works](framework/index.md#how-it-works)
  * [Getting Started](framework/index.md#getting-started)
    * [Prepare Your Custom Application](framework/index.md#prepare-your-custom-application)
    * [Create a New Functionality](framework/index.md#create-a-new-functionality)
    * [Change an Existing Functionality](framework/index.md#change-an-existing-functionality)
    * [Create and Publish an Extension](framework/index.md#create-and-publish-an-extension)
  * [Related Cookbook Articles](framework/index.md#related-cookbook-articles)
    * [Architecture Principles of Oro Applications](framework/architecture-principles.md)
* [Application Customization](customization/index.md)
  * [Customize the Source Code](customization/index.md#customize-the-source-code)
    * [Prepare for Source Code Customization](customization/index.md#prepare-for-source-code-customization)
    * [Implement the Customization](customization/index.md#implement-the-customization)
    * [Publish Your Complete Customization as a Package on the Oro Extensions Store](customization/index.md#publish-your-complete-customization-as-a-package-on-the-oro-extensions-store)
  * [Customize via UI](customization/index.md#customize-via-ui)
* [Differences to Common Symfony Applications](differences.md)
  * [The Application Kernel](differences.md#the-application-kernel)
  * [Routing Configuration](differences.md#routing-configuration)
  * [Access Control Lists](differences.md#access-control-lists)
  * [Extension Management](differences.md#extension-management)
* [Custom Oro Application](custom-application.md)
  * [Application Repository and Installation](custom-application.md#application-repository-and-installation)
  * [Application Custom Code](custom-application.md#application-custom-code)
  * [Application Deployment](custom-application.md#application-deployment)

#### BUSINESS TIP
## Business Tip

Are you in the process of selecting the <a href="https://oroinc.com/b2b-ecommerce/b2b-ecommerce-comparison" target="_blank">best eCommerce platform for B2B</a>? Evaluate nine alternatives on our B2B comparison page.

<!-- Frontend -->
