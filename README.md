# Fork of elm-lang/virtual-dom

This is a fork of the [elm-lang/virtual-dom](https://github.com/elm-lang/virtual-dom) repository which is used not for development but for academic purposes. We try to restore the automatic history replay of the former Elm debugger (see [core/Debug](http://package.elm-lang.org/packages/elm-lang/core/3.0.0/Debug) package in version 3.0.0).

To achieve this we changed the virtual-dom package as follows:
1. Import and export buttons do not longer access the file system but store the history in the session storage. This has two effects:
  1. The user does not have to choose a file to store in or load from which removes one level of indirection and leads to a more immediate experience.
  2. There is now only one history of a running Elm application. History is not exchangeable by loading a different file. This removes complexity.
2. There is now a "Clear" button for clearing the history.
3. Import is automatically triggered on page load. If there is a Elm history in the session storage it is automatically loaded and replayed.
4. Export is automatically triggered on page unload. When leaving the page (which includes reloading) the Elm history is stored in the session storage.

The following is the original README of elm-lang/virtual-dom.

# Virtual DOM for Elm

A virtual DOM implementation that backs Elm's core libraries for [HTML](http://package.elm-lang.org/packages/elm-lang/html/latest/) and [SVG](http://package.elm-lang.org/packages/elm-lang/svg/latest/). You should almost certainly use those higher-level libraries directly.

It is pretty fast! You can read about that [here](http://elm-lang.org/blog/blazing-fast-html-round-two).
