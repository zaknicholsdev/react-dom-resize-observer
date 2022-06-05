# React Resize Observer

Hook to provide a performant mechanism by which code can monitor an element for changes to its size, with notifications being delivered to the observer each time the size changes.

[![codecov](https://codecov.io/gh/zaknicholsdev/react-dom-resize-observer/branch/develop/graph/badge.svg)](https://codecov.io/gh/zaknicholsdev/react-dom-resize-observer)

![Workflow](https://github.com/zaknicholsdev/react-dom-resize-observer/actions/workflows/ci-cd.yml/badge.svg?branch=develop)


### Installation

```sh
$ npm install react-dom-resize-observer
```

### Examples

```tsx
export function App() {
  const {
      // New dimensions when resize is observed.
      entry, 
      // Callback to pass as a ref to give this hook access to the DOM element.
      observer, 
      // Callback to disconnect observing completely.
      disconnect
      // Callback to unobserve a specific element.
      unobserve 
    } = useResizeObserver<HTMLDivElement>(onResize)

    const { entry, disconnect, unobserve, observe } =
    useResizeObserver<HTMLDivElement | null>({
      // You can optionally pass your own ref if you already have one.
      elementRef: ref,
      onResize: (el) => { /** Do something with the element... */ },
    });


  return (
    // Attach the observer as a ref to the DOM. 
    <div ref={observer} onClick={disconnect}>
      App
    </div>
  )
}
```
