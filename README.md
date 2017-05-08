ob-blockdiag.el
---------------

An extension for org-babel to support [blockdiag](http://blockdiag.com/en/).

## Installation

This package is availaple in [MELPA](https://melpa.org/).

> [How to enable MELPA](https://melpa.org/#/getting-started).

With "MELPA enabled emacs" you could install this package by typing this sequence:

``` text
M-x
package-install
ob-blockdiag
⏎
```

Now you could enable this package in your Emacs config with:

``` emacs-lisp
(org-babel-do-load-languages 'org-babel-load-languages
 '((blockdiag . t))
)
```

## Example

> Blockdiag in Fedora installed from `python3-blockdiag` package
> which has unusual executable name.
> Output file name is `ololo.png`

``` org
#+BEGIN_SRC blockdiag :tool blockdiag-3.5 :file ololo.png
blockdiag {
   A [label = "foo"];
   B [label = "bar"];
   C [label = "baz"];
   A -> B [label = "click bar", textcolor="red"];
   B -> C [label = "click baz"];
   C -> A;
}
#+END_SRC
```

## Arguments

There are some things you could customize:

    - `:tool` if you have blockdiag in unusual location or want to use seqdiag or [others](http://blockdiag.com/en/#table-of-contents)
    - `:font` if you want the `:tool` to use provided font
    - `:size` if you want the `:tool` to use custom size

## Errors and output

It recreates a buffer with name `*ob-blockdiag*` every time you evaluating something.

There will be errors and output.
