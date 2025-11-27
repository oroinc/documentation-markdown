<a id="bundle-docs-platform-search-bundle-datetime"></a>

# DateTimeFormatter

#### HINT
See the [Search Index](../../../backend/architecture/tech-stack/search/index.md#search-index-overview) documentation to get a more high-level understanding of the search index concept in the Oro application.

Class <a href="https://github.com/oroinc/platform/blob/5.1/src/Oro/Bundle/SearchBundle/Formatter/DateTimeFormatter.php" target="_blank">DateTimeFormatter</a>.

Please use this class if you need format DateTime object to <a href="https://github.com/oroinc/platform/blob/5.1/src/Oro/Bundle/SearchBundle/Formatter/DateTimeFormatter.php#L7" target="_blank">string by specific format</a>.

* format
  ```php
  public function format(\DateTime $dateTimeValue)
  ```

  Returns formatted string of DateTime. The class uses DateTimeFormatter::DATETIME_FORMAT constant to format the DateTime object as a string.

<!-- Frontend -->
