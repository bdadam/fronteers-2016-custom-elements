<!-- .x-slide: data-background="assets/sport-fitness-workout-resolution.jpg" -->
<!-- .slide: data-background="assets/elephant-cub-tsavo-kenya-66898.jpeg" -->
<!-- .slide: id="opening-slide" -->

# Custom Elements

### Lightweight Alternatives to Frameworks

-----

###### Adam Beres-Deak

@bdadamm

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
