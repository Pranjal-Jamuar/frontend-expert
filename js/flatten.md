# Flatten

```js
const formatArray = array => {
  let newArray = []

  for (let i = 0; i < array.length; i++) {
    if (Array.isArray(array[i])) {
      newArray = [...newArray, ...formatArray(array[i])]
    } else if (typeof array[i] === "object") {
      newArray.push(formatObj(array[i]))
    } else {
      newArray.push(array[i])
    }
  }

  return newArray
}

const formatObj = value => {
  let newObj = {}
  const keys = value ? Object.keys(value) : []

  for (const key of keys) {
    if (
      !Array.isArray(value[key]) &&
      value[key] != null &&
      typeof value[key] === "object"
    ) {
      let returnIterator = formatObj(value[key])

      newObj = { ...newObj, ...returnIterator }
    } else {
      if (Array.isArray(value[key])) {
        newObj[key] = formatArray(value[key])
      } else {
        newObj[key] = value[key]
      }
    }
  }

  return newObj
}

const flatten = value => {
  if (Array.isArray(value)) return formatArray(value)

  if (value != null && typeof value === "object") return formatObj(value)

  return value
}

// Do not edit the line below.
exports.flatten = flatten
```
