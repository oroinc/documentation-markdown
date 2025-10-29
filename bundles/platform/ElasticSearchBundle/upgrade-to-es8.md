# Upgrade Website Index to Elasticsearch >=8.4, <9.0

You have only one option to perform the upgrade: via full reindexation.

Keep in mind that the previous OroCommerce versions (5.0 and below) have different structure for
flat object fields, so full indexation is required in order to fill the data in the correct format.

## Full Reindexation

This option is suitable for upgrades from all previous versions.

Search index upgrade is part of the [application upgrade](../../../backend/setup/upgrade-to-new-version.md#upgrade-application).
So, once you have turned on maintenance mode through `app/console lexik:maintenance:lock --env=prod`, you need to perform the following actions:

1. <a href="https://www.elastic.co/guide/en/elasticsearch/reference/master/stopping-elasticsearch.html" target="_blank">Stop old Elasticsearch</a>
2. Modify credentials for search engine configuration in the corresponding environment variables
3. <a href="https://www.elastic.co/guide/en/elasticsearch/reference/master/starting-elasticsearch.html" target="_blank">Start the Elasticsearch</a> 8.\* service.

Proceed with the [standard upgrade procedure](../../../backend/setup/upgrade-to-new-version.md#upgrade-application).

### Note

If you are skipping search indexation during the upgrade or keeping all the indices during the Elasticsearch upgrade
then you have to recreate indices and trigger full indexation manually:

```bash
php bin/console oro:elasticsearch:create-standard-indexes --env=prod
php bin/console oro:search:reindex --env=prod --scheduled
```

#### HINT
See the [Indexation process](../../../backend/architecture/tech-stack/search/index.md#search-index-overview-indexation-process) documentation for more details on synchronous and asynchronous (scheduled) indexation.

<!-- Frontend -->
