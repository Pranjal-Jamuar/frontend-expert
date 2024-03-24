# Debounce

```js
function debounce(callback, delay, isImmediate = false) {
  function immediate() {
    let lastCall = -Infinity
    return function (...args) {
      const now = Date.now()
      if (now - lastCall >= delay) {
        callback.apply(this, args)
      }
      lastCall = now
    }
  }
  function delayed() {
    let id = null
    return function (...args) {
      if (id) {
        clearTimeout(id)
      }
      id = setTimeout(() => {
        callback.apply(this, args)
      }, delay)
    }
  }
  return isImmediate ? immediate() : delayed()
}

// Do not edit the line below.
exports.debounce = debounce
```
