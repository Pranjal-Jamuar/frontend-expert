# Robot Emoji

```css
.head {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 150px;
  height: 150px;
  border: 5px solid #9bbcc2;
  border-radius: 20px;
  background-color: #a4d9eb;
  margin: 50px;
}

.light {
  position: absolute;
  display: flex;
  flex-direction: column;
  align-items: center;
  top: -45px;
}

.bulb {
  width: 30px;
  height: 30px;
  margin-bottom: -5px;
  background-color: #ffa500;
  border-radius: 50%;
  z-index: 0;
}

.stick {
  width: 10px;
  height: 15px;
  background-color: #808080;
}

.ears {
  display: flex;
  flex-basis: 100%;
  justify-content: space-between;
}

.ear {
  width: 10px;
  height: 50px;
  margin: 80px;
  background-color: #c90a0a;
  border-radius: 5px 0 0 5px;
}

.ear:last-of-type {
  border-radius: 0 5px 5px 0;
}

.eyes {
  position: absolute;
  display: flex;
  justify-content: center;
  top: 25px;
  gap: 20px;
}

.eye {
  width: 30px;
  height: 30px;
  background-color: white;
  border-radius: 50%;
  border: 5px solid #00b3ff;
}

.nose {
  position: absolute;
  width: 0;
  height: 0;
  border-left: 15px solid transparent;
  border-right: 15px solid transparent;
  border-bottom: 30px solid #c90a0a;
}

.mouth {
  display: flex;
  position: absolute;
  bottom: 25px;
  width: 100px;
  height: 25px;
  background-color: #dedede;
  border: 1px solid black;
  border-radius: 20px;
  justify-content: space-around;
}

.tooth {
  width: 5px;
  height: 100%;
  background-color: black;
}
```
