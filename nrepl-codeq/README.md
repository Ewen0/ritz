# nrepl-codeq

An nREPL middleware for use with datomic's codeq. `elisp` for nrepl.el is
provided to use the middleware.

## Usage

You will need an nREPL srever running the codeq middleware, and to have the
`nrepl-ritz.el` emacs packgae installed.

[Download datomic free](http://downloads.datomic.com/free.html), and install the
datomic jar in your local repo following the
[instructions](http://docs.datomic.com/integrating-peer-lib.html).

[Clone codeq](https://github.com/Datomic/codeq), and run `lein install`.

Add nrepl-codeq to your `:dev` (in `project.clj`) or `:user` (in
`~/.lein/profiles.clj`) dependencies.

```clj
:dependencies [[ritz/ritz-nrepl-middleware "0.5.0"]]
```

Add wrap-codeq-def to your nREPL middleware (in `project.clj` or your `:user`
profile).

```clj
:repl-options {:nrepl-middleware
                [ritz.nrepl.middleware.codeq-def/wrap-codeq-def]}
```

To view the definitions of a symbol within an nrepl.el session, use

    M-x nrepl-codeq-def

## License

Copyright © 2012 Hugo Duncan

Distributed under the Eclipse Public License.