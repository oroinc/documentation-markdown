<a id="bundle-docs-platform-ui-bundle-multi-use-resource-manager"></a>

# MultiUseResourceManager ⇐ BaseClass

Allows to create/remove resource that could be used by multiple holders.

Use case:

```javascript
var backdropManager = new MultiUseResourceManager({
    listen: {
        'constructResource': function() {
            $(document.body).addClass('backdrop');
        },
        'disposeResource': function() {
            $(document.body).removeClass('backdrop');
        }
    }
});

// 1. case with Ids
var holderId = backdropManager.hold();
// then somewhere
backdropManager.release(holderId);

// 2. case with holder object
backdropManager.hold(this);
// then somewhere, please note that link to the same object should be provided
backdropManager.release(this);

// 2. case with holder identifier
backdropManager.hold(this.cid);
// then somewhere, please note that link to the same object should be provided
backdropManager.release(this.cid);
```

**Extends:** [BaseClass](base-class.md#bundle-docs-platform-ui-bundle-baseclass)

## multiUseResourceManager.counter : number

Holders counter

**Kind**: instance property of MultiUseResourceManager
**Access:** protected

## multiUseResourceManager.isCreated : boolean

True if resource is created

**Kind**: instance property of MultiUseResourceManager

## multiUseResourceManager.holders : Array

Array of ids of current resource holders

**Kind**: instance property of MultiUseResourceManager

multiUseResourceManager.constructor()

**Kind**: instance method of MultiUseResourceManager

## multiUseResourceManager.hold(holder) ⇒ \*

Holds resource

**Kind**: instance method of MultiUseResourceManager
**Returns**: \* - holder identifier

| Param   | Type   | Description       |
|---------|--------|-------------------|
| holder  | \*     | holder identifier |

## multiUseResourceManager.release(id)

Releases resource

**Kind**: instance method of MultiUseResourceManager

| Param   | Type   | Description       |
|---------|--------|-------------------|
| id      | \*     | holder identifier |

## multiUseResourceManager.isReleased(id) ⇒ boolean

Returns true if resource holder has been already released

**Kind**: instance method of MultiUseResourceManager

| Param   | Type   | Description       |
|---------|--------|-------------------|
| id      | \*     | holder identifier |

## multiUseResourceManager.checkState()

Check state, creates or disposes resource if required

**Kind**: instance method of MultiUseResourceManager
**Access:** protected

## multiUseResourceManager.dispose()

**Kind**: instance method of MultiUseResourceManager
