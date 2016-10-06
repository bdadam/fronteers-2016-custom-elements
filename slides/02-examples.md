# Examples

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

### HTTPS-redirect

```html
<https-redirect></https-redirect>
```

```javascript
class HttpsRedirect extends HTMLElement {
    connectedCallback() {
        if (location.protocol !== 'https:') {
            location.protocol = 'https:';
        }
    }
}

customElements.define('https-redirect', HttpsRedirect);
```

--

### Ajax

```html
<x-ajax id="ajax-request"
        url="https://example.com/api/entity"
        method="post"
        params='{ "key": "value" }'
        content-type="application/json"
        data-type="json"
        onsuccess="successHandler"
        onerror="errorHandler">
</x-ajax>
<script>
document.querySelector('#ajax-request')
    .addEventListener('success', e => {
        console.log(e.response)
    });
</script>
```
