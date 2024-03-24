# Toasts

```js
const textarea = document.getElementById("message-content")
const duration = document.getElementById("duration")
const cancelable = document.getElementById("cancelable")
const success = document.getElementById("success")
const addBtn = document.getElementById("add-button")
const clearBtn = document.getElementById("clear-button")
const list = document.getElementById("toasts")

const addToast = () => {
  const div = document.createElement("div")
  div.classList.add("toast")
  div.classList.add(success.checked ? "success-toast" : "error-toast")

  const p = document.createElement("p")
  p.classList.add("message")
  p.textContent = textarea.value || (success.checked ? "Success!" : "Error.")

  const button = document.createElement("button")
  button.classList.add("cancel-button")
  button.textContent = "X"

  if (cancelable.checked) {
    div.appendChild(p)
    div.appendChild(button)
  } else {
    div.appendChild(p)
  }

  div.addEventListener("click", removeToast)

  list.insertBefore(div, list.firstChild)

  const toastDuration = duration.value <= 500 ? 500 : duration.value
  setTimeout(() => div.remove(), toastDuration)
}

const removeToast = e => {
  e.target.parentElement.remove()
}

const clearList = () => {
  list.innerHTML = ""
}

addBtn.addEventListener("click", addToast)
clearBtn.addEventListener("click", clearList)
```
