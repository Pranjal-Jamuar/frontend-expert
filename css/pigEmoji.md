# Pig Emoji

```css
.head {
  background-color: #ffc0cb;
  height: 200px;
  width: 200px;
  margin-top: 20px;
  border-radius: 50%;
  border: 5px solid black;
  position: relative;
}

.ear {
  background-color: #ffc0cb;
  height: 50px;
  width: 50px;
  border-radius: 50%;
  border: 5px solid black;
  position: absolute;
  top: -10px;
  z-index: -1;
}

.ear:first-of-type {
  left: 10px;
}

.ear:last-of-type {
  right: 10px;
}

.eye {
  height: 50px;
  width: 50px;
  border-radius: 50%;
  border: 2px solid black;
  position: absolute;
  top: 40px;
  background-color: white;
}

.eye:first-of-type {
  left: 30px;
}

.eye:last-of-type {
  right: 30px;
}

.pupil {
  width: 50%;
  height: 50%;
  border-radius: 50%;
  background-color: black;
  margin: 50% auto;
  transform: translateY(-50%);
}

.nose {
  width: 100px;
  height: 60px;
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  bottom: 30px;
  border-radius: 35%;
  background-color: #f57187;
  border: 2px solid black;
  display: flex;
  justify-content: space-around;
  align-items: center;
}

.nostril {
  background-color: black;
  border-radius: 50%;
  height: 50%;
  width: 25%;
}
```
