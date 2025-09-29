<a id="dev-doc-frontend-javascript-modularity"></a>

# JavaScript Modularity

## Overview

Nowadays Oro uses **ES6** modularity approach as best practices.
However since a build of JS gets made with webpack other types of modules are supported as well (e.g. **AMD**, **CommonJS**).

#### NOTE
Since OroPlatform uses ES6 only starting from 4v a lot of legacy **AMD** modules are still present in the code.

## ES6 modules (recommended)

ES Modules are the ECMAScript standard for working with modules.
Making components available in other files, we must first export and then import using **export** and **import** keywords.

#### SEE ALSO
You can find more information on how to write modular JavaScript using ES Modules in:

* <a href="https://en.wikipedia.org/wiki/ECMAScript#6th_Edition_-_ECMAScript_2015" target="_blank">ECMAScript Wiki</a>
* <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules" target="_blank">ES6 Modules</a>

```javascript
import BaseEmailVariableView from 'oroemail/js/email/variable/view';

const MyEmailVariableView = BaseEmailVariableView.extend({
    /* define extended logic here */
};

export default MyEmailVariableView
```

#### NOTE
We recommend to use this solution because it gives benefits like: automatically resolving cyclic dependencies,
readable syntax, possibility to import module partially etc.

## AMD, CommonJS (legacy)

AMD (**A**synchronous **M**odule **D**efinition) – is a concept of creating modular
JavaScript code with a defined set of dependencies. It defines the order in which resources
have to be loaded and executed and, therefore, keeping the global scope clean.

#### SEE ALSO
You can find more information on how to write modular JavaScript using AMD and CommonJS in:

* <a href="https://en.wikipedia.org/wiki/Asynchronous_module_definition" target="_blank">Asynchronous Module Definition</a>
* <a href="https://en.wikipedia.org/wiki/CommonJS" target="_blank">CommonJS</a>
* <a href="http://addyosmani.com/writing-modular-js/" target="_blank">Writing Modular JavaScript</a>

```javascript
define(function (require) {
    'use strict';

    const MyEmailVariableView;
    const BaseEmailVariableView = require('oroemail/js/email/variable/view');

    MyEmailVariableView = BaseEmailVariableView.extend({
        /* define extended logic here */
    });

    return MyEmailVariableView;
});
```

## Loading script from remote resources

Sometimes you need to download dependency which is not managed by webpack.
For that you may use <a href="https://github.com/ded/script.js" target="_blank">scriptjs</a> library.
It takes care of downloading and evaluating the external script at runtime.

```javascript
import scriptjs from 'scriptjs';
import BaseView from 'oroui/jsbase/view';

const MyView = BaseView.extend({
    initialize() {
        scriptjs('foo.js', () => {
            // foo.js is ready;

            this.doShomething();
        })
    },

    doShomething() {
        /* do something */
    }
});

export default MyView
```

<!-- Frontend -->
