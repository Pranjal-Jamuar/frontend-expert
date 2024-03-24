# Array Methods

```js
Array.prototype.myMap = function (callback) {
  const result = []
  for (let i = 0; i < this.length; i++) {
    result.push(callback(this[i], i, this))
  }
  return result
}

Array.prototype.myFilter = function (callback) {
  const result = []
  for (let i = 0; i < this.length; i++) {
    if (callback(this[i], i, this) === true) {
      result.push(this[i])
    }
  }
  return result
}

Array.prototype.myReduce = function (callback, initialValue) {
  let result = initialValue
  for (let i = 0; i < this.length; i++) {
    if (result === undefined && i === 0) {
      result = this[i]
    } else {
      result = callback(result, this[i], i, this)
    }
  }
  return result
}
```
