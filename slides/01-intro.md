# Custom Elements

#### Lightweight alternatives to frameworks

###### Adam Beres-Deak

---

> Custom Elements provide a way to define standardized functionality which can be invoked declaratively with the corresponding HTML markup.

---

```html
<custom-element some-attribute="value"></custom-element>
```

---

### Properties of custom Elements

- natural way of componentization
- useful lifecycle events
- framework agnostic
- declarative usage (HTML)

--

### Custom Element Lifecycle

- created
- attached to DOM
- attribute changed
- removed from DOM

--

```javascript
class CustomElement extends HTMLElement {
    constructor() { super(); /* mandatory call to super() */ }

    static get observedAttributes() {
        return ["attr1", "attr2"];
    }

    connectedCallback() { }
    disconnectedCallback() { }
    attributeChangedCallback(name, oldValue, newValue) { }

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