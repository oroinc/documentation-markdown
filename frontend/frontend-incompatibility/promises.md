# Using Native Promises Instead of jQuery Deferred

Starting with OroCommerce 7.0, the frontend framework is transitioning away from `jQuery Deferred` in favor of **native Promises**. Native Promises provide
a standardized, modern, and more reliable way to handle asynchronous logic, and they integrate smoothly with newer features, such as **async/await**.

This document shows examples of replacing `$.Deferred` and `$.when` with equivalent Promise-based patterns.

## Replacing initLayout().done() to initLayout().then()

| Before (using .done() method)                                                                                                                                                                                                                                | After (using .then() method)                                                                                                                                                                                                                                 |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ```javascript<br/>import BaseView from 'oroui/js/app/views/base/view';<br/><br/>const SomeView = BaseView.extend({<br/>    render: function() {<br/>        this.initLayout().done(() => {...});<br/>    }<br/>});<br/><br/>export default SomeView;<br/>``` | ```javascript<br/>import BaseView from 'oroui/js/app/views/base/view';<br/><br/>const SomeView = BaseView.extend({<br/>    render: function() {<br/>        this.initLayout().then(() => {...});<br/>    }<br/>});<br/><br/>export default SomeView;<br/>``` |

## Replacing $.Deferred With Promise

| Before (using $.Deferred)                                                                                                                                                                                                                                                                                                                                                                                                                                                                   | After (using native Promise)                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ```javascript<br/>function loadData() {<br/>  var d = $.Deferred();<br/>  $.ajax({<br/>    url: '/api/data',<br/>    success: function (result) {<br/>      d.resolve(result);<br/>    },<br/>    error: function () {<br/>      d.reject('Request failed');<br/>    }<br/>  });<br/>  return d.promise();<br/>}<br/>loadData()<br/>  .done(function (result) {<br/>    console.log('Loaded:', result);<br/>  })<br/>  .fail(function (err) {<br/>    console.error(err);<br/>  });<br/>``` | ```javascript<br/>function loadData() {<br/>  return new Promise(function (resolve, reject) {<br/>    $.ajax({<br/>      url: '/api/data',<br/>      success: resolve,<br/>      error: function () {<br/>        reject('Request failed');<br/>      }<br/>    });<br/>  });<br/>});<br/>}<br/><br/>loadData()<br/>  .then(function (result) {<br/>    console.log('Loaded:', result);<br/>  })<br/>  .catch(function (err) {<br/>    console.error(err);<br/>  });<br/>``` |

## Replacing $.when With Promise.all

| Before (using $.when)                                                                                                                                                                                                   | After (using Promise.all)                                                                                                                                                                                                         |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ```javascript<br/>$.when(loadUser(), loadSettings())<br/>  .done(function (user, settings) {<br/>    console.log(user, settings);<br/>  })<br/>  .fail(function () {<br/>    console.error('Failed');<br/>  });<br/>``` | ```javascript<br/>Promise.all([loadUser(), loadSettings()])<br/>  .then(function ([user, settings]) {<br/>    console.log(user, settings);<br/>  })<br/>  .catch(function () {<br/>    console.error('Failed');<br/>  });<br/>``` |

## Using async/await (optional)

Native Promises can also be used with `async`/`await`, which can simplify
asynchronous code and make it easier to read.

```javascript
async function init() {
  try {
    const result = await loadData();
    console.log('Loaded:', result);
  } catch (err) {
    console.error(err);
  }
}

init();
```

## Summary of mappings

| jQuery Deferred      | Native Promise        | Note                              |
|----------------------|-----------------------|-----------------------------------|
| `$.Deferred()`       | `new Promise()`       | Replace custom deferred wrappers. |
| `promise.done(fn)`   | `promise.then(fn)`    | Success callback.                 |
| `promise.fail(fn)`   | `promise.catch(fn)`   | Error callback.                   |
| `promise.always(fn)` | `promise.finally(fn)` | Runs whether success or failure.  |
| `$.when(a, b)`       | `Promise.all([a, b])` | Returns array of results.         |
