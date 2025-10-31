<a id="dev-doc-frontend-javascript-unit-tests"></a>

# JavaScript UnitTests

## Installation

The following software is required to run JS tests:

> - <a href="https://nodejs.org/en/" target="_blank">Node.js</a> (JavaScript Engine)
> - <a href="http://karma-runner.github.io/4.0/index.html" target="_blank">Karma</a> (Test Runner for JavaScript)
> - <a href="https://jasmine.github.io/api/3.5/global" target="_blank">Jasmine 3.5</a> (Behavior-Driven Development Testing Framework)

#### HINT
For instructions on how to install **Node.js**, navigate to the <a href="https://nodejs.org/en/download/" target="_blank">official website</a>.

Once the node is installed, install several modules using <a href="https://npmjs.org/" target="_blank">Node Packaged Modules</a> manager by executing the following command from the root folder of your application:

```none
npm install
```

## Configuration

Configuration for the test-run is placed in karma.config.js.dist file on the root directory of the application.

#### HINT
See more information in the official <a href="http://karma-runner.github.io/4.0/config/configuration-file.html" target="_blank">Karma documentation</a>.

It can be useful to create a separate configuration file by copying the karma.config.js.dist file to karma.config.js and modifying it.

## Running

To run tests, call the following command:

```none
npm run test
```

To run testsuite with a custom configuration, you can use the command line parameters which overwrite the parameters in the configuration file.

There are few custom options added for preparing karma config:

- –mask \_string_ file mask for Spec files. By default it is ‘vendor/oro/\*\*/Tests/JS/\*\*/\*Spec.js’ that matches all Spec files in the project within oro vendor directory.
- –spec \_string_ path for a certain Spec file, if it passed then the search by mask is skipped and the test is run single Spec file.
- –skip-indexing \_boolean_ allows to skip phase of collection Spec files and reuse the collection from previews run (if it exists).
- –theme \_string_ theme name is used to generate webpack config for certain theme. By default it is ‘admin.oro’.

To keep tests continuously running and re-executing when any watched file is modified, use the following command:

```none
npm run test-watch
```

To debug unit test:

> - run test in watch mode
> - open the `http://localhost:9876/debug.html` page in you browser (check the port in the address, it has to be the same as in terminal’s output)
> - open the inspector panel and use it for the debug purpose

Any modification of the source or test file will lead to reassembly, after which you can reload the page in the browser and debug the updated code.

To run specific test, use the –spec “<path/to/someSpec.js>” parameter:

```none
npm run test-watch -- --spec vendor/oro/platform/src/Oro/Bundle/UIBundle/Tests/JS/mediatorSpec.js
```

The following extensions can be useful if you use PHPStorm:

- <a href="https://plugins.jetbrains.com/plugin/7287-karma" target="_blank">Karma plugin</a> helps to run testsuite from the IDE and view results there;
- <a href="https://plugins.jetbrains.com/plugin/7233-ddescriber-for-jasmine" target="_blank">ddescriber for jasmine</a> helps to quickly turn off or skip some tests from testsuite .

## Writing

#### HINT
See <a href="https://jasmine.github.io/api/3.5/global" target="_blank">Jasmine 3.5</a> documentation for extensive information on writing tests with **Jasmine 3.5**.

The example below illustrates the spec for the oroui/js/mediator module:

```js
import mediator from 'oroui/js/mediator';
import Backbone from 'backbone';

describe('oroui/js/mediator', function () {
    it("compare mediator to Backbone.Events", function() {
        expect(mediator).toEqual(Backbone.Events);
        expect(mediator).not.toBe(Backbone.Events);
    });
});
```

#### HINT
Use the <a href="https://github.com/plasticine/inject-loader" target="_blank">inject-loader</a> webpack loader for stubbing dependencies of a tested module.

### Jasmine-jQuery

<a href="https://github.com/velesin/jasmine-jquery" target="_blank">Jasmine-jQuery</a> extends the base Jasmine functionality, specifically it:

> - adds a number of useful matchers, and allows to check the state of a jQuery instance easily
> - applies HTML-fixtures before each test and rolls back the document after tests
> - provides a way to load HTML and JSON fixtures required for a test

However, because Jasmine-jQuery requires the full path to a fixture resource, it is better to use import to load the fixtures by a related path.

```js
import 'jasmine-jquery';
import $ from 'jquery';
import html from 'text-loader!./Fixture/markup.html';

describe('some/module', function () {
    beforeEach(function () {
        // appends loaded html to document's body,
        // after test rolls back it automatically
        window.setFixtures(html);
    });

    it('checks the markup of a page', function () {
        expect($('li')).toHaveLength(5);
    });
});
```

<!-- Frontend -->
