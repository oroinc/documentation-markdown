<a id="backend-session-storage"></a>

# Session Storage

By default, the Oro application is configured to store <a href="https://www.php.net/manual/en/book.session.php" target="_blank">sessions</a> in files. If multiple servers serve your application, you must use a database to make sessions work across different servers. The recommended database
for best performance is <a href="https://redis.io/" target="_blank">Redis</a>. See [Configure Redis Servers](../../../bundles/platform/RedisConfigBundle/configure-redis-servers.md#bundle-docs-platform-redis-bundle-configure-servers)
for more details.

## Session Locking Impact on Application Availability

The Oro application requires shared session storage in any distributed environment (more than one web node). By default, <a href="https://www.php.net/manual/en/features.session.security.management.php#features.session.security.management.session-locking" target="_blank">session data is locked</a> to prevent race conditions and ensure data consistency.

This works well for consecutive requests (classic web browsing), but causes problems when multiple parallel requests run within the same session. A common B2B case is real-time price and inventory checks against a back-end ERP, which may respond slowly. To keep these checks from blocking the interface, they typically run in parallel over AJAX.

In production, this can critically affect availability: each parallel request hits the session lock and queues behind the others. With many concurrent users generating dozens of such requests, ERP performance directly limits Oro availability — and a slow ERP can overflow the request queue.

There are a few options to overcome availability issues for this kind of scenario:

* Use stateless endpoint without session initialization. Such an approach has a significant downside as it will allow accessing data without authentication stored in the session.
* Close the session before accessing any 3rd party system (recommended approach):
  ```php
  public function myAction(Request $request)
  {
      $session = $request->getSession();
      if (null !== $session && $session->isStarted()) {
          $session->save();
      }

      // do controller work here
  }
  ```

<!-- Frontend -->
