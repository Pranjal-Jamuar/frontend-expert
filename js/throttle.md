# Throttle

```js
function throttle(callback, delay) {
  let storedArgs = null
  let wait = false
  let timerId
  function checkStoredArgs() {
    if (storedArgs == null) {
      wait = false
    } else {
      callback.call(this, ...storedArgs)
      storedArgs = null
      timerId = setTimeout(checkStoredArgs, delay)
    }
  }

  const throttledFunction = function (...args) {
    if (wait) {
      storedArgs = args
      return
    }

    callback.call(this, ...args)

    wait = true
    setTimeout(checkStoredArgs, delay)
  }
  throttledFunction.cancel = function () {
    clearTimeout(timerId)
    storedArgs = null
  }
  return throttledFunction
}

// Do not edit the line below.
exports.throttle = throttle
```
