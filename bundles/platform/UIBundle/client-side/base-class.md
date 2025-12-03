<a id="bundle-docs-platform-ui-bundle-baseclass"></a>

# BaseClass

BaseClass implements the <a href="http://backbonejs.org/#Events" target="_blank">Backbone events API</a>, Chaplin’s <a href="https://github.com/chaplinjs/chaplin/blob/master/docs/chaplin.view.md#listen" target="_blank">declarative event bindings</a>, and the <a href="https://github.com/chaplinjs/chaplin/blob/master/docs/chaplin.event_broker.md" target="_blank">Chaplin.EventBroker API</a>.

## Constructor Options

| Param          | Type   | Description                                       |
|----------------|--------|---------------------------------------------------|
| options        | Object | Options container                                 |
| options.listen | Object | Object defining event listeners for this instance |

## Properties

- **baseClass.disposed**: boolean

  Indicates whether the class instance has been disposed. This flag helps prevent operations on disposed instances.

* **Kind**: instance property of BaseClass

<!-- Frontend -->
