# Promise Methods

```js
Promise.myRace = function (promises) {
  return new Promise((resolve, reject) => {
    for (let i = 0; i < promises.length; i++) {
      const promise = promises[i]
      promise.then(resolve).catch(reject)
    }
  })
}

Promise.myAny = function (promises) {
  return new Promise((resolve, reject) => {
    const rejected = []
    for (let i = 0; i < promises.length; i++) {
      const promise = promises[i]
      promise
        .then(resolve)
        .catch(error => {
          rejected.push(error)
        })
        .finally(() => {
          if (rejected.length === promises.length)
            reject("all promises rejected")
        })
    }
  })
}

Promise.myAll = function (promises) {
  const settled = new Array(promises.length).fill(null)

  return new Promise((resolve, reject) => {
    for (let i = 0; i < promises.length; i++) {
      const promise = promises[i]
      promise
        .then(value => {
          settled[i] = value
        })
        .catch(error => reject(error))
        .finally(() => {
          if (settled.every(x => x !== null)) resolve(settled)
        })
    }
  })
}

Promise.myAllSettled = function (promises) {
  const promiseValues = new Array(promises.length).fill(null)

  return new Promise((resolve, reject) => {
    for (let i = 0; i < promises.length; i++) {
      const promise = promises[i]
      promise
        .then(value => {
          promiseValues[i] = {
            status: "fulfilled",
            value: value,
          }
        })
        .catch(error => {
          promiseValues[i] = {
            status: "rejected",
            error: error,
          }
        })
        .finally(() => {
          if (promiseValues.every(x => x !== null)) resolve(promiseValues)
        })
    }
  })
}
```
