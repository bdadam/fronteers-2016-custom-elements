<!-- .x-slide: data-background="assets/sport-fitness-workout-resolution.jpg" -->

# Custom Elements

### Lightweight alternatives to frameworks

-----

###### Adam Beres-Deak

---

#### Providing a library to other developers without them having to write a single line of JavaScript code

---

> Custom Elements provide a way to define standardized functionality which can be invoked declaratively with the corresponding HTML markup.

```html
<custom-element some-attribute="value"></custom-element>
```

---

### Properties of custom Elements

- declarative usage (HTML)
- natural way of componentization
- useful lifecycle events
- framework agnostic
- DOM API

--

### Custom Element Lifecycle

- created
- attached to DOM
- attribute changed
- removed from DOM

--

```javascript
class CustomElement extends HTMLElement {
    connectedCallback() { }
    disconnectedCallback() { }
    attributeChangedCallback(name, oldValue, newValue) { }

    constructor() { super(); /* mandatory call to super() */ }

    static get observedAttributes() {
        return ["attr1", "attr2"];
    }

    someCustomMethod() { }
}

customElements.define('custom-element', CustomElement);
```

--

### Creating custom elements

```javascript
class CustomElement extends HTMLElement {
    constructor() {
        super(); // mandatory call to super()
        console.log('constructor called');
    }
}
customElements.define('custom-element', CustomElement);

document.createElement('custom-element'); // "constructor called"
```
