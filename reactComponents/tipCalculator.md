# Tip Calculator

```js
import React from "react"

export default function TipCalculator() {
  const [bill, setBill] = useState(50)
  const [tip, setTip] = useState(18)
  const [people, setPeople] = useState(1)

  const handleBill = e => {
    const value = e.target.value
    setBill(value)
  }

  const handleTip = e => {
    const value = e.target.value
    setTip(value)
  }

  const handlePeople = e => {
    const value = e.target.value
    setPeople(value)
  }

  const totalTip = (bill * (tip / 100)).toFixed(2)
  const tipPerPerson = (totalTip / people).toFixed(2)

  return (
    <>
      <label>
        Bill
        <input type="number" value={bill} onChange={handleBill} />
      </label>
      <label>
        Tip Percentage
        <input type="number" value={tip} onChange={handleTip} />
      </label>

      <label>
        Number of People
        <input type="number" value={people} onChange={handlePeople} />
      </label>
      <p>Total Tip: {totalTip > 0 ? `$${totalTip}` : "-"}</p>
      <p>Tip Per Person: {tipPerPerson > 0 ? `$${tipPerPerson}` : "-"}</p>
    </>
  )
}
```
