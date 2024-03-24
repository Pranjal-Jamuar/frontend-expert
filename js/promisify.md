# Promisify

```js
function promisify(callback) {
  return function (...args) {
    return new Promise((resolve, reject) => {
      callback.call(this, ...args, (err, val) =>
        err ? reject(err) : resolve(val)
      )
    })
  }
}

// Do not edit the line below.
exports.promisify = promisify
```
