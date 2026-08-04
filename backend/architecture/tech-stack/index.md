<a id="architecture-overview-tech-stack"></a>

# Technology Stack

<!-- begin_client_side -->

Like any **web application**, the Oro application follows a <a href="https://en.wikipedia.org/wiki/Client%E2%80%93server_model" target="_blank">client - server architecture</a>: the server-side stack prepares the web content and delivers the response to the client. Oro applications rely on a number of embedded, integrated, and distributed technologies, explained below.

## Client Side

A **client**, whether a web browser or a third-party application connected via [the API](../../../api/index.md#web-services-api), requests the Oro application server-side to get the application content or JSON response. Information received in response from the server-side may be used:

* By the web browser – to render or update the web page shown to the end user.
* By the third party application – trigger actions in the Oro applications or other integrated systems to launch data synchronization.

### Web Browser

Oro applications support the following web browsers:

* <a href="https://www.mozilla.org/en-US/firefox/new/" target="_blank">Mozilla Firefox</a> (latest version)
* <a href="https://www.google.com/chrome/" target="_blank">Google Chrome</a> (latest version)
* <a href="https://www.microsoft.com/en-us/edge?form=MA13FJ" target="_blank">Microsoft Edge</a> (latest version)
* <a href="http://www.apple.com/safari/" target="_blank">Safari</a> (latest version)

Out of the box, Oro Applications are mobile-friendly due to the responsive and adaptive UI.

In addition to HTTP connections, Oro applications establish WebSocket connections between web browsers and the server side for real-time communication (for example, status notifications and alerts).

### API Client

The architecture of the third-party application that connects to the Oro application via [the API](../../../api/index.md#web-services-api) is not limited by the Oro application architecture. You can implement the API client as a separate custom web application, custom mobile application, ERP system, ETL service, etc.

<!-- stop_client_side -->
<!-- begin_server_side -->

## Server Side

On the **server-side**, the Oro application comprises multiple systems and elements that interact to deliver a reliable, scalable, and responsive Oro solution. They are detailed in the following sections.

### Oro PHP Application

The core component, **Oro PHP Application**, is a modular **PHP** web application that leverages the **Symfony** framework and **Doctrine ORM** strengths. It interacts with the following system components:

* Web Server and PHP
* Database and RDBMS
* File Storage
* Session Storage
* Message Queue
* Search Engine

### Web Server and PHP

A **web server** is an HTTP server that manages client requests and proxies them to the **Oro PHP Application**.
**Web server** may rely on the **PHP-FPM** to process requests to **Oro PHP Application** and prepare the response.

Supported web servers: <a href="https://httpd.apache.org/" target="_blank">Apache</a> and <a href="https://www.nginx.com/" target="_blank">Nginx</a>

### Database and RDBMS

**Oro application** uses the **database** to store application data and uses the Doctrine database abstraction layer (DBAL) and object-relational mapper (ORM) to interact with the database. That enables out-of-the-box support of various databases enabled by Doctrine. On top of that, in the Oro application, Doctrine capabilities are extended with additional database functions in the <a href="https://github.com/oroinc/doctrine-extensions" target="_blank">Oro Doctrine Extensions</a> library. Currently, the extended functions are supported for PostgreSQL database only.

Supported RDBMs:

* PostgreSQL in CE and EE

#### NOTE
For implementation details, see [Database System Component](database.md#op-structure-database) topic for more information about the database component.

### File Storage

Oro application uses **File Storage** to access data files.

You can configure the file storage to use different filesystems to store the data, like a local filesystem, GridFS storage, etc.

There are two types of storage:

* **private** is intended to store data that should not be available via a direct link, for example,
  attachments’ data, import and export files, protected media cache files, etc.
* **public** is intended to store data that can be available via a direct link without access checks, for example,
  resized product images, sitemap files, etc.

#### NOTE
For implementation details, see [File Storage](file-storage.md#backend-file-storage) topic for more information about
the file storage component.

### Session Storage

Oro application uses <a href="https://www.php.net/manual/en/intro.session.php" target="_blank">sessions</a> to preserve user data between web requests. This information is placed in a persistent
store that can be accessed from subsequent requests. For implementation details, see
[Session Storage](session-storage.md#backend-session-storage) topic.

### Message Queue

The Oro application uses the **Message Queue** to process heavy jobs asynchronously, since running them immediately may degrade performance. Reindexing large volumes of data, creating large bulks of items, and similar jobs are usually handled by MQ consumers.

To process queued messages, the Oro application uses a proprietary consumer service. It runs as a daemon and handles all asynchronous jobs (messages) registered in a Message Queue.

The consumer service is scalable: it can run as parallel processes and/or on multiple servers to handle a large volume of asynchronous processes. The number of processes required depends on server capacity. To keep response times acceptable and absorb spikes in the server-side workload, you can scale message processing by adding more consumer services on demand.

Supported MQ solutions:

* Proprietary DB-based MQ in CE and EE
* RabbitMQ in EE only (for scalability)

#### NOTE
For implementation details, see [Message Queue](../../mq/index.md#op-structure-mq-index) topic for more information about the message queue component.

### Search Engine

Oro application uses **Search Index** to enable full-text search and speed up the run-time access to the large amounts of application data.

Supported search index providers:

* [DB full-text search](search/index.md#search-index-db-from-md) in CE and EE
* [Elastic Search](../../../bundles/platform/ElasticSearchBundle/index.md#elastic-search) in EE only

#### NOTE
For implementation details, see [Search Index Concept](search/index.md#search-index-overview) topic for more information about the search index component.

### Cache Storage

The purpose of caching is to minimize the number of computing operations, including fetching data from other sources, by reusing results stored in the cache storage.

In production environments, we employ the following types of cache:
- Data Cache
- System Cache
- Content Cache

**Data cache**

Data cache is used for storing data that can be generated and changed in runtime.
It depends on database data, therefore must be shared in [multi-node setups](../../../cloud/architecture/index.md#cloud-architecture).
It is implemented using <a href="https://symfony.com/doc/current/components/cache/adapters/redis_adapter.html" target="_blank">Redis Cache Adapter</a> and [OroRedisConfigBundle](../../../bundles/platform/RedisConfigBundle/index.md#bundle-docs-platform-redis-bundle) with Redis Sentinel or Redis Cluster.

Examples of such cache are below:

* [Caching complex ACL structures](../../entities/acls.md#coobook-entities-acl-enable)
* [Catalog Menu Caching](../../../bundles/commerce/CatalogBundle/index.md#bundle-docs-commerce-catalog-bundle)
* <a href="https://www.doctrine-project.org/projects/doctrine-orm/en/2.15/reference/caching.html" target="_blank">Doctrine ORM caching</a>

#### NOTE
See the [Data Cache Service](../../../bundles/platform/CacheBundle/index.md#bundle-docs-platform-cache-bundle-data-cache-service) documentation for more information.

**System cache**

System cache should be generated during deployment operations and must be read-only in runtime.
It mainly relies on code sources such as DI container, annotations, TWIG, YAML and in some cases, database data like [Extend Entities](../../entities/extend-entities/index.md#book-entities-extended-entities). As a result, it should not be shared in [multi-node setups](../../../cloud/architecture/index.md#cloud-architecture).
It is implemented using <a href="https://symfony.com/doc/current/components/cache/adapters/filesystem_adapter.html" target="_blank">Filesystem Cache Adapter</a> and <a href="https://symfony.com/doc/current/components/cache/adapters/php_files_adapter.html" target="_blank">PHP Files Cache Adapter</a>, and it becomes the most efficient cache when combined with OPcache.

Examples of such cache are below:

* <a href="https://symfony.com/doc/current/components/dependency_injection/workflow.html#working-with-a-cached-container" target="_blank">Symfony container</a>
* <a href="https://symfony.com/doc/current/reference/configuration/twig.html#cache" target="_blank">Twig caching</a>

#### NOTE
See the [Caching Static Configuration](../../../bundles/platform/CacheBundle/index.md#bundle-docs-platform-cache-bundle-caching-static-configs) documentation for more information.

**Content cache**

Content cache is used for storing html content to avoid its generation whenever the page is accessed.
It depends on the database data, but must not be shared in [multi-node setups](../../../cloud/architecture/index.md#cloud-architecture).
It is implemented using <a href="https://symfony.com/doc/current/components/cache/adapters/redis_adapter.html" target="_blank">Redis Cache Adapter</a> and [OroRedisConfigBundle](../../../bundles/platform/RedisConfigBundle/index.md#bundle-docs-platform-redis-bundle) using standalone Redis running alongside PHP-FPM and Nginx.

#### NOTE
For more information, see [OroCommerce Render Caching](../../../frontend/storefront/render-cache.md#dev-doc-render-cache).

### Notes on Deployment Options

For a compact, resource-efficient deployment, all systems and elements of the Oro application can be hosted on a single physical or virtual server instance.

For scalable, high-load deployments:

* Multiple instances of the Oro application can run on their own dedicated web servers, with a load balancer directing client requests to the appropriate server.
* Each system and element of the Oro application can be hosted on its own dedicated server and scaled separately.

**Next step**: [Oro PHP Application Structure](../structure/index.md#architecture-oro-php-application-structure)

**Related Topics**

* [Database](database.md#op-structure-database)
* [File Storage](file-storage.md#backend-file-storage)
* [Session Storage](session-storage.md#backend-session-storage)
* [Message Queue](../../mq/index.md#op-structure-mq-index)
* [Search Index Concept](search/index.md#search-index-overview)

<!-- Frontend -->
