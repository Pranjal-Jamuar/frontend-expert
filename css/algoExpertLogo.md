# AlgoExpert Logo

```css
#wrapper {
  background-color: #02203c;
  display: flex;
  align-items: center;
  gap: 50px;
  padding-left: 50px;
}

#logo {
  display: flex;
  width: 10px;
  height: 10px;
  border: 5px solid white;
  border-radius: 50%;
  justify-content: center;
  align-items: center;
}

#logo::before,
#logo::after {
  content: " ";
  width: 100px;
  height: 30px;
  border: 5px solid white;
  border-radius: 50%;
  position: absolute;
}

#logo::before {
  transform: rotate(45deg);
}

#logo::after {
  transform: rotate(-45deg);
}

h1 {
  font-size: 48px;
  font-family: monospace;
  color: white;
}
```
