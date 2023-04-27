# EventListenerList

This is a module that extends the Element interface to provide a way to track registered event listeners on a DOM element.

The module exports a default function that, when called, overwrites the default `addEventListener`, `removeEventListener`, `getEventListeners` and `clearEventListeners` methods of the `Element.prototype`.

## Usage
To use the EventListenerList module, import the default function from the module and call it.

```
import EventListenerList from "@types/dom-eventlistenerlist";


EventListenerList();
```

### Once the function is called, you can use the new methods on any DOM element.
```
const myButton = document.querySelector("#myButton");

// add an event listener and get the registered listeners for the "click" event
myButton.addEventListener("click", () => console.log("Clicked"));
myButton.getEventListeners("click"); // [{ type: "click", listener: [Function], useCapture: false }]

// clear all event listeners for the element
myButton.clearEventListeners();

// remove a specific event listener
const mouseoutListener = () => console.log("Mouse out");
myButton.addEventListener("mouseout", mouseoutListener);
myButton.clearEventListeners("mouseout");
```
