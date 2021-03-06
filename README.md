[![MELPA](http://melpa.org/packages/puml-mode-badge.svg)](http://melpa.org/#/puml-mode) [![MELPA Stable](http://stable.melpa.org/packages/puml-mode-badge.svg)](http://stable.melpa.org/#/puml-mode)

PlantUML mode for Emacs
=======================

<img src="https://raw.githubusercontent.com/skuro/puml-mode/master/banner.png"
 alt="puml-mode in action" title="Behold the beauty of text-based UML diagrams!" />

> “Pummel me all you want," I say. "Pummel me to death, in fact. My answers will not change."
> The Invierno step back, frowning. "You must love her very much," he says, not unkindly.”
>
> from [The Bitter Kingdom - Fire and Thorns #3](https://www.goodreads.com/book/show/11431896-the-bitter-kingdom)


A [PlantUml](http://plantuml.sourceforge.net/) major mode for Emacs.

Installation
============

Make sure you have [MELPA](http://melpa.org/) enabled in your ``emacs.d``. Then, you can just

    M-x package-install<RET>
    puml-mode<RET>

Also, to enable preview you need to tell `puml-mode` where to locate the PlantUML JAR file. By default it will look for it in `~/plantuml.jar`, but you can specify any location with:

    M-x customize-variable<RET>
    puml-plantuml-jar-path<RET>

Features
========

- Syntax highlight
- Autocompletion
- Preview

Enable the major mode
=====================

You can automatically enable `puml-mode` for files with extension `.puml` or `plantuml` by adding the following to your `.emacsrc`:

    ;; Enable puml-mode for PlantUML files
    (add-to-list 'auto-mode-alist
                 '("\\.puml\\'" . puml-mode)
                 '("\\.plantuml\\'" . puml-mode))

Of course, you can always enable manually the major mode by typing `M-x puml-mode` once in the desired PlantUML file buffer.

Usage
=====

You can either tell `puml-mode` to autocomplete the word before the cursor by typing `M-x puml-complete-symbol`. This will open a popup with all the available completions as found in the list of keywords given by running PlantUML with the `-language` flag.

To render the PlantUML diagram within Emacs, you can also hit `M-x puml-preview`. This will run PlantUML and display the result in the `*PUML-Preview*` buffer. The format used to render the diagram is automagically chosen from what's supported by your Emacs. It will be one of the following, in order of preference:

- SVG
- PNG
- Unicode ASCII art

Default key bindings
====================

The following shortcuts are enabled by default:

    C-c C-c  renders a PlantUML diagram from the current buffer in the best supported format

Credits
=======

This project stemmed from the great work of [Zhang Weize](http://zhangweize.wordpress.com/2010/09/20/update-plantuml-mode/),
and the current code still borrows a lot from it.

Thanks to [Pavel G. Koukoushkin](https://github.com/svargellin) for implementing the preview functionality.

License
=======

Released under the terms of [GPLv2](http://www.gnu.org/licenses/gpl-2.0.html). See [LICENSE.txt](https://github.com/skuro/plantuml-mode/blob/master/LICENSE.txt).
