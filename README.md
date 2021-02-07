# react-hooks-utils

> Just some react hooks utils... (WIP)

## Install

```bash
npm install --save react-hooks-utils
```

## Usage

### useStateWithCb:
```jsx
import React from 'react'
import { useStateWithCb } from 'react-hooks-utils'

function testCallback(value) {
    const el = document.getElementById('test')
    el.innerText = `Current value is ${value}`
}

function Example() {
    const [state, setState] = useStateWithCb(0, testCallback)
    const increment = () => setState((prev) => prev + 1)
    const decrement = () => setState((prev) => prev - 1)
    return (
        <div>
            <button onClick={increment}>Increment</button>
            <button onClick={decrement}>Decrement</button>
            <p id="test"/>
        </div>
    )
}
```

### useDimensions:
```jsx
import React from 'react'
import { useDimensions } from 'react-hooks-utils'

function Example() {
    const {
        ref,
        height,
        width
    } = useDimensions()
    return (
        <div ref={ref}>
            <p>Width: {width}px</p>
            <p>Height: {height}px</p>
        </div>
    )
}
```

### useWindowDimensions:
```jsx
import React from 'react'
import { useWindowDimensions } from 'react-hooks-utils'

function Example() {
    const {
        height,
        width,
        breakpoint
    } = useWindowDimensions()
    return (
        <div ref={ref}>
            <p>Width: {width}px</p>
            <p>Height: {height}px</p>
            <p>Current breakpoint: {breakpoint}</p>
        </div>
    )
}
```

## License

MIT © [johnnyboi91](https://github.com/johnnyboi91)