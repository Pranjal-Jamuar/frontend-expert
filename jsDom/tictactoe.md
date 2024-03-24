# Tic Tac Toe

```js
const heading = document.getElementById("game-heading"),
  restartBtn = document.getElementById("restart-button"),
  squareBoxes = document.querySelectorAll(".game-square")
let currentPlayer, totalMoves
const winningCombos = [
  [0, 1, 2],
  [3, 4, 5],
  [6, 7, 8],
  [0, 3, 6],
  [1, 4, 7],
  [2, 5, 8],
  [0, 4, 8],
  [2, 4, 6],
]

const initialiseGame = () => {
  heading.textContent = "Player 1's Turn"
  currentPlayer = 1
  totalMoves = 0
}

const startGame = () => {
  initialiseGame()
  squareBoxes.forEach((box, i) => {
    box.disabled = false
    box.textContent = ""
    box.addEventListener("click", boxClickHandler)
  })
}

const boxClickHandler = event => {
  const box = event.target
  box.textContent = currentPlayer === 1 ? "X" : "O"
  box.disabled = true

  if (checkWinning(box.textContent)) {
    gameEnd()
    heading.textContent = `Player ${currentPlayer} Won!`
    return
  } else {
    currentPlayer = currentPlayer == 1 ? 2 : 1
    heading.textContent = `Player ${currentPlayer}'s Turn`
    totalMoves++
    checkIfTie()
  }
}

const checkWinning = currentTurn => {
  return winningCombos.some(combo => {
    return combo.every(c => squareBoxes[c].textContent == currentTurn)
  })
}

const checkIfTie = () => {
  if (totalMoves === squareBoxes.length) {
    heading.textContent = "Tie Game!"
    gameEnd()
  }
}

const gameEnd = () => {
  restartBtn.style.display = "block"
  squareBoxes.forEach((box, i) => {
    box.disabled = true
  })
}

restartBtn.addEventListener("click", () => {
  restartBtn.style.display = "none"
  startGame()
})

startGame()
```
