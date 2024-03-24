# Todo List

```js
const list = document.getElementsByTagName("ul")[0]
const todoInput = document.getElementById("todo-input")
const addButton = document.getElementById("add-button")

let toggleAddButton = () => {
  return (addButton.disabled = todoInput.value.length === 0)
}

let clearInput = () => {
  return (todoInput.value = "")
}

const addItem = () => {
  const li = document.createElement("li")
  const text = document.createElement("h2")
  text.innerText = todoInput.value
  const button = document.createElement("button")
  button.classList.add("delete-button")
  button.innerText = "X"
  button.addEventListener("click", () => {
    const parent = button.parentElement
    parent.remove()
  })
  li.appendChild(text)
  li.appendChild(button)
  list.appendChild(li)
}

const handleAddItem = () => {
  addItem()
  clearInput()
  toggleAddButton()
}

addButton.addEventListener("click", handleAddItem)
todoInput.addEventListener("keyup", toggleAddButton)
```
