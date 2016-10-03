# Custom Elements

#### Lightweight alternatives to frameworks

###### Adam Beres-Deak

--

# Next slide


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