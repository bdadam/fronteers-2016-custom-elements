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

- lifecycle
- framework agnostic
- 


--

### Custom Element Lifecycle

- created
- attached to DOM
- attribute changed
- removed from DOM

--

```javascript
class CustomElement extends HTMLElement {
    constructor() {
        super(); // mandatory call to super()
    }

    static get observedAttributes() {
        return ["attr1", "attr2"];
    }

    connectedCallback() { }
    disconnectedCallback() { }
    attributeChangedCallback(name, oldValue, newValue) { }
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

--

# Usages

--

### Icons
<style>
.icon-demo {
    width: 32px;
    height: 32px;
    color: green;
    overflow: hidden;
    display: inline-block;
    line-height: 1;
}

.icon-green path {
    fill: green;
}

.icon-blue path {
    fill: blue;
}

.icon-red path {
    fill: red;
}
.icon-yellow path {
    fill: yellow;
}
</style>

<x-icon class="icon-demo icon-green" type="happy"></x-icon> <x-icon class="icon-demo icon-blue" type="wink"></x-icon> <x-icon class="icon-demo icon-yellow" type="tongue"></x-icon> <x-icon class="icon-demo icon-red" type="evil"></x-icon>

```html
<x-icon type="happy"  class="icon-demo icon-green"></x-icon>
<x-icon type="wink"   class="icon-demo icon-blue"></x-icon>
<x-icon type="tongue" class="icon-demo icon-yellow"></x-icon>
<x-icon type="evil"   class="icon-demo icon-red"></x-icon>
```

[goo.gl/GEQqE9](https://goo.gl/GEQqE9)

--

### Tracking

```html
<x-tracking type="google-analytics"
            tid="UA-XXXXX-Y"
            send="pageview">
</x-tracking>

<x-tracking type="google-analytics"
            send="event"
            category="Video"
            action="play"
            label="Cat playing piano">
</x-tracking>
```

--

### Notification

<x-notification type="success" message="Action completed successfully!" timeout="5000"></x-notification>

```html
<x-notification type="success"
                message="Action completed successfully!"
                timeout="5000">
</x-notification>
```

--

### Notification (code)

```javascript
class XNotification extends HTMLElement {
    connectedCallback() {
        const message = this.getAttribute('message');
        const type = this.getAttribute('type');
        const style = type === 'success'
                ? 'background-color: #dff0d8; color: #3c763d; ...'
                : 'background-color: #ccc; color: #444;';
        
        this.innerHTML = `<div style="${style}">${message}</div>`;
    }
}

customElements.define('x-notification', XNotification);

```

--

### Notification (code/2)
```javascript
class XNotification extends HTMLElement {
    
    show() {
        this.removeAttribute('hidden');
    }

    hide() {
        this.setAttribute('hidden', '');
    }
}

customElements.define('x-notification', XNotification);

document.querySelector('#success-notification').show();
// or
document.querySelector('#success-notification').hide();
```

---

### Custom Elements are reality

* Native support in Chrome and Firefox (earlier version of the spec)
* Most features can be polyfilled (even IE8, iOS 5.1, Android 2.2)
* [github/WebReflection/document-register-element](https://github.com/WebReflection/document-register-element) (5kB min+gzip)

---

```html
<this-presentation has-ended="true">
    <available-at>             goo.gl/aCJfKJ            </available-at>

    <presented-by>
        <presenter-name>       Adam Beres-Deak          </presenter-name>
        <presenter-website>    bdadam.com               </presenter-website>

        <presenter-twitter>    @bdadamm                 </presenter-twitter>
        <presenter-github>     github/bdadam            </presenter-github>
        <presenter-email>      me@bdadam.com            </presenter-github>
    </presented-by>
</this-presentation>
```