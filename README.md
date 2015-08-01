# Code-Mirror
Polymer element wrapping [CodeMirror](http://codemirror.net)

## What is this?
Code-Mirror is a Web Component made with [Polymer](https://www.polymer-project.org/) that wraps a default text-area with CodeMirror's highlight syntax, plugins and options.

## Installation and usage

#### Install with npm:
`npm i --save polymer-code-mirror`
#### Install with Bower
`bower install --save polymer-code-mirror`

In your html file import the component and just drop the tag.

```html
...
<head>
    <link rel="import" href="bower_components/polymer-code-mirror/code-mirror.html"/>
</head>
<body>
    <code-mirror mode="python" theme="solarized dark">
    import turtle

    t = turtle.Turtle()

    for c in ['red', 'green', 'yellow', 'blue', 'lime']:
        t.color(c)
        t.forward(72)
        t.left(72)
    </code-mirror>
</body>
```

`<code-mirror>` expects a *mode* (the language). If none is passed, the syntax highlight will not work.

### ~~Hack~~ *Fix* to make `<code-mirror>` work properly
You need this hack to refresh the editors on your site.
```html
<script>
    var els = document.getElementsByClassName('CodeMirror');
    for(var el in els){
        el = parseInt(el, 10);
        if(!isNaN(el)) {
            els[el].CodeMirror.refresh();
        }
    }
</script>
```
## Next features
* [ ] Add all modes and plugins from CodeMirror
* [ ] Fix hack above

## Contributing
Feel free to contribute by sendig a PR.
