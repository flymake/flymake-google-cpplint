**NOTE: I recommend that you use the [flycheck](https://github.com/flycheck/flycheck).
Because, you can run the checker more than one. Of course, including [this](https://github.com/flycheck/flycheck-google-cpplint).**

# flymake-google-cpplint.el

cpplint.py by Google for Emacs with flymake-mode.

If you're want to write code according to the [Google C++ Style Guide](http://google-styleguide.googlecode.com/svn/trunk/cppguide.xml), this will help a great deal.

I recommend that the package [google-c-style](http://melpa.milkbox.net/#/google-c-style) also installed with.

To use [cpplint.py](http://google-styleguide.googlecode.com/svn/trunk/cpplint/cpplint.py) with Emacs, you will need `cpplint.py` installed.

You should be able to run

```sh
$ cpplint.py
```

and, you'll also need to install [flymake-easy](https://github.com/purcell/flymake-easy).

# Usage

## Install cpplint.py

Example:

```sh
$ wget http://google-styleguide.googlecode.com/svn/trunk/cpplint/cpplint.py
$ sudo mv cpplint.py /usr/local/bin/cpplint.py
$ sudo chmod 755 /usr/local/bin/cpplint.py
```

## Add to load-path

You'll need to add the directory containing `flymake-google-cpplint.el` to your `load-path`.

If not, also add to your config

```lisp
(add-to-list 'load-path "~/.emacs.d/path/to/flymake-google-cpplint.el")
```

## Add to your Emacs config

```lisp
(require 'flymake-google-cpplint)
(add-hook 'c++-mode-hook 'flymake-google-cpplint-load)
```

## Configure for cpplint.py

```lisp
(custom-set-variables
 '(flymake-google-cpplint-verbose "3")
 '(flymake-google-cpplint-linelength "120")
 ...
 )
```

For more information: [cpplint.py](http://google-styleguide.googlecode.com/svn/trunk/cpplint/cpplint.py)

## cpplint.py command location

By default, the location of the `cpplint.py` command is searched.

```lisp
(custom-set-variables
 '(flymake-google-cpplint-command "/path/to/cpplint.py"))
```

## Where to create temporary copy

One of 'tempdir or 'inplace (default).

```lisp
(custom-set-variables
 '(flymake-google-cpplint-location 'tempdir))
```

# Notes

`cpplint.py` does not support C source files.
