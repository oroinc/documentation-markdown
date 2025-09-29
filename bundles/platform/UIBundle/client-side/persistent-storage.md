<a id="bundle-docs-platform-ui-bundle-persistent-storage"></a>

# PersistentStorage

## persistentStorage

Provides clint-side storage. Uses localStorage if supported, otherwise uses cookies. Realizes <a href="https://developer.mozilla.org/en-US/docs/Web/API/Storage" target="_blank">Storage Interface</a>.

**Kind**: Exported member

## persistentStorage.length : number

Returns an integer representing the number of data items stored in the Storage object.

**Kind**: static property of persistentStorage
**Read only**: true

## persistentStorage.getItem(sKey) ⇒ string

When passed a key name, will return that key’s value.

**Kind**: static method of persistentStorage

| Param   | Type   |
|---------|--------|
| sKey    | string |

## persistentStorage.key(nKeyId)

When passed a number n, this method will return the name of the nth key in the storage.

**Kind**: static method of persistentStorage

| Param   | Type   |
|---------|--------|
| nKeyId  | number |

## persistentStorage.setItem(sKey, sValue)

When passed a key name and value, will add that key to the storage, or update that key’s value if it
already exists.

**Kind**: static method of persistentStorage

| Param   | Type   |
|---------|--------|
| sKey    | string |
| sValue  | string |

## persistentStorage.removeItem(sKey)

When passed a key name, will remove that key from the storage.

**Kind**: static method of persistentStorage

| Param   | Type   |
|---------|--------|
| sKey    | string |

## persistentStorage.hasOwnProperty()

**Kind**: static method of persistentStorage

## persistentStorage.clear()

When invoked, will empty all keys out of the storage.

**Kind**: static method of persistentStorage

<!-- Frontend -->
