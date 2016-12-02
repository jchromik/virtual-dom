# Fork of elm-lang/virtual-dom

This is a fork of the [elm-lang/virtual-dom](https://github.com/elm-lang/virtual-dom) repository which is used not for development but for academic purposes. We try to restore the automatic history replay of the former Elm debugger (see [core/Debug](http://package.elm-lang.org/packages/elm-lang/core/3.0.0/Debug) package in version 3.0.0).

To achieve this we changed the virtual-dom package as follows:
1. We added the buttons "Load" and "Store" that load/store the history from/to the session storage.
2. We also added a "Clear" button for clearing the history.
3. Load is automatically triggered on page load. If there is a Elm history in the session storage it is automatically loaded and replayed.
4. Store is automatically triggered on page unload. When leaving the page (which includes reloading) the Elm history is stored in the session storage.

The following is the original README of elm-lang/virtual-dom.

# Virtual DOM for Elm

A virtual DOM implementation that backs Elm's core libraries for [HTML](http://package.elm-lang.org/packages/elm-lang/html/latest/) and [SVG](http://package.elm-lang.org/packages/elm-lang/svg/latest/). You should almost certainly use those higher-level libraries directly.

It is pretty fast! You can read about that [here](http://elm-lang.org/blog/blazing-fast-html-round-two).
