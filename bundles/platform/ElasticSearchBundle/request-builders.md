<a id="bundle-docs-platform-elastic-search-bundle-builders"></a>

# Request Builders

Request builder is a separate class used to build a specific part of a search request to Elasticsearch based on source Query object. Request builder must implement the
\\Oro\\Bundle\\ElasticSearchBundle\\RequestBuilder\\RequestBuilderInterface interface. According to this interface, the builder receives Query object and the existing request array. The builder returns modified request array.

There are four default request builders.

## FromRequestBuilder

**Class:** Oro\\Bundle\\ElasticSearchBundle\\RequestBuilder\\FromRequestBuilder

Builder gets the **from** part of a query and converts any specific entities into the required indexes. See <a href="https://www.elastic.co/guide/en/elasticsearch/reference/6.x/search-search.html" target="_blank">index types</a> for more information.

## WhereRequestBuilder

**Class:** Oro\\Bundle\\ElasticSearchBundle\\RequestBuilder\\WhereRequestBuilder

Builder iterates through all conditions in the **where** part of the query and passes them to the chain of part builders that are used to process specific condition operators.

- **ContainsWherePartBuilder** - processes **~** (contains) and **!~** (not contains) operators. Adds <a href="https://www.elastic.co/guide/en/elasticsearch/reference/6.x/query-dsl-match-query.html" target="_blank">match query</a> for “all_text” field with nGram tokenizer or <a href="https://www.elastic.co/guide/en/elasticsearch/reference/6.x/query-dsl-wildcard-query.html" target="_blank">wildcard query</a> for regular fields.
- **EqualsWherePartBuilder** - processes **=** (equals) and **!=** (not equals) operators. Adds a <a href="https://www.elastic.co/guide/en/elasticsearch/reference/6.x/query-dsl-term-query.html" target="_blank">term query</a>.
- **RangeWherePartBuilder** - processes arithmetical operators applied to numeric values: **>** (greater), **>=** (greater or equals), **<** (lower) and **<=** (lower or equals ). Adds appropriate <a href="https://www.elastic.co/guide/en/elasticsearch/reference/6.x/query-dsl-range-query.html" target="_blank">range query</a>.
- **InWherePartBuilder** - processes **in** and **!in** operators. Converts the set into several **=** or **!=** conditions that uses <a href="https://www.elastic.co/guide/en/elasticsearch/reference/6.x/query-dsl-term-query.html" target="_blank">term query</a>.

Each part builder receives field name, field type, condition operator, value, boolean keyword and source request and returns the altered request.

## OrderRequestBuilder

**Class:** Oro\\Bundle\\ElasticSearchBundle\\RequestBuilder\\OrderRequestBuilder

Builder gets the order-by field and the order direction from the query. If they are defined, builder converts them to the <a href="https://www.elastic.co/guide/en/elasticsearch/reference/6.x/search-request-sort.html" target="_blank">sort</a> parameter of a search request.
The result is sorted by relevance by default.

## LimitRequestBuilder

**Class:** Oro\\Bundle\\ElasticSearchBundle\\RequestBuilder\\LimitRequestBuilder

Builder gets first result and max results values from the query and if they are defined they are converted into the <a href="https://www.elastic.co/guide/en/elasticsearch/reference/6.x/search-request-from-size.html" target="_blank">from/size</a> pagination parameters of a search request.

## AggregateBuilder

**Class:** Oro\\Bundle\\ElasticSearchBundle\\RequestBuilder\\AggregateBuilder

Builder gets collection of aggregating function and field name from the query. If they are defined they are converted into the <a href="https://www.elastic.co/guide/en/elasticsearch/reference/6.x/search-aggregations.html" target="_blank">aggregations</a> parameters of a search request.
Built structure of aggregations parameters will have <a href="https://www.elastic.co/guide/en/elasticsearch/reference/6.x/search-aggregations-bucket.html" target="_blank">bucket</a> type of aggregations, where each bucket is associated with a field name and a document criterion.

<!-- Frontend -->
