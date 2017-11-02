# xplat-button

Cross platform button plugin for jQuery, with support for delegated event handlers.

## $.button( *callback* )

The ```.button()``` method can be seen as a cross-platform replacement for the built-in ```.click()``` method. It listens for the ```click``` and ```touchend``` events.

```javascript
$('#button').button(function () {
    // action
});
```

## $.buttonClass( *selector*, *callback* )

The ```.buttonClass()``` method is a delegated version of the ```.button()``` method. This means it is not bound to a specific element, but rather to a container (for example: ```document.body```) within which elements are targeted by the selector (first parameter). The main benefit of this approach is that the method does not have to be called again when content within the container is changed or added.

This example will fire every time an element with the class ```exampleBtn``` in the page is clicked or tapped, regardless of whether it existed when the method was called or not.

```javascript
$(document.body).buttonClass('.exampleBtn', function () {
    // action
});
```

## ```this```

In the callbacks for both methods, ```this``` refers to the clicked object.

```javascript
$('#button').button(function () {
    var clickedObject = $(this);
});
```