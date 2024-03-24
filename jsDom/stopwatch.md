# Stopwatch

```js
"use strict"

// Global Variables
const INTERVAL_MS = 20
let min = 0
let sec = 0
let ms = 0
let begin
let timerID

// Elements
let startBtnEl = document.getElementById("start-button")
let stopBtnEl = document.getElementById("stop-button")
let resetBtnEl = document.getElementById("reset-button")
let timerEl = document.getElementById("timer")

// Listeners
startBtnEl.addEventListener("click", startStopwatch)
stopBtnEl.addEventListener("click", pauseStopwatch)
resetBtnEl.addEventListener("click", resetStopwatch)

// Functions
function updateTimerContent(currentMs, currentSec, currentMin) {
  let formattedCurrentMs = currentMs.toLocaleString("en-US", {
    minimumIntegerDigits: 3,
  })

  let formattedCurrentSec = currentSec.toLocaleString("en-US", {
    minimumIntegerDigits: 2,
  })

  let formattedCurrentMin = currentMin.toLocaleString("en-US", {
    minimumIntegerDigits: 2,
  })

  timerEl.textContent = `${formattedCurrentMin}:${formattedCurrentSec}:${formattedCurrentMs}`
}

function startStopwatch() {
  startBtnEl.disabled = true
  stopBtnEl.disabled = false
  resetBtnEl.disabled = true

  if (begin == undefined) {
    begin = Date.now()
  } else {
    begin = Date.now() - (sec * 1000 + ms)
  }

  timerID = setInterval(calculateTimer, INTERVAL_MS)
}

function pauseStopwatch() {
  startBtnEl.disabled = false
  stopBtnEl.disabled = true
  resetBtnEl.disabled = false
  clearInterval(timerID)
}

function resetStopwatch() {
  pauseStopwatch()
  resetBtnEl.disabled = true
  ms = 0
  sec = 0
  min = 0
  updateTimerContent(0, 0, 0)
  begin = Date.now()
}

function calculateTimer() {
  let end = Date.now()
  let elapsed = end - begin

  ms = Math.floor(elapsed % 1000)
  sec = Math.floor(elapsed / 1000)

  if (sec == 60) {
    min++
    sec = 0
    begin = Date.now()
  }
  updateTimerContent(ms, sec, min)
}
```
