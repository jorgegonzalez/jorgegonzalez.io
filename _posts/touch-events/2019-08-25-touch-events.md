---
layout: post
title: "Touch Events"
date: 2019-08-25
categories: javascript react
---

This is a nice and quick utility I learned recently to support both `TouchEvents` and `MouseEvents` while only worrying about the `onClick` prop.

**This probably doesn't support all use cases.**

`getTouchEvents` takes a callback that is invoked (or not) by either the `onClick` or `onTouchStart` handlers, depending on the environment.

```js
function getTouchEvents(callback) {
  if (callback) {
    if (window && "ontouchstart" in window) {
      return {
        onTouchStart: callback,
        onClick: noop,
      };
    } else {  
      return {
        onTouchStart: noop,
        onClick: callback,
      };
    }
  }
}
```

Finally, add this utility to your design system's `Button` primitive:

```jsx
function Button({ onCick, children }) {
  const touchEvents = getTouchEvents(onClick);
  return <button {...touchEvents}>{children}</button>;
}

function App() {
  return (
    <div>
      <Button onClick={() => alert("onClick")}>Click</Button>
      <Button onClick={() => alert("onTouchStart")}>Touch</Button>
    </div>
  );
}
```
