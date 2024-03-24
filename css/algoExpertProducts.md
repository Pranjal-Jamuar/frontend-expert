# AlgoExpert Products

```css
.product {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 50px;
  color: white;
  font-weight: bold;
}

#algo-expert {
  grid-row: 2 / 3;
  grid-column: 1 / -1;
  background-color: #626ee3;
  width: 75%;
  align-self: center;
  justify-self: center;
}

#systems-expert {
  grid-row: 1 / 2;
  grid-column: 1 / 3;
  background-color: #890023;
  align-self: center;
}

#ml-expert {
  background-color: #f37f1b;
  grid-column: 4 / -1;
  height: 75px;
}

#frontend-expert {
  background-color: #11967e;
  grid-row: 3 / -1;
  grid-column: 1 / 2;
  align-self: end;
}

#programming-expert {
  background-color: #f21b3f;
  height: 75px;
  grid-column: 2 / -1;
  margin-left: 10px;
}

#wrapper {
  display: grid;
  grid-template-rows: 1fr 0.6fr 1fr;
  grid-template-columns: 4fr 1fr 2fr 3fr;
  row-gap: 24px;
}
```
