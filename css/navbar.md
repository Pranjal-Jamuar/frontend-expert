# Navbar

```css
:root {
  --font-size: 18px;
}

nav,
ul {
  display: flex;
  flex-direction: row;
}

nav {
  background: #6e072d;
  color: white;
  justify-content: space-between;
}

ul {
  margin: 0;
  padding: 0;
}

li {
  padding: var(--font-size) calc(var(--font-size) * 1.5);
  font-size: var(--font-size);
  border-right: 2px solid white;
  display: inline-block;
  list-style: none;
}

li:last-child {
  border: 0;
}

li:hover {
  background: #b90e4d;
  cursor: pointer;
}
```
