# Rainbow Circles

```css
div {
  box-sizing: border-box;
  display: grid;
  place-items: center;
  border-radius: 50%;
  border: 25px solid;
  aspect-ratio: 1;
  width: calc(100% - 50px);
  height: calc(100% - 50px);
}

#outer {
  background: #ffa500;
  border-color: #ff0000;
  width: 300px;
  height: 300px;
}

#middle {
  background: #008000;
  border-color: #ffff00;
}

#inner {
  background: #800080;
  border-color: #0000ff;
}
```
