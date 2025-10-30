<a id="bundle-docs-platform-batch-bundle"></a>

# OroBatchBundle

<a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/BatchBundle" target="_blank">OroBatchBundle</a> adds <a href="https://github.com/oroinc/OroAkeneoBundle/blob/1.6.0/README.md" target="_blank">AkeneoBatchBundle</a> to Oro applications and enables batch architecture usage for data processing.

## Components

**BufferedIdentityQueryResultIterator**

Iterates the results of the query.

- Allows iterating large query results without the risk of getting out of memory error.
- Allows iterating through the changing dataset
- Ensures that the initial query result will be constant during pagination; this allows modifying or deleting rows included in the dataset.

Preloading of unique row identifiers fixes the query dataset. The iterator uses <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/BatchBundle/ORM/Query/ResultIterator/IdentityIterationStrategyInterface.php" target="_blank">IdentityIterationStrategyInterface</a> to modify the original query.

First, it detects unique result row identifiers and stores them. Then, it paginates through the array of stored identifiers by batches and limits the origin query with the current batch set of IDs.

By default, <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/BatchBundle/ORM/Query/ResultIterator/SelectIdentifierWalker.php" target="_blank">SelectIdentifierWalker</a> SQL walker is used to detect the entity single identity field. These identifiers are fetched and hydrated by <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/BatchBundle/ORM/Query/ResultIterator/IdentifierHydrator.php" target="_blank">IdentifierHydrator</a> to an array of integers in memory. **1,5 million** rows in a query will require approximately **80MB** of memory to store keys.

<a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/BatchBundle/ORM/Query/ResultIterator/LimitIdentifierWalker.php" target="_blank">LimitIdentifierWalker</a> SQL walker is used to add the ‘Where In (identifiers)’ clause to a query and fetch a batch of a query result.

In case if OneToMany/ManyToMany joins, the iterator will iterate root entities. The count method will return several root entities (unique IDs).
In this case, the actual number of rows fetched in one batch can vary depending on the number of joined rows corresponding to the given ID.
If Order By is used on a joined field, the actual joined field order could be different while the Root Entities order stays consistent.

Hydrating the query result to an entity object with joined ToMany relations will level above problems. This works well for queries with an entity with a single identifier.

In complex cases, you can implement <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/BatchBundle/ORM/Query/ResultIterator/IdentityIterationStrategyInterface.php" target="_blank">IdentityIterationStrategyInterface</a> interface with custom Iteration Strategy.
Custom Iteration Strategy can be set to an iterator with the *setIterationStrategy()* method before the query is executed (iteration is started).

<!-- Frontend -->
