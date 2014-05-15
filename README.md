#pylint.vim

[Pylint](http://www.pylint.org/) integration for the
[Vim text editor](http://www.vim.org/).

This is a fork of the original
[`pylint.vim`](http://www.vim.org/scripts/script.php?script_id=891) compiler
script.  Pylint update v1.x broke it, and this fork adapts the
script to the new generation of Pylint.

##Installation

Drop `pylint.vim` in `~/.vim/compiler` directory. Ensure that your `PATH`
environment variable includes the path to `pylint` executable.

Add the following line to the autocmd section of `.vimrc`

    autocmd FileType python compiler pylint

##Usage

Pylint is called after a buffer with Python code is saved. QuickFix window is
opened to show errors, warnings and hints provided by Pylint.  Code rate
calculated by Pylint is displayed at the bottom of the window.

Above is realized with the `:Pylint` command. To disable calling Pylint every
time a buffer is saved put into `.vimrc` file

    let g:pylint_onwrite = 0

Displaying code rate calculated by Pylint can be avoided by setting

    let g:pylint_show_rate = 0

Openning of QuickFix window can be disabled with

    let g:pylint_cwindow = 0

Setting signs for the lines with errors can be enabled with

    let g:pylint_signs = 1

Of course, standard `:make` command can be used as in case of every other
compiler.

Setting highlights for the lines can be disabled with

    let g:pylint_inline_highlight = 0

Coding style warning highlight can be disabled with

    let g:pylint_conventions = 0

Warning highlight can be disabled with

    let g:pylint_warning = 0

